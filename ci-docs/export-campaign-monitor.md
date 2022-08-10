---
title: Εξαγωγή τμημάτων στο Campaign Monitor (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196302"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Εξαγωγή τμημάτων στο Campaign Monitor (έκδοση προεπισκόπησης)

Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Campaign Monitor και χρησιμοποιήστε τα για δραστηριότητες μάρκετινγκ.

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [Λογαριασμός Campaign Monitor](https://www.campaignmonitor.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.
- Ένα [Αναγνωριστικό λίστας Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Ένα [Δημιουργημένο κλειδί API](https://www.campaignmonitor.com/api/getting-started/) από τις **Ρυθμίσεις λογαριασμού** στο Campaign Monitor για να αποκτήσετε το αναγνωριστικό λίστας API.
- [Διαμορφωμένα τμήματα](segments.md) στο Customer Insights.
- Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Έως 1 εκατομμύριο προφίλ πελατών ανά εξαγωγή στο Campaign Monitor, η ολοκλήρωση των οποίων μπορεί να διαρκέσει έως και 20 λεπτά. Ο αριθμός των προφίλ πελατών που μπορείτε να εξαγάγετε στο Campaign Monitor εξαρτάται από το συμβόλαιό σας με το Campaign Monitor.
- Μόνο τμήματα.

## <a name="set-up-connection-to-campaign-monitor"></a>Ρύθμιση σύνδεσης στο Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Campaign Monitor**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Campaign Monitor.

1. Επιλέξτε **Έλεγχος ταυτότητας με το Campaign Monitor** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Campaign Monitor.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Campaign Monitor. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Εισάγετε **Αναγνωριστικό λίστας Campaign Monitor**.

1. Στην ενότητα **Δεδομένα που αντιστοιχούν**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη. Απαιτείται η εξαγωγή τμημάτων στο Campaign Monitor.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
