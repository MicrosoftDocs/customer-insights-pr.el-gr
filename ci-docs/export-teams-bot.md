---
title: Bot του Teams για το Dynamics 365 Customer Insights (προεπισκόπηση)
description: Αναζητήστε ενοποιημένα προφίλ πελατών στο Microsoft Teams με τη βοήθεια ενός bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195842"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot του Teams για το Dynamics 365 Customer Insights (προεπισκόπηση)

Συνδεθείτε με το Microsoft Teams για να επιτρέψετε σε ένα bot να αναζητήσει ενοποιημένα προφίλ πελατών στα κανάλια Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot Teams που εμφανίζουν μια καρτέλα πελάτη":::

## <a name="prerequisites"></a>Προϋποθέσεις

- Τουλάχιστον [προστέθηκε μια πηγή δεδομένων](data-sources.md).
- Η [διαδικασία ενοποίησης](data-unification.md) να έχει ολοκληρωθεί.
- Τα πεδία προστίθενται στο [ευρετήριο αναζήτησης και φιλτραρίσματος](search-filter-index.md).
- Το Customer Insights και το Teams να βρίσκονται στον ίδιο οργανισμό.
- Το περιβάλλον σας έχει ορίσει το κύριο κοινό στόχο σε μεμονωμένους πελάτες. Οι επιχειρηματικοί λογαριασμοί δεν υποστηρίζονται.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Ρυθμίστε τις παραμέτρους του bot

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.
1. Στο πλακίδιο Microsoft Teams, επιλέξτε **Ρύθμιση**.
1. Θα ανακατευθυνθείτε στην περιοχή **Εφαρμογές** στο Teams. Μπορείτε, επίσης, να ανοίξετε το Teams και να επιλέξετε **Εφαρμογές** στην κάτω αριστερή γωνία ή [να το λάβετε από το AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) απευθείας.
1. Αναζητήστε το **Customer Insights** και επιλέξτε την εφαρμογή.
1. Επιλέξτε **Προσθήκη**.
1. Συνδεθείτε στο Customer Insights στο Teams. Εμφανίζεται ένα μήνυμα καλωσορίσματος.

## <a name="things-you-can-do-with-the-bot"></a>Πράγματα που μπορείτε να κάνετε με το bot

Το bot παρέχει δυνατότητες αναζήτησης για ενοποιημένα προφίλ πελατών.

- Εισάγετε **Αναζήτηση** ακολουθούμενο από όνομα, διεύθυνση ηλεκτρονικού ταχυδρομείου ή οποιοδήποτε άλλο πεδίο στο ενοποιημένο προφίλ πελάτη που προστίθεται στο ευρετήριο αναζήτησης και φίλτρου.

  Θα λάβετε μια κάρτα με έως και 15 πεδία από το προφίλ πελάτη που προκύπτει. Οι πολλαπλοί συνδυασμοί επιστρέφουν μια λίστα αποτελεσμάτων όπου μπορείτε να επιλέξετε ένα προφίλ. Για να αναζητήσετε μια ακριβή αντιστοίχιση, προσθέστε τον όρο αναζήτησης σε διπλά εισαγωγικά.

- Εάν ο οργανισμός σας διατηρεί πολλά περιβάλλοντα Customer Insights στον ίδιο οργανισμό, εισαγάγετε **switchinstance** για να επιλέξετε σε ποιο περιβάλλον θέλετε να συνδέσετε το bot.

- Εισάγετε **βοήθεια** για να δείτε μια λίστα με τις διαθέσιμες εντολές για το bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]