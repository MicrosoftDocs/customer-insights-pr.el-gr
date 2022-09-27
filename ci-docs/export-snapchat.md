---
title: Εξαγωγή τμημάτων στο Snapchat (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195382"
---
# <a name="export-segments-to-snapchat-preview"></a>Εξαγωγή τμημάτων στο Snapchat (έκδοση προεπισκόπησης)

Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Snapchat και χρησιμοποιήστε τα για διαφήμιση.

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [Επαγγελματικός λογαριασμός Snapchat](https://business.snapchat.com/), ένας [Λογαριασμός διαφημίσεων Snapchat](https://ads.snapchat.com/)και τα αντίστοιχα διαπιστευτήρια διαχειριστή. Πρέπει να είστε τουλάχιστον μέλος ενός λογαριασμού οργανισμού και διαχειριστής δεδομένων ενός συγκεκριμένου διαφημιστικού λογαριασμού.
- Τουλάχιστον ένα κοινό στον διαχειριστή Snapchat κοινού του τύπου SAM (Snap Audience Match).
- Το [Τμήμα Snapchat/Αναγνωριστικό κοινού](https://businesshelp.snapchat.com/s/article/custom-audiences). Το αναγνωριστικό του κοινού μπορείτε να το βρείτε στη διεύθυνση URL αφού επιλέξετε το κοινό στον υπεύθυνο κοινού Snapchat.
- [Διαμορφωμένα τμήματα](segments.md) στο Customer Insights.
- Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Έως 1 εκατομμύριο προφίλ πελατών, τα οποία μπορεί να χρειαστούν έως και 15 λεπτά για να ολοκληρωθούν.
- Μόνο τμήματα.

## <a name="set-up-connection-to-snapchat"></a>Ρύθμιση σύνδεσης στο Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Snapchat**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Σύνδεση** για να αρχικοποιήσετε τη σύνδεση.

1. Επιλέξτε **Έλεγχος ταυτότητας με το Snapchat** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Snapchat.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Snapchat. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Εισάγετε το **Τμήμα Snapchat/Αναγνωριστικό κοινού**.

1. Στην ενότητα **Δεδομένα που αντιστοιχούν**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]