---
title: Εξαγωγή τμημάτων στο ActiveCampaign
description: Μάθετε πώς να ρυθμίζετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725400"
---
# <a name="export-segments-to-activecampaign-preview"></a>Εξαγωγή τμημάτων στο ActiveCampaign (έκδοση προεπισκόπησης)

Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο ActiveCampaign και χρησιμοποιήστε τα για δραστηριότητες μάρκετινγκ.

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [λογαριασμός ActiveCampaign](https://www.activecampaign.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.
- Ένα [Αναγνωριστικό λίστας ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Ένα [Κλειδί API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) και REST Endpoint Hostname.
- [Διαμορφωμένα τμήματα](segments.md) στο Customer Insights.
- Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Η ιδιωτική σύνδεση σε συνδυασμό με το Φέρτε τον δικό σας χώρο αποθήκευσης (BYOS) δεν υποστηρίζεται.
- Έως και 1 εκατομμύριο προφίλ πελατών ανά εξαγωγή στο ActiveCampaign, η ολοκλήρωση των οποίων μπορεί να διαρκέσει έως και 90 λεπτά. Ο αριθμός των προφίλ πελατών που μπορείτε να εξαγάγετε στο ActiveCampaign εξαρτάται από τη σύμβασή σας με το ActiveCampaign.
- Μόνο τμήματα.

## <a name="set-up-connection-to-activecampaign"></a>Ρυθμίστε τη σύνδεση στο ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **ActiveCampaign**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Πληκτρολογήστε το κλειδί API ActiveCampaign και το όνομα κεντρικού υπολογιστή τελικού σημείου REST. Το όνομα κεντρικού υπολογιστή τελικού σημείου REST είναι μόνο το όνομα κεντρικού υπολογιστή, χωρίς https://.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Σύνδεση** για να αρχικοποιήσετε τη σύνδεση.

1. Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα ActiveCampaign. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Εισάγετε **Αναγνωριστικό λίστας ActiveCampaign**.

1. Στην ενότητα **Δεδομένα που αντιστοιχούν**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.

1. Προαιρετικά, εξαγάγετε **Όνομα**, **Επίθετο**, και **Τηλέφωνο** για να δημιουργήσετε πιο εξατομικευμένα email. Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
