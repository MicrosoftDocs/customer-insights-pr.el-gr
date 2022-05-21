---
title: Σύνδεση σε έναν λογαριασμό Azure Data Lake Storage χρησιμοποιώντας μια αρχή υπηρεσίας
description: Χρησιμοποιήστε μια αρχή υπηρεσίας Azure για να συνδεθείτε στη δική σας λίμνη δεδομένων.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 776eee79c25edbd40ed119510a314f5126933c3e
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739162"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Σύνδεση σε έναν λογαριασμό Azure Data Lake Storage χρησιμοποιώντας μια αρχή υπηρεσίας Azure

Αυτό το άρθρο ασχολείται με το πώς να συνδέσετε το Dynamics 365 Customer Insights με έναν λογαριασμό Azure Data Lake Storage χρησιμοποιώντας μια αρχή υπηρεσίας Azure αντί για κλειδιά λογαριασμού υπηρεσίας αποθήκευσης. 

Τα αυτοματοποιημένα εργαλεία που χρησιμοποιούν υπηρεσίες Azure θα πρέπει να έχουν πάντοτε περιορισμένα δικαιώματα. Αντί να συνδέεστε με εφαρμογές ως πλήρως προνομιούχος χρήστης, το Azure προσφέρει τις αρχές εξυπηρέτησης. Μπορείτε να χρησιμοποιήσετε τις αρχές εξυπηρέτησης για να [προσθέσετε ή να επεξεργαστείτε με ασφάλεια ένα φάκελο του Common Data Model ως προέλευση δεδομένων](connect-common-data-model.md) ή [να δημιουργήσετε ή να ενημερώσετε ένα περιβάλλον](create-environment.md).

> [!IMPORTANT]
> - Ο λογαριασμός αποθήκευσης Data Lake που θα χρησιμοποιήσει την αρχή υπηρεσίας πρέπει να είναι Gen2 και να έχει [ενεργοποιημένο τον ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace). Οι λογαριασμοί αποθήκευσης Azure Data Lake Gen1 δεν υποστηρίζονται.
> - Χρειάζεστε δικαιώματα διαχειριστή για τη συνδρομή σας στο Azure για να δημιουργήσετε μια αρχή υπηρεσίας.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Δημιουργία μιας αρχής υπηρεσίας Azure για Customer Insights

Πριν δημιουργήσετε μια νέα αρχή εξυπηρέτησης για το Customer Insights, ελέγξτε εάν υπάρχει ήδη στον οργανισμό σας.

### <a name="look-for-an-existing-service-principal"></a>Αναζήτηση υπάρχουσας αρχής εξυπηρέτησης

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com) και συνδεθείτε στον οργανισμό σας.

2. Από **Υπηρεσίες Azure**, επιλέξτε **Azure Active Directory**.

3. Στην περιοχή **Διαχείριση**, επιλέξτε **Εταιρικές εφαρμογές**.

4. Προσθέστε ένα φίλτρο για **την εκκίνηση του αναγνωριστικού εφαρμογής με** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ή αναζητήστε το όνομα `Dynamics 365 AI for Customer Insights`.

5. Εάν βρείτε μια καρτέλα που ταιριάζει, αυτό σημαίνει ότι η αρχή υπηρεσίας υπάρχει ήδη. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Στιγμιότυπο οθόνης που δείχνει μια υπάρχουσα αρχή υπηρεσίας.":::
   
6. Εάν δεν επιστραφούν αποτελέσματα, δημιουργήστε έναν νέο διευθυντή εξυπηρέτησης.

### <a name="create-a-new-service-principal"></a>Δημιουργία μιας νέας αρχής εξυπηρέτησης

1. Εγκαταστήστε την πιο πρόσφατη έκδοση του Azure Active Directory PowerShell for Graph. Για περισσότερες πληροφορίες, μεταβείτε στην [Eγκατάσταση του Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Στον υπολογιστή σας, επιλέξτε το πλήκτρο των Windows στο πληκτρολόγιό σας και αναζητήστε το **Windows PowerShell** και επιλέξτε **Εκτέλεση ως Διαχειριστής**.
   
   1. Στο παράθυρο PowerShell που ανοίγει, καταχωρείστε `Install-Module AzureAD`.

2. Δημιουργήστε την αρχή υπηρεσίας για Customer Insights με τη λειτουργική μονάδα Azure AD PowerShell.

   1. Στο παράθυρο PowerShell, καταχωρείστε `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Αντικαταστήστε το *[δικό σας αναγνωριστικό καταλόγου]* με το πραγματικό αναγνωριστικό καταλόγου της συνδρομής σας στο Azure, όπου θέλετε να δημιουργήσετε τον κύριο υπηρεσίας. Η παράμετρος ονόματος περιβάλλοντος, `AzureEnvironmentName`, είναι προαιρετική.
  
   1. Εισαγάγετε `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Αυτή η εντολή δημιουργεί τον κύριο υπηρεσίας για το Customer Insights στην επιλεγμένη συνδρομή Azure. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Εκχώρηση δικαιωμάτων στον διευθυντή εξυπηρέτησης για πρόσβαση στον λογαριασμό αποθήκευσης

Μεταβείτε στην πύλη Azure για να εκχωρήσετε δικαιώματα στον κύριο υπηρεσίας για το λογαριασμό χώρου αποθήκευσης που θέλετε να χρησιμοποιήσετε στο Customer Insights.

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com) και συνδεθείτε στον οργανισμό σας.

