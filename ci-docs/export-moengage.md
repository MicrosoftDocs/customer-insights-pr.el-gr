---
title: Εξαγωγή τμημάτων στο MoEngage
description: Μάθετε πώς να διαμορφώνετε τη σύνδεση και να κάνετε εξαγωγή στο MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199118"
---
# <a name="export-segments-to-moengage-preview"></a>Εξαγωγή τμημάτων στο MoEngage (προεπισκόπηση)

Εξάγετε τμήματα ενοποιημένων προφίλ πελατών στο MoEngage και χρησιμοποιήστε τα για email marketing στο MoEngage.

## <a name="prerequisites-for-a-connection"></a>Προϋποθέσεις για μια σύνδεση

- [Λογαριασμός MoEngage](https://www.moengage.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.
- Πλήκτρο MoEngage API από τις Ρυθμίσεις > API στο MoEngage.
- [Διαμορφωμένα τμήματα](segments.md) στο Customer Insights.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Έως 100.000 προφίλ πελατών ανά εξαγωγή στο MoEngage, τα οποία μπορεί να διαρκέσουν έως και 15 λεπτά. Ο αριθμός των προφίλ πελατών που μπορείτε να εξαγάγετε στο MoEngage εξαρτάται από το συμβόλαιό σας με το MoEngage.
- Μόνο τμήματα.

## <a name="set-up-connection-to-moengage"></a>Ρυθμίστε τη σύνδεση στο MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **MoEngage** για να διαμορφώσετε τη σύνδεση.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εισάγετε [Αναγνωριστικό API δεδομένων MoEngage και κλειδί API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Σύνδεση** για να αρχικοποιήσετε τη σύνδεση στο MoEngage.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα MoEngage. Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.

1. Στην ενότητα **Δεδομένα που αντιστοιχούν**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη. Επαναλάβετε τα ίδια βήματα για άλλα προαιρετικά πεδία.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε. Θα δημιουργήσουμε ένα ή περισσότερα τμήματα με το ίδιο όνομα με τα επιλεγμένα τμήματα στο MoEngage υπό το **Τμήματα** > **Προσαρμοσμένα τμήματα**.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]