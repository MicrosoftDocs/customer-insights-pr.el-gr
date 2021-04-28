---
title: Εξαγωγή δεδομένων του Customer Insights στο Snapchat
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760535"
---
# <a name="export-segment-lists-to-snapchat-preview"></a>Εξαγωγή λιστών τμημάτων στο Snapchat (έκδοση προεπισκόπησης)

Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Snapchat και χρησιμοποιήστε τα για διαφήμιση. 

## <a name="prerequisites-for-a-connection"></a>Προϋποθέσεις για μια σύνδεση

-   Έχετε έναν [επιχειρηματικό λογαριασμό Snapchat](https://business.snapchat.com/), έναν [διαφημιστικό λογαριασμό Snapchat ](https://ads.snapchat.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.
-   Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.
-   Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Η εξαγωγή στο Snapchat περιορίζεται σε τμήματα.
- Η εξαγωγή έως 1 εκατομμυρίων προφίλ στο Snapchat μπορεί να χρειαστεί έως και 15 λεπτά για να ολοκληρωθεί. 

## <a name="set-up-connection-to-snapchat"></a>Ρύθμιση σύνδεσης στο Snapchat

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Snapchat** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.

1. Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Snapchat.

1. Επιλέξτε **Έλεγχος ταυτότητας με το Snapchat** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Snapchat. 

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Snapchat. Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.

1. Πληκτρολογήστε το [**αναγνωριστικό κοινού Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη. Απαιτείται η εξαγωγή τμημάτων στο Snapchat.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε. 

1. Επιλέξτε **Αποθήκευση**.

Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.

Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab). Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Απόρρητο δεδομένων και συμμόρφωση

Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο Snapchat, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα. Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το Snapchat θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε. Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.