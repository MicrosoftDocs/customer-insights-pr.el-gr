---
title: Όρια εξυπηρέτησης στο Dynamics 365 Customer Insights
description: Κατανοήστε τα όρια και τους περιορισμούς.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641762"
---
# <a name="service-limits-in-customer-insights"></a>Όρια εξυπηρέτησης στο Customer Insights

Σε αυτό το άρθρο περιγράφονται τα ενσωματωμένα όρια για την υπηρεσία Customer Insights, τα οποία έχουν σχεδιαστεί για να διασφαλιστεί η αξιοπιστία και η σταθερότητα της υπηρεσίας. Οποιεσδήποτε αιτήσεις για αλλαγές μπορούν να γίνουν μέσω του [Φόρουμ ιδεών](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Area  | Όρια  | Σημειώσεις |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Τμήματα αγοράς, μέτρα και προβλέψεις | 300  | Ο συνολικός αριθμός των [τμημάτων](segments.md), των [μέτρων](measures.md) και των [προβλέψεων](predictions.md) σε συνδυασμό, δεν μπορεί να υπερβαίνει τα 300.  |
| Σχέσεις | 20 επίπεδα βάθους στις σχέσεις μεταξύ των διαδρομών οντοτήτων. | Όταν δημιουργείτε [τμήματα](segments.md) ή [μέτρα](measures.md) χρησιμοποιώντας το περιβάλλον εργασίας του προγράμματος δημιουργίας, οι διαδρομές οντοτήτων μπορούν να έχουν έως και 20 μεταπηδήσεις σχέσης μεταξύ της οντότητας έναρξης και της οντότητας προορισμού.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
