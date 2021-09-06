---
title: Όρια εξυπηρέτησης
description: Κατανοήστε τα όρια και τους περιορισμούς.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034864"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Όρια εξυπηρέτησης στη δυνατότητα πληροφοριών κοινού του Dynamics 365 Customer Insights

Σε αυτό το άρθρο περιγράφονται τα ενσωματωμένα όρια για την υπηρεσία Customer Insights, τα οποία έχουν σχεδιαστεί για να διασφαλιστεί η αξιοπιστία και η σταθερότητα της υπηρεσίας. Οποιεσδήποτε αιτήσεις για αλλαγές μπορούν να γίνουν μέσω του [Φόρουμ ιδεών](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Περιοχή  | Όρια  | Σημειώσεις |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Τμήματα και μετρήσεις | 100 τμήματα ή μετρήσεις. | Ο συνολικός αριθμός ενεργών [τμημάτων](segments.md) και [μετρήσεων](measures.md) σε συνδυασμό δεν μπορεί να υπερβαίνει το 100.  |
| Σχέσεις | 20 επίπεδα βάθους στις σχέσεις μεταξύ των διαδρομών οντοτήτων. | Όταν δημιουργείτε [τμήματα](segments.md) ή [μέτρα](measures.md) χρησιμοποιώντας το περιβάλλον εργασίας του προγράμματος δημιουργίας, οι διαδρομές οντοτήτων μπορούν να έχουν έως και 20 μεταπηδήσεις σχέσης μεταξύ της οντότητας έναρξης και της οντότητας προορισμού.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]