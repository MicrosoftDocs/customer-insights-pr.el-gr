---
title: Εξαγωγή δεδομένων Customer Insights στο Google Ads
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568442"
---
# <a name="connector-for-google-ads-preview"></a>Σύνδεση για το Google Ads (προεπισκόπηση)

Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στη λίστα κοινού του Google Ads και χρησιμοποιήστε τα για διαφήμιση στο Google Search, Gmail, YouTube και Google Display Network. 

## <a name="prerequisites"></a>Προϋποθέσεις

-   Έχετε έναν [λογαριασμό Google Ads](https://ads.google.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.
-   Υπάρχουν υπάρχοντα κοινά στο Google Ads και στα αντίστοιχα αναγνωριστικά. Για περισσότερες πληροφορίες, ανατρέξτε στα [ακροατήρια Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Έχετε [ρυθμίσει τμήματα](segments.md)
-   Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν πεδία που αντιπροσωπεύουν μια διεύθυνση ηλεκτρονικού ταχυδρομείου, όνομα και επώνυμο

## <a name="connect-to-google-ads"></a>Σύνδεση στο Google Ads

1. Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στο **Google Ads**, επιλέξτε **Ρύθμιση**.

1. Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.

1. Εισαγάγετε το **[αναγνωριστικό πελάτη Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Καταγράψτε το **[διακριτικό προγραμματιστή που ενέκρινε το Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.

1. Πληκτρολογήστε το **[αναγνωριστικό κοινού Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** και επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση με το Google Ads.

1. Επιλέξτε **Έλεγχος ταυτότητας με το Google Ads** και δώστε τα διαπιστευτήρια Google Ads.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Εξαγωγή στιγμιότυπου οθόνης για σύνδεση Google Ads":::

1. Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.

## <a name="configure-the-connector"></a>Ρυθμίστε τις παραμέτρους της σύνδεσης

1. Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη. Επαναλάβετε τα ίδια βήματα για τα πεδία **'Ονομα** και **Επώνυμο**.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε. Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Google Ads.

1. Επιλέξτε **Αποθήκευση**.

## <a name="export-the-data"></a>Εξαγωγή δεδομένων

Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab). Στο Google Ads, μπορείτε πλέον να βρείτε τα τμήματά σας στα [ακροατήρια Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Έως 1000000 προφίλ ανά εξαγωγή στο Google Ads.
- Η εξαγωγή στο Google Ads περιορίζεται σε τμήματα.
- Η εξαγωγή τμημάτων με συνολικά 1 εκατομμύριο προφίλ μπορεί να διαρκέσει έως και πέντε λεπτά λόγω περιορισμών από την πλευρά του παρόχου. 
- Η αντιστοίχιση στο Google Ads μπορεί να διαρκέσει έως και 48 ώρες.

## <a name="data-privacy-and-compliance"></a>Απόρρητο δεδομένων και συμμόρφωση

Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Google Ads, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα. Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Google Ads πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε. Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.
