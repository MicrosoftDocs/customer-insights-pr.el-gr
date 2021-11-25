---
title: Εξαγωγή δεδομένων του Customer Insights στο Omnisend
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5496efa075fa3474c579366d143ea55e86ec3995
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619028"
---
# <a name="export-segments-to-omnisend-preview"></a>Εξαγωγή τμημάτων στο Omnisend (έκδοση προεπισκόπησης)

Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Omnisend και χρησιμοποιήστε τα για δραστηριότητες μάρκετινγκ.

## <a name="prerequisites"></a>Προϋποθέσεις

-   Έχετε έναν [λογαριασμό Omnisend](https://www.omnisend.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή εκστρατείας.
-   Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.
-   Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Μπορείτε να εξαγάγετε έως και 1 εκ. προφίλ πελατών ανά εξαγωγή στο Omnisend και για να ολοκληρωθεί μπορεί να διαρκέσει έως και 4 ώρες.
- Η εξαγωγή στο Omnisend περιορίζεται σε τμήματα.
- Ο αριθμός των προφίλ πελατών που μπορείτε να εξαγάγετε στο Omnisend εξαρτάται από τη σύμβασή σας με το Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Ρύθμιση σύνδεσης στο Omnisend

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Omnisend** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Πληκτρολογήστε το [κλειδί API του Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.

1. Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Omnisend.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Omnisend. Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.

1. Στην ενότητα **Δεδομένα που αντιστοιχούν**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη. Απαιτείται για την εξαγωγή τμημάτων στο Omnisend. Προαιρετικά, μπορείτε να εξαγάγετε το Όνομα, το Επώνυμο, τη Διεύθυνση, τη Χώρα/Περιοχή, την Πολιτεία, την Πόλη και τον Ταχυδρομικό Κώδικα για να δημιουργήσετε πιο προσαρμοσμένα μηνύματα ηλεκτρονικού ταχυδρομείου. Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.

1. Επιλέξτε **Αποθήκευση**.

Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.

Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab). Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Απόρρητο δεδομένων και συμμόρφωση

Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο Omnisend, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα. Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το Omnisend θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε. Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.