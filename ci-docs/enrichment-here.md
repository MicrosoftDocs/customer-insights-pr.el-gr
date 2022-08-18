---
title: Εμπλουτισμός προφίλ πελατών με τη HERE Technologies (έκδοση προεπισκόπησης)
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτου μέρους της HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237858"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Εμπλουτισμός προφίλ πελατών με τη HERE Technologies (έκδοση προεπισκόπησης)

Η HERE Technologies είναι μια εταιρεία πλατφόρμας θέσης η οποία παρέχει δεδομένα και υπηρεσίες με επίκεντρο την τοποθεσία. Οι υπηρεσίες εμπλουτισμού δεδομένων της HERE Technologies βελτιώνουν την ακρίβεια των πληροφοριών θέσης για τους πελάτες σας. Παρέχει ομαλοποίηση διευθύνσεων, εξαγωγή γεωγραφικού πλάτους και γεωγραφικού μήκους και πολλά άλλα.

## <a name="prerequisites"></a>Προϋποθέσεις

- Μια ενεργή συνδρομή στη HERE Technologies. Για να λάβετε μια συνδρομή, [εγγραφείτε εδώ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ή [επικοινωνήστε απευθείας με την HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Μάθετε περισσότερα σχετικά με τον εμπλουτισμό τοποθεσίας της HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Μια [σύνδεση HERE](connections.md) [διαμορφώνεται](#configure-the-connection-for-here-technologies) από έναν διαχειριστή.

## <a name="configure-the-connection-for-here-technologies"></a>Ρύθμιση της σύνδεσης για τη HERE Technologies

Θα πρέπει να είστε [διαχειριστής](permissions.md#admin) στο Customer Insights και να έχετε ένα ενεργό κλειδί API της HERE Technologies.

1. Επιλέξτε **Προσθήκη σύνδεσης** κατά τη ρύθμιση παραμέτρων ενός εμπλουτισμού ή μεταβείτε στο **Διαχειριστής** > **Συνδέσεις** και επιλέξτε **Ρύθμιση** στο πλακίδιο HERE technologies.

1. Πληκτρολογήστε ένα όνομα για τη σύνδεση και ένα έγκυρο κλειδί API HERE Technologies.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων και, στη συνέχεια, επιλέξτε **Αποθήκευση**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Σελίδα ρύθμισης παραμέτρων σύνδεσης HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Ρύθμιση παραμέτρων του εμπλουτισμού

1. Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.

1. Επιλέξτε **Εμπλουτίστε τα δεδομένα μου** από το **Τοποθεσία** από το πλακίδιο HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Πλακίδιο HERE Technologies.":::

1. Επισκοπήστε τη σύνοψη και έπειτα επιλέξτε **Επόμενο**.

1. Επιλέξτε τη σύνδεση. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε **Σύνολο δεδομένων πελάτη** και επιλέξτε το προφίλ ή τμήμα που θέλετε να εμπλουτίσετε με δεδομένα από τη HERE Technologies. Η οντότητα *Πελάτης* εμπλουτίζει όλα τα προφίλ πελατών σας ενώ ένα τμήμα εμπλουτίζει μόνο τα προφίλ πελατών που περιέχονται σε αυτό το τμήμα.

1. Καθορίστε τον τύπο των πεδίων από τα ενοποιημένα προφίλ σας που θα χρησιμοποιήσετε για αντιστοίχιση: την κύρια ή/και τη δευτερεύουσα διεύθυνση. Μπορείτε να καθορίσετε μια αντιστοίχιση πεδίων και για τις δύο διευθύνσεις και να εμπλουτίσετε τα προφίλ και για τις δύο διευθύνσεις ξεχωριστά. Για παράδειγμα, για μια διεύθυνση οικίας και μια διεύθυνση επιχείρησης. Επιλέξτε **Επόμενο**.

1. Αντιστοιχίστε τα πεδία σας στα δεδομένα της HERE Technologies. Τα πεδία **Οδός 1** και **Ταχυδρομικός Κώδικας** είναι απαραίτητα για την επιλεγμένη κύρια ή/και δευτερεύουσα διεύθυνση. Για μεγαλύτερη ακρίβεια αντιστοίχισης, προσθέστε περισσότερα πεδία.

1. Επιλέξτε **Επόμενο** για να ολοκληρώσετε την αντιστοίχιση πεδίων.

1. Δώστε ένα **όνομα** για τον εμπλουτισμό και για την **Όνομα οντότητας εξόδου**.

1. Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.

1. Επιλέξτε **Εκτέλεση** για να ξεκινήσει η διεργασία εμπλουτισμού ή κλείσιμο για επιστροφή στη σελίδα **Εμπλουτισμός**.

## <a name="view-enrichment-results"></a>Προβολή αποτελεσμάτων εμπλουτισμού

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Ο **Αριθμός πελατών που εμπλουτίζονται ανά πεδίο** παρέχει μια λεπτομερή έρευνα στην κάλυψη κάθε εμπλουτισμένου πεδίου.

## <a name="next-steps"></a>Επόμενα βήματα

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
