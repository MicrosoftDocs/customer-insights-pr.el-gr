---
title: Κατανάλωση δεδομένων από το Azure Synapse Analytics
description: Χρησιμοποιήστε μια βάση δεδομένων στο Azure Synapse ως αρχείο προέλευσης δεδομένων στο Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646868"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Συνδέστε μια προέλευση δεδομένων του Azure Synapse (έκδοση προεπισκόπησης)

Το Azure Synapse Analytics είναι μια υπηρεσία ανάλυσης επιχειρηματικών δεδομένων που επιταχύνει το χρόνο για πληροφορίες σχετικά με τις αποθήκες δεδομένων και τα μεγάλα συστήματα δεδομένων. Το Azure Synapse Analytics συγκεντρώνει τις καλύτερες τεχνολογίες SQL που χρησιμοποιούνται στην αποθήκευση δεδομένων μεγάλων επιχειρήσεων, τις τεχνολογίες Spark που χρησιμοποιούνται για μεγάλα δεδομένα, το Data Explorer για ανάλυση σειρών καταγραφής και χρόνου, τις διοχέτευσης για ενοποίηση δεδομένων και το ETL/ELT, καθώς και την πλήρη ενοποίηση με άλλες υπηρεσίες Azure όπως το Power BI, το Cosmos DB και το AzureML.

Για περισσότερες πληροφορίες, δείτε την [Επισκόπηση Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Προϋποθέσεις

Πρέπει να πληρούνται οι παρακάτω προϋποθέσεις για να ρυθμίστε τη σύνδεση από Dynamics 365 Customer Insights σε Azure Synapse.

> [!IMPORTANT]
> Φροντίστε να ορίσετε όλες τις **αντιστοιχίσεις ρόλων** όπως περιγράφεται.  

## <a name="prerequisites-in-customer-insights"></a>Προϋποθέσεις στο Customer Insights

* Έχετε ρόλο **Διαχειριστή** στο Customer Insights. Μάθετε περισσότερα σχετικά με τα [δικαιώματα χρηστών στο Customer Insights](permissions.md#assign-roles-and-permissions).

Στο Azure: 

- Μια ενεργή συνδρομή Azure.

- Εάν χρησιμοποιείτε έναν νέο λογαριασμό Azure Data Lake Storage Gen2, η *αρχή υπηρεσίας για το Customer Insights* χρειάζεται δικαιώματα **συμβαλλόντος δεδομένων BLOB αποθήκευσης**. Μάθετε περισσότερα σχετικά με [τη σύνδεση σε ένα Azure Data Lake Storage με μια αρχή εξυπηρέτησης για το Customer Insights](connect-service-principal.md). Το Data Lake Storage Gen2 **πρέπει να έχει ενεργοποιημένο τον** [ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace).

- Στην ομάδα πόρων όπου βρίσκεται ο Azure Synapse workspace, η *αρχή υπηρεσίας* και ο *χρήστης για Customer Insights* χρειάζονται ανάθεση τουλάχιστον δικαιωμάτων **Αναγνώστη**. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Εκχώρηση ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal).

- Ο *χρήστης* χρειάζεται δικαιώματα **Συμβαλλόντος δεδομένων BLOB αποθήκευσης** στον λογαριασμό Azure Data Lake Storage Gen2 όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse. Μάθετε περισσότερα σχετικά με [τη χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Η *[διαχειριζόμενη ταυτότητα χώρου εργασίας Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* χρειάζεται δικαιώματα **χρειάζεται δικαιώματα** στο λογαριασμό Azure Data Lake Storage Gen2όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse. Μάθετε περισσότερα σχετικά για τη [χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Στο Azure Synapse workspace, η *αρχή υπηρεσίας για το Customer Insights* χρειάζεται την ανάθεση του ρόλου του **Διαχειριστή Synapse**. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Τρόπος ρύθμισης ελέγχου πρόσβασης για το χώρο εργασίας Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Σύνδεση σε βάσεις δεδομένων λίμνης δεδομένων στο Azure Synapse Analytics

1. Μεταβείτε στα **Δεδομένα** > **Προελεύσεις δεδομένων**.

1. Επιλέξτε **Προσθήκη προέλευσης δεδομένων**.

1. Επιλέξτε τη μέθοδο **Azure Synapse Analytics (Έκδοση προεπισκόπησης)**.

1. Δώστε ένα **Όνομα** για την προέλευση δεδομένων και επιλέξτε **Επόμενο** για να δημιουργήσετε την προέλευση δεδομένων. 

1. Επιλέξτε μια [διαθέσιμη σύνδεση](connections.md) to Azure Synapse Analytics ή δημιουργήστε μια νέα.

1. Επιλέξτε μια **Βάση δεδομένων λίμνης** από το χώρο εργασίας που είναι συνδεδεμένος στην επιλεγμένη σύνδεση του Azure Synapse Analytics και επιλέξτε **Επόμενο**.

1. Επιλέξτε τις οντότητες προς πρόσληψη από τη συνδεδεμένη βάση δεδομένων. 

1. Προαιρετικά, επιλέξτε τις οντότητες δεδομένων για να επιτρέψετε τη δημιουργία προφίλ δεδομένων. 

1. Επιλέξτε **Αποθήκευση** για να εφαρμόσετε την επιλογή σας και ξεκινήστε την πρόσληψη των δεδομένων από την προέλευση δεδομένων που μόλις δημιουργήσατε και που συνδέεται με τους πίνακες βάσης δεδομένων λίμνης στο Azure Synapse Analytics.