1. Ανοίξτε το λογαριασμό χώρου αποθήκευσης στον οποίο θέλετε να έχει πρόσβαση ο κύριος υπηρεσίας για το Customer Insights.

1. Στο αριστερό τμήμα παραθύρου, επιλέξτε **Στοιχείο ελέγχου πρόσβασης (IAM)** και, στη συνέχεια, επιλέξτε **Προσθήκη** > **Προσθήκη αντιστοίχισης ρόλου**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Στιγμιότυπο οθόνης που δείχνει την πύλη Azure κατά την προσθήκη μιας ανάθεσης ρόλου.":::

1. Στο τμήμα παραθύρου **Προσθήκη ανάθεσης ρόλων**, ορίστε τις ακόλουθες ιδιότητες:
   - Ρόλος: **Συμβάλλων δεδομένων αντικειμένου Blob αποθήκευσης**
   - Ανάθεση πρόσβασης σε: **Χρήστη, ομάδα ή διευθυντή εξυπηρέτησης**
   - Επιλέξτε μέλη: **Dynamics 365 AI για Customer Insights** (ο [κύριος εξυπηρέτησης](#create-a-new-service-principal) που δημιουργήσατε νωρίτερα σε αυτήν τη διαδικασία)

1.  Επιλέξτε **Έλεγχος + αντιστοίχιση**.

Μπορεί να διαρκέσει έως και 15 λεπτά για να γίνουν οι αλλαγές.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Εισαγάγετε το αναγνωριστικό πόρου Azure ή τις λεπτομέρειες της συνδρομής Azure στο συνημμένο λογαριασμό αποθήκευσης στο Customer Insights

Μπορείτε να επισυνάψετε ένα λογαριασμό Data Lake Storage στο Customer Insights [για να αποθηκεύσετε δεδομένα εξόδου](manage-environments.md) ή να [ τα χρησιμοποιήσετε ως προέλευση δεδομένων](connect-dataverse-managed-lake.md). Αυτή η επιλογή σάς επιτρέπει να επιλέξετε μεταξύ μιας προσέγγισης που βασίζεται σε πόρους ή μιας προσέγγισης που βασίζεται σε συνδρομή. Ανάλογα με την προσέγγιση που επιλέγετε, ακολουθήστε τη διαδικασία σε μία από τις ακόλουθες ενότητες.

### <a name="resource-based-storage-account-connection"></a>Σύνδεση λογαριασμού χώρου αποθήκευσης βάσει πόρων

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com), συνδεθείτε στη συνδρομή σας και ανοίξτε τον λογαριασμό χώρου αποθήκευσης.

1. Στο αριστερό τμήμα παραθύρου, μεταβείτε στην επιλογή **Ρυθμίσεις** > **Ιδιότητες**.

1. Αντιγράψτε την τιμή αναγνωριστικού πόρου του λογαριασμού αποθήκευσης.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Αντιγράψτε το αναγνωριστικό πόρου του λογαριασμού αποθήκευσης.":::

1. Στο Customer Insights, εισαγάγετε το αναγνωριστικό πόρου στο πεδίο πόρου που εμφανίζεται στην οθόνη σύνδεσης λογαριασμού χώρου αποθήκευσης.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Εισαγάγετε τις πληροφορίες αναγνωριστικού πόρου του λογαριασμού αποθήκευσης.":::   

1. Συνεχίστε με τα υπόλοιπα βήματα στο Customer Insights για να επισυνάψετε τον λογαριασμό χώρου αποθήκευσης.

### <a name="subscription-based-storage-account-connection"></a>Σύνδεση λογαριασμού χώρου αποθήκευσης βάσει συνδρομής

1. Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com), συνδεθείτε στη συνδρομή σας και ανοίξτε τον λογαριασμό χώρου αποθήκευσης.

1. Στο αριστερό τμήμα παραθύρου, μεταβείτε στην επιλογή **Ρυθμίσεις** > **Ιδιότητες**.

1. Εξετάστε τη **Συνδρομή**, την **Ομάδα πόρων** και το **Όνομα** του λογαριασμού χώρου αποθήκευσης για να βεβαιωθείτε ότι έχετε επιλέξει τις σωστές τιμές στο Customer Insights.

1. Στο Customer Insights, επιλέξτε τις τιμές για τα αντίστοιχα πεδία κατά την επισύναψη του λογαριασμού χώρου αποθήκευσης.

1. Συνεχίστε με τα υπόλοιπα βήματα στο Customer Insights για να επισυνάψετε τον λογαριασμό χώρου αποθήκευσης.


[!INCLUDE [footer-include](includes/footer-banner.md)]