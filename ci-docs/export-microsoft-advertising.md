---
title: Εξαγωγή τμημάτων στο Microsoft Advertising (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196532"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Εξαγωγή τμημάτων στο Microsoft Advertising (έκδοση προεπισκόπησης)

Εξαγάγετε τμήματα του Customer Insights στο Microsoft Advertising για να δημιουργήσετε κοινά Customer Match. Χρησιμοποιήστε αυτά τα κοινά για τις διαφημιστικές εκστρατείες σας.

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [Λογαριασμός Microsoft Advertising](https://ads.microsoft.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.
- Αναγνωριστικό πελάτη Microsoft Advertising και Αναγνωριστικό λογαριασμού. Βρείτε το αναγνωριστικό πελάτη (`cid`) και αναγνωριστικό λογαριασμού (`aid`) στις παραμέτρους της διεύθυνσης URL όταν είστε συνδεδεμένοι στο Microsoft Advertising.
- Οι όροι χρήσης του Customer Match γίνονται αποδεκτοί.
- [Διαμορφωμένα τμήματα](segments.md) στο Customer Insights.
- Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Έως 500.000 προφίλ πελατών ανά εξαγωγή στο Microsoft Advertising, τα οποία μπορεί να διαρκέσουν έως και 10 λεπτά.
- Μόνο τμήματα.

## <a name="set-up-connection-to-microsoft-advertising"></a>Ρυθμίστε τη σύνδεση με το Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Microsoft Advertising**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Η προεπιλογή είναι "διαχειριστές". Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εισάγετε το **Αναγνωριστικό πελάτη Microsoft Advertising**.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Σύνδεση** για να αρχικοποιήσετε τη σύνδεση.

1. Επιλέξτε **Έλεγχος ταυτότητας με το Microsoft Advertising** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Microsoft Advertising.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Microsoft Advertising. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Επιλέξτε τα τμήματα για εξαγωγή. Τα κοινά Customer Match στο Microsoft Advertising δημιουργούνται αυτόματα με το όνομα των τμημάτων που έχουν επιλεγεί για εξαγωγή. Κάθε τμήμα θα έχει ως αποτέλεσμα ένα ξεχωριστό κοινό Customer Match.

1. Πληκτρολογήστε το **Αναγνωριστικό πελάτη Microsoft Αdvertising και το αναγνωριστικό λογαριασμού**.

1. Στην ενότητα **Δεδομένα που αντιστοιχούν**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο με τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
