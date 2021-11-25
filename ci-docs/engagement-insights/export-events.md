---
title: Εξαγωγή συμβάντων που έχουν περιορισμό
description: Τρόπος συμβάντων με περιορισμό και συμβάντων βάσης.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606212"
---
# <a name="export-events"></a>Εξαγωγή συμβάντων

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ένα συμβάν αντιπροσωπεύει συμπεριφορά χρήστη. Καταγράφει πότε ένας χρήστης εμφανίζει μια σελίδα (προβολή συμβάντος) ή αλληλεπιδρά με περιεχόμενο (συμβάν ενέργειας). Όταν μπορείτε να αποφασίσετε ποιες ιδιότητες των δεδομένων θέλετε να εμφανίζονται σε μια αναφορά, αυτή η εικονική προβολή των δεδομένων ονομάζεται *περιορισμένο συμβάν*. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και τροποποίηση συμβάντων](refined-events.md).

- Μπορείτε να εξαγάγετε συμβάντα και περιορισμένα συμβάντα στον εξωτερικό χώρο αποθήκευσης. 
- Οι εξαγωγές είναι μια πρόσθια ροή δεδομένων. Δεν μπορείτε να αναπληρώσετε τη ροή. 
- Οι εξαγωγές έχουν σταθερά σχήματα. Εάν προσθέσετε προσαρμοσμένες ιδιότητες σε ένα συμβάν, δεν θα συμπεριληφθούν. Θα χρειαστεί να δημιουργήσετε μια νέα εξαγωγή.

## <a name="prerequisites"></a>Προϋποθέσεις

Πριν ρυθμίσετε μια εξαγωγή, θα πρέπει να αποκτήσετε πρόσβαση και μια ενεργή συνδρομή στην πύλη Azure. Θα χρειαστείτε τις πληροφορίες του λογαριασμού χώρου αποθήκευσης κατά τη διαδικασία εξαγωγής. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Δημιουργία λογαριασμού Azure Data Lake Storage Gen 2

1. Πραγματοποιήστε είσοδο στην πύλη Azure και [δημιουργήστε έναν νέο λογαριασμό χώρου αποθήκευσης](/azure/storage/common/storage-account-create). 

1. Βεβαιωθείτε ότι έχετε ενεργοποιήσει τον **Ιεραρχικό χώρο ονομάτων** στην καρτέλα **Για προχωρημένους**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Ενεργοποίηση ιεραρχικού χώρου ονομάτων στην καρτέλα για προχωρημένους.":::

1. Μόλις αναπτυχθεί, μεταβείτε στο λογαριασμό χώρου αποθήκευσης που μόλις δημιουργήθηκε. Στο τμήμα παραθύρου περιήγησης επιλέξτε **Ρυθμίσεις** > **Κλειδιά πρόσβασης**. 

1. Αντιγράψτε τα στοιχεία **Όνομα λογαριασμού** και **Κλειδί** για να τα χρησιμοποιήσετε κατά τη δημιουργία μιας νέας εξαγωγής.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Κλειδιά πρόσβασης σε έναν λογαριασμό χώρου αποθήκευσης.":::

## <a name="export-events"></a>Εξαγωγή συμβάντων

Υπάρχουν δύο τρόποι για να εμφανιστεί το παράθυρο διαλόγου **Εξαγωγή συμβάντων**: 
- Μεταβείτε στην επιλογή **Δεδομένα** > **Εξαγωγές** και επιλέξτε **Νέα εξαγωγή**.
- Μεταβείτε στο **Δεδομένα** > **Συμβάντα**, επιλέξτε **Περισσότερα [...]** δίπλα από το συμβάν που θέλετε να εξαγάγετε και επιλέξτε **Εξαγωγή** από το αναπτυσσόμενο μενού. 

:::image type="content" source="media/new-export.png" alt-text="Δημιουργία νέας εξαγωγής.":::

Θα λάβετε καθοδήγηση στα βήματα δημιουργίας εξαγωγής:

1. Δώστε ένα **όνομα εξαγωγής** και, στη συνέχεια, επιλέξτε **Επόμενο**.

1. Στην αναπτυσσόμενη λίστα **Επιλογή συμβάντων**, επιλέξτε τα βασικά συμβάντα και τα πιο συγκεκριμένα συμβάντα που θα συμπεριληφθούν στην εξαγωγή. 

1. Στην ενότητα **Δομής αρχείου**, επιλέξτε τον ρυθμό (ωριαίο ή καθημερινό) για να δημιουργήσετε νέα αρχεία στον χώρο αποθήκευσης προορισμού και, στη συνέχεια, επιλέξτε **Επόμενο**. Τα συμβάντα εξαγάγονται συνεχώς καθώς φθάνουν.

1. Στο παράθυρο διαλόγου **Επιλογή μορφής**, επιλέξτε τη μορφή για την εξαγωγή σας. Επιλέξτε μεταξύ των μορφών **Κοινό μοντέλο δεδομένων**, **CSV** και **JSON**. Για να χρησιμοποιήσετε την εξαγωγή με άλλες εφαρμογές Dynamics 365, συνιστούμε τη μορφή **κοινού μοντέλου δεδομένων**.

1. Στο παράθυρο διαλόγου **Επιλογή προορισμού**, καθορίστε την τοποθεσία Azure Data Lake Storage Gen 2.
    1. **Το όνομα λογαριασμού ADLS Gen 2** είναι το όνομα του λογαριασμού χώρου αποθήκευσης στον οποίο θέλετε να αποθηκεύσετε την εξαγωγή. 
    1. Η **Διαδρομή φακέλου** καθορίζει πού θα πρέπει να αποθηκευτεί η εξαγωγή στο σύστημα αρχείων και στη δομή καταλόγου του λογαριασμού χώρου αποθήκευσης.
    1. Το **Κοινόχρηστο κλειδί** είναι διαθέσιμο από την πύλη Azure για το λογαριασμό χώρου αποθήκευσης.

1. Ελέγξτε και επιβεβαιώστε τις επιλογές σας για ολοκλήρωση.

## <a name="view-and-manage-exports"></a>Προβολή και διαχείριση εξαγωγών

Αφού ρυθμίσετε μια εξαγωγή, μεταβείτε στην επιλογή **Δεδομένα** > **Εξαγωγές** για να την προβάλετε. Επιλέξτε **Περισσότερα [...]** για κάθε υφιστάμενη αναφορά για να την επεξεργαστείτε ή να τη διαγράψετε.


[!INCLUDE[footer-include](../includes/footer-banner.md)]