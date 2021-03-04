---
title: Σχήματα οντότητας Customer Insights στο Common Data Model
description: Εργασία με οντότητες στο Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269284"
---
# <a name="entity-schemas-in-common-data-model"></a>Σχήματα οντοτήτων σε Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Το [Common Data Model](https://docs.microsoft.com/common-data-model/) (CDM) είναι μια προδιαγραφή σε δήλωση και ένας ορισμός τυπικών οντοτήτων που αντιπροσωπεύουν κοινώς χρησιμοποιούμενες έννοιες και δραστηριότητες για διάφορους τομείς επιχειρήσεων και παραγωγικότητας. Αυτό το μοντέλο επεκτείνεται σε δεδομένα παρατήρησης και ανάλυσης επίσης. Το Common Data Model προσφέρει καλά ορισμένες, αρθρωτές και επεκτάσιμες επιχειρηματικές οντότητες, όπως Λογαριασμός, Επιχειρηματική μονάδα, Υπόμνημα, Επαφή, Υποψήφιος πελάτης, Ευκαιρία, και Προϊόν, καθώς και αλληλεπιδράσεις και σχέσεις μεταξύ προμηθευτών, εργαζόμενων και πελατών, όπως οι δραστηριότητες και οι συμβάσεις παροχής υπηρεσιών. Ο καθένας μπορεί να αναπτύξει και να επεκτείνει ορισμούς Common Data Model για να αποτυπώσει πρόσθετες ιδέες για συγκεκριμένες επιχειρήσεις.

Πρόκειται για ένα μοντέλο κοινόχρηστων δεδομένων που επιτρέπει την ευκολότερη συνεργασία των εφαρμογών και των ολοκληρωμένων δεδομένων, παρέχοντας έναν ενοποιημένο ορισμό των δεδομένων. Το Common Data Model περιλαμβάνει ένα εμπλουτισμένο σύστημα μεταδεδομένων με τυπικές οντότητες, σχέσεις, ιεραρχίες, χαρακτηριστικά και πολλά άλλα. Προήλθε από εφαρμογές Dynamics 365 και είναι ανοιχτού κώδικα στο GitHub με πάνω από 260 τυπικές οντότητες. Ένα μεγάλο σύστημα εσωτερικών και εξωτερικών συνεργατών συμβάλλει στις συγκεκριμένες έννοιες της βιομηχανίας στο Common Data Model.

Πολλά συστήματα και πλατφόρμες υλοποιούν σήμερα το Common Data Model, συμπεριλαμβανομένων των ροών δεδομένων Power BI και των υπηρεσιών δεδομένων Azure. Υποστηρίζεται στα Common Data Service, Dynamics 365, Power Apps, Power BI και σε προσεχείς υπηρεσίες δεδομένων Azure που συγκεντρώνει άμεσα την τιμή προς την [πρωτοβουλία ανοιχτών δεδομένων](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Σχήματα οντοτήτων Customer Insights

Για να δημιουργήσετε μια προβολή 360 μοιρών του πελάτη και να καταστήσετε τα μοντέλα Customer Insights διαθέσιμα σε ένα Common Data Model για επεκτασιμότητα, έχουμε δημοσιεύσει τα παρακάτω σχήματα οντοτήτων:

| Οντότητα | Περιγραφή |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Μια δραστηριότητα που εκτελείται από ένα χρήστη ο οποίος έχει αξία παρατήρησης για την επιχείρηση. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Ένα άτομο ή ένας οργανισμός που έχει εκτελέσει ή έχει τη δυνατότητα να εμπλακεί σε μια επιχειρηματική δραστηριότητα. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Ορισμός των KPI που έχει διαχωριστεί με μηδέν ή περισσότερες διαστάσεις (π.χ. μηνιαίοι ενεργοί χρήστες, Σύνολο δαπανών ανά πελάτη, μέση αξία κτήσης πελάτη) |
|[Τμήμα](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Προσδιορίζει μια ομάδα μελών με κοινά χαρακτηριστικά. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Μέλη που συμμετέχουν σε ένα δεδομένο τμήμα αγοράς. |

Για περισσότερες πληροφορίες, ανατρέξτε στην τεκμηρίωση σχετικά με τα [σχήματα οντοτήτων Customer Insights στο Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Προβολή οντοτήτων χρησιμοποιώντας τον πλοηγό οντότητας του Common Data Model

Μπορείτε να προβάλετε οντότητες στον [Πλοηγό οντοτήτων του Common Data Model](https://microsoft.github.io/CDM/). Επιλέξτε **Φόρτωση από GitHub!** και μεταβείτε στα **foundationCommon** > **crmCommon** > **λύσεις** > **customerInsights** όπου θα βρείτε τη λίστα με τις οντότητες Customer Insights και τους ορισμούς τους.
> [!div class="mx-imgBorder"]
> ![Πλοηγός οντότητας CDM που δείχνει οντότητα CustomerActivity](media/CDM-entity-navigator.png "Πλοηγός οντότητας CDM που δείχνει οντότητα CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]