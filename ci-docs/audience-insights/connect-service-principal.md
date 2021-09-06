---
title: Σύνδεση σε έναν λογαριασμό Azure Data Lake Storage χρησιμοποιώντας μια αρχή υπηρεσίας
description: Χρησιμοποιήστε μια αρχή υπηρεσίας Azure για να συνδεθείτε στη δική σας λίμνη δεδομένων.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461148"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Σύνδεση σε έναν λογαριασμό Azure Data Lake Storage χρησιμοποιώντας μια αρχή υπηρεσίας Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Τα αυτοματοποιημένα εργαλεία που χρησιμοποιούν υπηρεσίες Azure θα πρέπει να έχουν πάντοτε περιορισμένα δικαιώματα. Αντί να συνδέεστε με εφαρμογές ως πλήρως προνομιούχος χρήστης, το Azure προσφέρει τις αρχές εξυπηρέτησης. Διαβάστε στη συνέχεια για να μάθετε πώς να συνδέετε το Dynamics 365 Customer Insights με έναν λογαριασμό Azure Data Lake Storage χρησιμοποιώντας μια αρχή υπηρεσίας Azure αντί για κλειδιά λογαριασμού χώρου αποθήκευσης. 

Μπορείτε να χρησιμοποιήσετε την αρχή υπηρεσίας για [να προσθέσετε ή να επεξεργαστείτε με ασφάλεια έναν φάκελο του Common Data Model ως προέλευση δεδομένων](connect-common-data-model.md) ή [να δημιουργήσετε ή να ενημερώσετε ένα περιβάλλον](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Ο λογαριασμός Data Lake Storage που θα χρησιμοποιήσει<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> την αρχή υπηρεσίας πρέπει να έχει [ενεργοποιημένο τον ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace).
> - Χρειάζεστε δικαιώματα διαχειριστή για τη συνδρομή σας Azure για τη δημιουργία της αρχής εξυπηρέτησης.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Δημιουργία μιας αρχής υπηρεσίας Azure για Customer Insights

Πριν δημιουργήσετε μια νέα αρχή υπηρεσίας για πληροφορίες κοινού ή πληροφορίες δέσμευσης, ελέγξτε αν υπάρχει ήδη στον οργανισμό σας.

### <a name="look-for-an-existing-service-principal"></a>Αναζήτηση υπάρχουσας αρχής εξυπηρέτησης

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com) και συνδεθείτε στον οργανισμό σας.

2. Από **Υπηρεσίες Azure**, επιλέξτε **Azure Active Directory**.

3. Στην περιοχή **Διαχείριση**, επιλέξτε **Εταιρικές εφαρμογές**.

4. Αναζήτησης για τη Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> αναγνωριστικό εφαρμογής:
   - Πληροφορίες κοινού: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` με το όνομα `Dynamics 365 AI for Customer Insights`
   - Πληροφορίες δέσμευσης: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` με το όνομα `Dynamics 365 AI for Customer Insights engagement insights`

5. Εάν βρείτε μια καρτέλα που ταιριάζει, αυτό σημαίνει ότι η αρχή υπηρεσίας υπάρχει ήδη. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Στιγμιότυπο οθόνης που δείχνει μια υπάρχουσα αρχή υπηρεσίας.":::
   
6. Εάν δεν επιστραφούν αποτελέσματα, δημιουργήστε έναν νέο διευθυντή εξυπηρέτησης.

