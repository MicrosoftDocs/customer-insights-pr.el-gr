---
title: Εμπλουτισμός εταιρικών προφίλ με την Dun & Bradstreet (έκδοση προεπισκόπησης)
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτων από την Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196026"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Εμπλουτισμός εταιρικών προφίλ με την Dun & Bradstreet (έκδοση προεπισκόπησης)

Η Dun & Bradstreet παρέχει εμπορικά δεδομένα, αναλύσεις και πληροφορίες για επιχειρήσεις. Δίνει τη δυνατότητα στους πελάτες με ενοποιημένα προφίλ πελατών για τις εταιρείες να εμπλουτίσουν τα δεδομένα τους. Οι εμπλουτισμοί περιλαμβάνουν χαρακτηριστικά όπως αριθμός DUNS, το μέγεθος της εταιρείας, η τοποθεσία, ο κλάδος και άλλα.

## <a name="prerequisites"></a>Προϋποθέσεις

- Μια ενεργή άδεια χρήσης [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Ενοποιημένα προφίλ πελατών](customer-profiles.md) για εταιρείες.
- Έχει ρυθμιστεί ένα [έργο](#set-up-your-dun--bradstreet-project) Dun & Bradstreet.
- Μια [σύνδεση](connections.md) Dun & Bradstreet [ρυθμίζεται](#configure-a-connection-for-dun--bradstreet) από διαχειριστή.

## <a name="set-up-your-dun--bradstreet-project"></a>Ρυθμίστε το δικό σας έργο Dun & Bradstreet

Ως κάτοχος άδειας χρήσης του Dun & Bradstreet, μπορείτε να ρυθμίσετε ένα έργο [στο Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Συνδεθείτε στο [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Για ανάκτηση διαπιστευτηρίων, [επαναφέρετε τον κωδικό πρόσβασής σας](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Πραγματοποιήστε λήψη [του αρχείου προτύπου csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) που θα χρησιμοποιηθεί για την αντιστοίχιση των πεδίων Customer Insights στα αντίστοιχα πεδία Dun & Bradstreet.

1. Φορτώστε το αρχείο στο βήμα **Αποστολής δεδομένων** της εμπειρίας δημιουργίας έργου Dun & Bradstreet.

1. Επιλέξτε τις οριζόντιες κουκκίδες κάτω από τη σχετική **προέλευση** στο πρόσφατα δημιουργημένο έργο Dun & Bradstreet για να δείτε τις διαθέσιμες επιλογές.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Στιγμιότυπο οθόνης με κουκκίδες σε ένα έργο Dun & Bradstreet.":::

1. Επιλέξτε **Λήψη λεπτομερειών S3**. Αποθηκεύστε αυτές τις πληροφορίες σε ασφαλές σημείο. Θα χρειαστεί να ρυθμίσετε [τη σύνδεση για τον εμπλουτισμό](#configure-a-connection-for-dun--bradstreet) σε Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Στιγμιότυπο οθόνης της επιλογής πληροφοριών s3 σε ένα έργο Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Ρύθμιση παραμέτρων σύνδεσης για Dun & Bradstreet

Πρέπει να είστε [διαχειριστής](permissions.md#admin) στο Customer Insights και να έχετε τα διαπιστευτήρια από το Dun & Bradstreet Connect.

1. Επιλέξτε **Προσθήκη σύνδεσης** κατά τη ρύθμιση παραμέτρων εμπλουτισμού ή μεταβείτε στην επιλογή **Διαχειριστής** > **Συνδέσεις** και επιλέξτε **Ρύθμιση** στο πλακίδιο Dun & Bradstreet.

1. Πληκτρολογήστε ένα όνομα για τη σύνδεση.

1. Δώστε έγκυρα διαπιστευτήρια Dun & Bradstreet και λεπτομέρειες έργου Dun & Bradstreet *Περιοχή, Απόθεση διαδρομής φακέλου και Όνομα φακέλου απόθεσης*. Αυτές [οι πληροφορίες προέρχονται](#set-up-your-dun--bradstreet-project) από το έργο Dun & Bradstreet.

1. Ελέγξτε και δώστε τη συγκατάθεσή σας για το [Απόρρητο δεδομένων και συμμόρφωση](#data-privacy-and-compliance) επιλέγοντας **Συμφωνώ**.

1. Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων και, στη συνέχεια, επιλέξτε **Αποθήκευση**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Σελίδα ρύθμισης παραμέτρων σύνδεσης για Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Απόρρητο δεδομένων και συμμόρφωση

Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα σε Dun & Bradstreet, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα. Η Microsoft θα μεταφέρει αυτά τα δεδομένα με βάση τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι η Dun & Bradstreet πληροί οποιεσδήποτε υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ίσως έχετε. Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ο διαχειριστής σας για το Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον εμπλουτισό ανά πάσα στιγμή, ώστε να διακοπεί η χρήση αυτής της λειτουργικότητας.

## <a name="supported-countries-or-regions"></a>Υποστηριζόμενες χώρες ή περιφέρειες

Προς το παρόν, υποστηρίζουμε τις ακόλουθες επιλογές χώρας/περιοχής: Καναδάς (Αγγλικά) ή Ηνωμένων Πολιτειών (Αγγλικά).

## <a name="configure-the-enrichment"></a>Ρύθμιση παραμέτρων του εμπλουτισμού

1. Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.

1. Επιλέξτε **Εμπλουτίστε τα δεδομένα μου** στο **Δεδομένα εταιρείας** για το πλακίδιο Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Στιγμιότυπο οθόνης του πλακιδίου Dun & Bradstreet.":::

1. Επισκοπήστε τη σύνοψη και έπειτα επιλέξτε **Επόμενο**.

1. Επιλέξτε τη σύνδεση και επιβεβαιώστε. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε **Σύνολο δεδομένων πελάτη** και επιλέξτε το προφίλ ή τμήμα που θέλετε να εμπλουτίσετε με δεδομένα εταιρείας από την Dun & Bradstreet. Η οντότητα *Πελάτης* εμπλουτίζει όλα τα προφίλ πελατών σας ενώ ένα τμήμα εμπλουτίζει μόνο τα προφίλ πελατών που περιέχονται σε αυτό το τμήμα.

1. Καθορίστε ποιος τύπος πεδίων από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιήστε για την αντιστοίχηση δεδομένων εταιρείας από την Dun & Bradstreet. Απαιτείται τουλάχιστον ένα από τα πεδία **Όνομα και διεύθυνση** μ **Τηλέφωνο** ή **Ηλεκτρονικό ταχυδρομείο**.

1. Επιλέξτε **Επόμενο**

1. Αντιστοιχίστε τα πεδία σας στα δεδομένα της εταιρείας από την Dun & Bradstreet. Απαιτούνται πεδία είτε **αριθμός DUNS** είτε **Όνομα εταιρείας** και **Χώρα**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Παράθυρο αντιστοίχισης πεδίων Dun & Bradstreet.":::

1. Επιλέξτε **Επόμενο** για να ολοκληρώσετε την αντιστοίχιση πεδίων.

1. Δώστε ένα **όνομα** για τον εμπλουτισμό και για την **Όνομα οντότητας εξόδου**.

1. Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.

1. Επιλέξτε **Εκτέλεση** για να ξεκινήσει η διεργασία εμπλουτισμού ή κλείσιμο για επιστροφή στη σελίδα **Εμπλουτισμός**.

## <a name="view-enrichment-results"></a>Προβολή αποτελεσμάτων εμπλουτισμού

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Επόμενα βήματα

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
