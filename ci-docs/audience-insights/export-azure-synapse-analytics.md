---
title: Εξαγωγή δεδομένων του Customer Insights στο Azure Synapse Analytics
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977377"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Εξαγωγή δεδομένων σε Azure Synapse Analytics (έκδοση προεπισκόπησης)

Το Azure Synapse είναι μια υπηρεσία ανάλυσης που επιταχύνει το χρόνο λήψης πληροφοριών σε αποθήκες δεδομένων και συστήματα μαζικών δεδομένων. Μπορείτε να συγκεντρώνετε και να χρησιμοποιείτε δεδομένα του Customer Insights στο [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Προϋποθέσεις

Πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις για τη ρύθμιση παραμέτρων της σύνδεσης από το Customer Insights στο Azure Synapse.

> [!NOTE]
> Φροντίστε να ορίσετε όλες τις **αντιστοιχίσεις ρόλων** όπως περιγράφεται.  

## <a name="prerequisites-in-customer-insights"></a>Προϋποθέσεις στο Customer Insights

* Έχετε τον ρόλο **Διαχειριστή** στις πληροφορίες κοινού. Μάθετε περισσότερα σχετικά με τον [ορισμό δικαιωμάτων χρήστη σε πληροφορίες κοινού](permissions.md#assign-roles-and-permissions)

Στο Azure: 

- Μια ενεργή συνδρομή Azure.

- Εάν χρησιμοποιείτε ένα νέο λογαριασμό Azure Data Lake Storage Gen2, η *κύρια υπηρεσία για πληροφορίες κοινού* χρειάζεται δικαιώματα **συμβαλλόντος δεδομένων BLOB αποθήκευσης**. Μάθετε περισσότερα σχετικά με τη [σύνδεση σε λογαριασμό Azure Data Lake Storage Gen2 με την κύρια υπηρεσία Azure για πληροφορίες κοινού](connect-service-principal.md). Το Data Lake Storage Gen2 **πρέπει να έχει ενεργοποιημένο τον** [ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace).

- Στην ομάδα πόρων βρίσκεται ο χώρος εργασίας Azure Synapse, στην *κύρια υπηρεσία* και στον *χρήστη για πληροφορίες κοινού* πρέπει να εκχωρηθούν τουλάχιστον δικαιώματα **Αναγνώστη**. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Εκχώρηση ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal).

- Ο *χρήστης* χρειάζεται δικαιώματα **Συμβαλλόντος δεδομένων BLOB αποθήκευσης** στον λογαριασμό Azure Data Lake Storage Gen2 όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse. Μάθετε περισσότερα σχετικά με [τη χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Η *[διαχειριζόμενη ταυτότητα χώρου εργασίας Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* χρειάζεται δικαιώματα **χρειάζεται δικαιώματα** στο λογαριασμό Azure Data Lake Storage Gen2όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse. Μάθετε περισσότερα σχετικά για τη [χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Στον χώρο εργασίας Azure Synapse, η *κύρια υπηρεσία για πληροφορίες κοινού* χρειάζεται να ανατεθεί ο ρόλος **Διαχειριστής Synapse**. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Τρόπος ρύθμισης ελέγχου πρόσβασης για το χώρο εργασίας Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Ρυθμίστε τη σύνδεση και κάντε εξαγωγή στο Azure Synapse

### <a name="configure-a-connection"></a>Ρύθμιση παραμέτρων μιας σύνδεσης

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** κι επιλέξτε **Azure Synapse Analytics** ή επιλέξτε **Ρύθμιση** στο πλακίδιο **Azure Synapse Analytics** για τη ρύθμιση παραμέτρων της σύνδεσης.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο Εμφανιζόμενο όνομα. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυτήν τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Επιλέξτε ή αναζητήστε τη συνδρομή στην οποία θέλετε να χρησιμοποιήσετε τα δεδομένα του Customer Insights. Μόλις επιλεγεί μια συνδρομή, μπορείτε επίσης να επιλέξετε **Χώρος εργασίας**, **Λογαριασμός χώρου αποθήκευσης** και **Περιέκτης**.

1. Επιλέξτε **Αποθήκευση** για να αποθηκεύσετε τη σύνδεση.

### <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα **Azure Synapse Analytics**. Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες [συνδέσεις](connections.md) αυτού του τύπου.

1. Παράσχετε ένα αναγνωρίσιμο **εμφανιζόμενο όνομα** για την εξαγωγή σας και ένα **όνομα βάσης δεδομένων**.

1. Επιλέξτε ποιες οντότητες θέλετε να εξαγάγετε στο Azure Synapse Analytics.

1. Επιλέξτε **Αποθήκευση**.

Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.

Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab). Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Ενημέρωση εξαγωγής

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Επεξεργασία** στην εξαγωγή που θέλετε να ενημερώσετε.

   - **Προσθέστε** ή **Καταργήστε** οντότητες από την επιλογή. Εάν οι οντότητες καταργηθούν από την επιλογή, δεν διαγράφονται από τη βάση δεδομένων Synapse Analytics. Ωστόσο, οι μελλοντικές ανανεώσεις δεδομένων δεν θα ενημερώσουν τις οντότητες που καταργήθηκαν σε αυτήν τη βάση δεδομένων.

   - Η **Αλλαγή του ονόματος βάσης δεδομένων** δημιουργεί μια νέα βάση δεδομένων Synapse Analytics. Η βάση δεδομένων με το όνομα που είχε ρυθμιστεί προηγουμένως δεν θα λαμβάνει ενημερώσεις σε μελλοντικές ανανεώσεις.