>[!NOTE]
>Για να κάνετε χρήση της πλήρους ισχύος του Dynamics 365 Customer Insights, προτείνουμε να προσθέσετε και τις δύο εφαρμογές στην αρχή υπηρεσίας.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Δημιουργία μιας νέας αρχής εξυπηρέτησης
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Εγκαταστήστε την πιο πρόσφατη έκδοση του Azure Active Directory PowerShell for Graph. Για περισσότερες πληροφορίες, μεταβείτε στην [Eγκατάσταση του Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Στον υπολογιστή σας, επιλέξτε το πλήκτρο των Windows στο πληκτρολόγιό σας και αναζητήστε το **Windows PowerShell** και επιλέξτε **Εκτέλεση ως Διαχειριστής**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Στο παράθυρο PowerShell που ανοίγει, καταχωρείστε `Install-Module AzureAD`.

2. Δημιουργήστε την αρχή υπηρεσίας για Customer Insights με τη λειτουργική μονάδα Azure AD PowerShell.

   1. Στο παράθυρο PowerShell, καταχωρείστε `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Αντικαταστήστε το *"[αναγνωριστικό του μισθωτή σας]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> με το πραγματικό αναγνωριστικό του μισθωτή σας, στο οποίο θέλετε να δημιουργήσετε την αρχή υπηρεσίας. Η παράμετρος ονόματος περιβάλλοντος, `AzureEnvironmentName`, είναι προαιρετική.
  
   1. Εισαγάγετε `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Αυτή η εντολή δημιουργεί τον διευθυντή εξυπηρέτησης για πληροφορίες κοινού σχετικά με τον επιλεγμένο μισθωτή. 

   1. Εισαγάγετε `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Αυτή η εντολή δημιουργεί την αρχή υπηρεσίας για πληροφορίες δέσμευσης<!--note from editor: Edit okay?--> στον επιλεγμένο μισθωτή.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Εκχώρηση δικαιωμάτων στον διευθυντή εξυπηρέτησης για πρόσβαση στον λογαριασμό αποθήκευσης

Μεταβείτε στην πύλη Azure για να εκχωρήσετε δικαιώματα στον διευθυντή εξυπηρέτησης για τον λογαριασμό χώρου αποθήκευσης που θέλετε να χρησιμοποιήσετε στις πληροφορίες κοινού.

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com) και συνδεθείτε στον οργανισμό σας.

1. Ανοίξτε τον λογαριασμό χώρου αποθήκευσης στον οποίο θέλετε να έχει πρόσβαση ο διευθυντής εξυπηρέτησης για πληροφορίες κοινού.

1. Στο αριστερό τμήμα παραθύρου, επιλέξτε **Στοιχείο ελέγχου πρόσβασης (IAM)** και, στη συνέχεια, επιλέξτε **Προσθήκη** > **Προσθήκη αντιστοίχισης ρόλου**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Στιγμιότυπο οθόνης που δείχνει την πύλη Azure κατά την προσθήκη μιας ανάθεσης ρόλου.":::

1. Στο τμήμα παραθύρου **Προσθήκη ανάθεσης ρόλων**, ορίστε τις ακόλουθες ιδιότητες:
   - Ρόλος: **Συμβάλλων δεδομένων αντικειμένου Blob αποθήκευσης**
   - Ανάθεση πρόσβασης σε: **Χρήστη, ομάδα ή διευθυντή εξυπηρέτησης**
   - Επιλέξτε: **Dynamics 365 AI για Customer Insights** και **Dynamics 365 AI για πληροφορίες δέσμευσης του Customer Insights** (οι δύο [αρχές υπηρεσίας](#create-a-new-service-principal) που δημιουργήσατε νωρίτερα σε αυτήν τη διαδικασία)

1.  Επιλέξτε **Αποθήκευση**.

Μπορεί να διαρκέσει έως και 15 λεπτά για να γίνουν οι αλλαγές.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Εισαγάγετε το αναγνωριστικό πόρου Azure ή τις λεπτομέρειες συνδρομής Azure μέσα στο συνημμένο λογαριασμού χώρου αποθήκευσης στις πληροφορίες κοινού

Μπορείτε να<!--note from editor: Edit suggested only if this section is optional.--> επισυνάψτε έναν λογαριασμό Data Lake Storage στις πληροφορίες κοινού για να [αποθηκεύσετε δεδομένα εξόδου](manage-environments.md) ή [να τα χρησιμοποιήσετε ως προέλευση δεδομένων](connect-common-data-service-lake.md). Αυτή η επιλογή σάς επιτρέπει να επιλέξετε μεταξύ μιας προσέγγισης που βασίζεται σε πόρους ή μιας προσέγγισης που βασίζεται σε συνδρομή. Ανάλογα με την προσέγγιση που επιλέγετε, ακολουθήστε τη διαδικασία σε μία από τις ακόλουθες ενότητες.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Σύνδεση λογαριασμού χώρου αποθήκευσης βάσει πόρων

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com), συνδεθείτε στη συνδρομή σας και ανοίξτε τον λογαριασμό χώρου αποθήκευσης.

1. Στο αριστερό τμήμα παραθύρου, μεταβείτε στην επιλογή **Ρυθμίσεις** > **Ιδιότητες**.

1. Αντιγράψτε την τιμή αναγνωριστικού πόρου του λογαριασμού αποθήκευσης.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Αντιγράψτε το αναγνωριστικό πόρου του λογαριασμού αποθήκευσης.":::

1. Στις πληροφορίες κοινού, εισαγάγετε το αναγνωριστικό πόρου στο πεδίο πόρου που εμφανίζεται στην οθόνη σύνδεσης λογαριασμού αποθήκευσης.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Εισαγάγετε τις πληροφορίες αναγνωριστικού πόρου του λογαριασμού αποθήκευσης.":::   

1. Συνεχίστε με τα υπόλοιπα βήματα στις πληροφορίες κοινού για να επισυνάψετε τον λογαριασμό χώρου αποθήκευσης.

### <a name="subscription-based-storage-account-connection"></a>Σύνδεση λογαριασμού χώρου αποθήκευσης βάσει συνδρομής

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com), συνδεθείτε στη συνδρομή σας και ανοίξτε τον λογαριασμό χώρου αποθήκευσης.

1. Στο αριστερό τμήμα παραθύρου, μεταβείτε στην επιλογή **Ρυθμίσεις** > **Ιδιότητες**.

1. Επανεξετάστε τη **Συνδρομή**, την **Ομάδα πόρων** και το **Όνομα** του λογαριασμού χώρου αποθήκευσης, για να βεβαιωθείτε ότι έχετε επιλέξει τις σωστές τιμές στις πληροφορίες κοινού.

1. Στις πληροφορίες κοινού, επιλέξτε τις τιμές για τα αντίστοιχα πεδία κατά την επισύναψη του λογαριασμού χώρου αποθήκευσης.

1. Συνεχίστε με τα υπόλοιπα βήματα στις πληροφορίες κοινού για να επισυνάψετε τον λογαριασμό χώρου αποθήκευσης.


[!INCLUDE[footer-include](../includes/footer-banner.md)]