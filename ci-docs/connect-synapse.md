---
title: Συνδέστε μια προέλευση δεδομένων του Azure Synapse (έκδοση προεπισκόπησης)
description: Χρησιμοποιήστε μια βάση δεδομένων στο Azure Synapse ως αρχείο προέλευσης δεδομένων στο Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259798"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Συνδέστε μια προέλευση δεδομένων του Azure Synapse Analytics (έκδοση προεπισκόπησης)

Το Azure Synapse Analytics είναι μια υπηρεσία ανάλυσης επιχειρηματικών δεδομένων που επιταχύνει το χρόνο για πληροφορίες σχετικά με τις αποθήκες δεδομένων και τα μεγάλα συστήματα δεδομένων. Το Azure Synapse Analytics συγκεντρώνει τις καλύτερες τεχνολογίες SQL που χρησιμοποιούνται στην αποθήκευση δεδομένων μεγάλων επιχειρήσεων, τις τεχνολογίες Spark που χρησιμοποιούνται για μεγάλα δεδομένα, το Data Explorer για ανάλυση σειρών καταγραφής και χρόνου, τις διοχέτευσης για ενοποίηση δεδομένων και το ETL/ELT, καθώς και την πλήρη ενοποίηση με άλλες υπηρεσίες Azure όπως το Power BI, το Cosmos DB και το AzureML.

Για περισσότερες πληροφορίες, δείτε την [Επισκόπηση Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Προϋποθέσεις

> [!NOTE]
> Οι Synapse Workspaces που έχουν [ενεργοποιημένο το τείχος προστασίας](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) δεν υποστηρίζονται αυτή τη στιγμή.
> [!IMPORTANT]
> Φροντίστε να ορίσετε όλες τις **αντιστοιχίσεις ρόλων** όπως περιγράφεται.  

**Στο Customer Insights**:

* Έχετε ρόλο **Διαχειριστή** στο Customer Insights. Μάθετε περισσότερα σχετικά με τα [δικαιώματα χρηστών στο Customer Insights](permissions.md#add-users).

**Στο Azure**:

- Μια ενεργή συνδρομή Azure.

- Εάν χρησιμοποιείτε έναν νέο λογαριασμό Azure Data Lake Storage Gen2, η *αρχή υπηρεσίας για το Customer Insights* που είναι Dynamics 365 AI για Customer Insights" χρειάζεται δικαιώματα **συμβαλλόντος δεδομένων BLOB αποθήκευσης**. Μάθετε περισσότερα σχετικά με [τη σύνδεση σε ένα Azure Data Lake Storage με μια αρχή εξυπηρέτησης για το Customer Insights](connect-service-principal.md). Το Data Lake Storage Gen2 **πρέπει να έχει ενεργοποιημένο τον** [ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace).

- Στην ομάδα πόρων όπου βρίσκεται το Azure Synapse workspace, η *αρχή υπηρεσίας* που είναι Dynamics 365 AI για Customer Insights" και ο *χρήστης για Customer Insights* χρειάζονται ανάθεση τουλάχιστον δικαιωμάτων **Αναγνώστη**. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Εκχώρηση ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal).

- Ο *χρήστης* χρειάζεται δικαιώματα **Συμβαλλόντος δεδομένων BLOB αποθήκευσης** στον λογαριασμό Azure Data Lake Storage Gen2 όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse. Μάθετε περισσότερα σχετικά με [τη χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Η *[διαχειριζόμενη ταυτότητα χώρου εργασίας Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* χρειάζεται δικαιώματα **χρειάζεται δικαιώματα** στο λογαριασμό Azure Data Lake Storage Gen2όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse. Μάθετε περισσότερα σχετικά για τη [χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Στο Azure Synapse workspace, η *αρχή υπηρεσίας για το Customer Insights* που είναι Dynamics 365 AI για Customer Insights" χρειάζεται την ανάθεση του ρόλου του **Διαχειριστή Synapse**. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Τρόπος ρύθμισης ελέγχου πρόσβασης για το χώρο εργασίας Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Εάν το περιβάλλον Customer Insights αποθηκεύει δεδομένα στο [δικό σας Azure Data Lake Storage](own-data-lake-storage.md), ο χρήστης που ρυθμίζει τη σύνεση στο Azure Synapse Analytics χρειάζεται τουλάχιστον τον ενσωματωμένο ρόλο **Αναγνώστης** στον χώρο αποθήκευσης Data Lake. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Εκχώρηση ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Σύνδεση στη βάση δεδομένων λίμνης δεδομένων στο Azure Synapse Analytics

1. Μεταβείτε στα **Δεδομένα** > **Προελεύσεις δεδομένων**.

1. Επιλέξτε **Προσθήκη προέλευσης δεδομένων**.

1. Επιλέξτε τη μέθοδο **Azure Synapse Analytics (Έκδοση προεπισκόπησης)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Παράθυρο διαλόγου για σύνδεση σε δεδομένα Synapse Analytics":::
  
1. Καταχωρήστε ένα **Όνομα** για την προέλευση δεδομένων και μια προαιρετική **Περιγραφή**.

1. Επιλέξτε μια [διαθέσιμη σύνδεση](connections.md) στο Azure Synapse Analytics ή [δημιουργήστε μια νέα](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Επιλέξτε μια **Βάση δεδομένων** από το χώρο εργασίας που είναι συνδεδεμένος στην επιλεγμένη σύνδεση του Azure Synapse Analytics και επιλέξτε **Επόμενο**. Προς το παρόν, υποστηρίζουμε μόνο τον τύπο βάσης δεδομένων *Βάση δεδομένων λίμνης*.

1. Επιλέξτε τις οντότητες προς πρόσληψη από τη συνδεδεμένη βάση δεδομένων και επιλέξτε **Επόμενο**.

1. Προαιρετικά, επιλέξτε τις οντότητες δεδομένων για να επιτρέψετε τη δημιουργία προφίλ δεδομένων.

1. Επιλέξτε **Αποθήκευση** για να εφαρμόσετε την επιλογή σας και ξεκινήστε την πρόσληψη των δεδομένων από την προέλευση δεδομένων που μόλις δημιουργήσατε και που συνδέεται με τους πίνακες βάσης δεδομένων λίμνης στο Azure Synapse Analytics. Ανοίγει η σελίδα **Προελεύσεις δεδομένων** που εμφανίζει τη νέα προέλευση δεδομένων σε κατάσταση **Ανανέωσης**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Η φόρτωση των δεδομένων μπορεί να διαρκέσει πολύ. Μετά από μια επιτυχημένη ανανέωση, τα δεδομένα που απορροφήθηκαν μπορούν να ελεγχθούν από τη σελίδα [**Οντότητες**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]