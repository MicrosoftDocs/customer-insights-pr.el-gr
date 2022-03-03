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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350407"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Δυνατότητες ορίων εξυπηρέτησης στο Customer Insights

Σε αυτό το άρθρο περιγράφονται τα ενσωματωμένα όρια για την υπηρεσία Customer Insights, τα οποία έχουν σχεδιαστεί για να διασφαλιστεί η αξιοπιστία και η σταθερότητα της υπηρεσίας. Οποιεσδήποτε αιτήσεις για αλλαγές μπορούν να γίνουν μέσω του [Φόρουμ ιδεών](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Πληροφορίες κοινού

| Area  | Όρια  | Σημειώσεις |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Τμήματα αγοράς, μέτρα και προβλέψεις | 300  | Ο συνολικός αριθμός των [τμημάτων](audience-insights/segments.md), των [μέτρων](audience-insights/measures.md) και των [προβλέψεων](audience-insights/predictions.md) σε συνδυασμό, δεν μπορεί να υπερβαίνει τα 300.  |
| Σχέσεις | 20 επίπεδα βάθους στις σχέσεις μεταξύ των διαδρομών οντοτήτων. | Όταν δημιουργείτε [τμήματα](audience-insights/segments.md) ή [μέτρα](audience-insights/measures.md) χρησιμοποιώντας το περιβάλλον εργασίας του προγράμματος δημιουργίας, οι διαδρομές οντοτήτων μπορούν να έχουν έως και 20 μεταπηδήσεις σχέσης μεταξύ της οντότητας έναρξης και της οντότητας προορισμού.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
