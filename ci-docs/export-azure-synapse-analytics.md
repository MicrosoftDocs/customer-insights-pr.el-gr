---
title: Εξαγωγή δεδομένων στο Azure Synapse Analytics (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τη σύνδεση στο Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196394"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Εξαγωγή δεδομένων στο Azure Synapse Analytics (έκδοση προεπισκόπησης)

Το Azure Synapse είναι μια υπηρεσία ανάλυσης που επιταχύνει το χρόνο λήψης πληροφοριών σε αποθήκες δεδομένων και συστήματα μαζικών δεδομένων. Μπορείτε να συγκεντρώνετε και να χρησιμοποιείτε δεδομένα του Customer Insights στο [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Προϋποθέσεις

> [!NOTE]
> Φροντίστε να ορίσετε όλες τις **αντιστοιχίσεις ρόλων** όπως περιγράφεται.

- Στο Customer Insights, σας Azure Active Directory (AD) ο λογαριασμός χρήστη πρέπει να έχει ένα [Ρόλο διαχειριστή](permissions.md#assign-roles-and-permissions).

Στο Azure:

- Μια ενεργή συνδρομή Azure.

- Εάν χρησιμοποιείτε ένα νέο Azure Data Lake Storage λογαριασμό Gen2, η [κύρια υπηρεσία για το Customer Insights](connect-service-principal.md) έχει άδειες **Storage Blob Data Contributor**. Το Data Lake Storage Gen2 **πρέπει να έχει ενεργοποιημένο τον** [ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace).

- Στην ομάδα πόρων όπου το βρίσκεται Azure Synapse, στον *workspace* και στον *Azure AD χρήστη με δικαιώματα διαχειριστή στο Customer Insights* πρέπει να ανατεθούν τουλάχιστον **;άδειες** [Αναγνώστη](/azure/role-based-access-control/role-assignments-portal).

- Ο *Azure AD χρήστης με δικαιώματα διαχειριστή στο Customer Insights* έχει άδειες **Storage Blob Data Contributor** στον Azure Data Lake Storage Λογαριασμό Gen2 όπου βρίσκονται τα δεδομένα και συνδέονται με τον Azure Synapse workspace. Μάθετε περισσότερα σχετικά με [τη χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Η *[Azure Synapse διαχειριζόμενη ταυτότητα χώρου εργασίας](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* έχει άδειες **Storage Blob Data Contributor** στον Λογαριασμό Gen2 Azure Data Lake Storage όπου βρίσκονται τα δεδομένα και συνδέονται με τον Azure Synapse workspace. Μάθετε περισσότερα σχετικά για τη [χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Στον Azure Synapse workspace, η *κύρια υπηρεσία για το Customer Insights* έχει ανατεθημένο ρόλο **Διαχειριστή**[Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Ρύθμιση σύνδεσης σε Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Azure Synapse Analytics**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυτήν τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Επιλέξτε ή αναζητήστε τη συνδρομή στην οποία θέλετε να χρησιμοποιήσετε τα δεδομένα του Customer Insights. Μόλις επιλεγεί μια συνδρομή, μπορείτε επίσης να επιλέξετε **Χώρος εργασίας**, **Λογαριασμός χώρου αποθήκευσης** και **Περιέκτης**.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)] Για να διαμορφώσετε την εξαγωγή με μια κοινόχρηστη σύνδεση, χρειάζεστε τουλάχιστον δικαιώματα **Συνεισφέρων** στο Customer Insights.

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Azure Synapse Analytics. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Παράσχετε ένα αναγνωρίσιμο **εμφανιζόμενο όνομα** για την εξαγωγή σας και ένα **όνομα βάσης δεδομένων**. Η εξαγωγή θα δημιουργήσει ένα νέο [Azure Synapse βάση δεδομένων lake](/azure/synapse-analytics/database-designer/concepts-lake-database) στον χώρο εργασίας που ορίζεται στη σύνδεση.

1. Επιλέξτε ποιες οντότητες θέλετε να εξαγάγετε στο Azure Synapse Analytics.
   > [!NOTE]
   > Οι προελεύσεις δεδομένων που βασίζονται σε έναν [φάκελο Common Data Model](connect-common-data-model.md) δεν υποστηρίζονται.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Για να υποβάλετε ερωτήματα σχετικά με τα δεδομένα που έχουν εξαχθεί στο Synapse Analytics, χρειάζεστε πρόσβαση στο **Πρόγραμμα ανάγνωσης δεδομένων χώρου αποθήκευσης αντικειμένων Blob** στον χώρο αποθήκευσης προορισμού στον χώρο εργασίας εξαγωγής.

## <a name="update-an-export"></a>Ενημέρωση εξαγωγής

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Επεξεργασία** στην εξαγωγή που θέλετε να ενημερώσετε.

   - **Προσθέστε** ή **Καταργήστε** οντότητες από την επιλογή. Εάν οι οντότητες καταργηθούν από την επιλογή, δεν διαγράφονται από τη βάση δεδομένων Synapse Analytics. Ωστόσο, οι μελλοντικές ανανεώσεις δεδομένων δεν θα ενημερώσουν τις οντότητες που καταργήθηκαν σε αυτήν τη βάση δεδομένων.

   - Η **Αλλαγή του ονόματος βάσης δεδομένων** δημιουργεί μια νέα βάση δεδομένων Synapse Analytics. Η βάση δεδομένων με το όνομα που είχε ρυθμιστεί προηγουμένως δεν θα λαμβάνει ενημερώσεις σε μελλοντικές ανανεώσεις.

[!INCLUDE [footer-include](includes/footer-banner.md)]
