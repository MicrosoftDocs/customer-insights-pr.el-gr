---
title: Σχήματα οντοτήτων σε Common Data Model
description: Εργασία με οντότητες στο Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183493"
---
# <a name="entity-schemas-in-common-data-model"></a>Σχήματα οντοτήτων σε Common Data Model

Το [Common Data Model](/common-data-model/) (CDM) είναι μια προδιαγραφή σε δήλωση και ένας ορισμός τυπικών οντοτήτων που αντιπροσωπεύουν κοινώς χρησιμοποιούμενες έννοιες και δραστηριότητες για διάφορους τομείς επιχειρήσεων και παραγωγικότητας. Αυτό το μοντέλο επεκτείνεται σε δεδομένα παρατήρησης και ανάλυσης επίσης. Το Common Data Model προσφέρει καλά ορισμένες, αρθρωτές και επεκτάσιμες επιχειρηματικές οντότητες, όπως Λογαριασμός, Επιχειρηματική μονάδα, Υπόμνημα, Επαφή, Υποψήφιος πελάτης, Ευκαιρία, και Προϊόν, καθώς και αλληλεπιδράσεις και σχέσεις μεταξύ προμηθευτών, εργαζόμενων και πελατών, όπως οι δραστηριότητες και οι συμβάσεις παροχής υπηρεσιών. Ο καθένας μπορεί να αναπτύξει και να επεκτείνει ορισμούς Common Data Model για να αποτυπώσει πρόσθετες ιδέες για συγκεκριμένες επιχειρήσεις.

Πρόκειται για ένα μοντέλο κοινόχρηστων δεδομένων που επιτρέπει την ευκολότερη συνεργασία των εφαρμογών και των ολοκληρωμένων δεδομένων, παρέχοντας έναν ενοποιημένο ορισμό των δεδομένων. Το Common Data Model περιλαμβάνει ένα εμπλουτισμένο σύστημα μεταδεδομένων με τυπικές οντότητες, σχέσεις, ιεραρχίες, χαρακτηριστικά και πολλά άλλα. Προήλθε από εφαρμογές Dynamics 365 και είναι ανοιχτού κώδικα στο GitHub με πάνω από 260 τυπικές οντότητες. Ένα μεγάλο σύστημα εσωτερικών και εξωτερικών συνεργατών συμβάλλει στις συγκεκριμένες έννοιες της βιομηχανίας στο Common Data Model.

Πολλά συστήματα και πλατφόρμες υλοποιούν σήμερα το Common Data Model, συμπεριλαμβανομένων ροών δεδομένων Power BI και υπηρεσιών δεδομένων Azure. Υποστηρίζεται ήδη στις υπηρεσίες δεδομένων Microsoft Dataverse, Dynamics 365, Power Apps, Power BI και στις επερχόμενες υπηρεσίες δεδομένων Azure, οι οποίες θα παρέχονται απευθείας στην [Πρωτοβουλία ανοιχτών δεδομένων](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>Σχήματα οντοτήτων Customer Insights

Για να δημιουργήσετε μια προβολή 360 μοιρών του πελάτη και να καταστήσετε τα μοντέλα Customer Insights διαθέσιμα σε ένα Common Data Model για επεκτασιμότητα, έχουμε δημοσιεύσει τα παρακάτω σχήματα οντοτήτων:

| Οντότητα | Περιγραφή |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Μια δραστηριότητα που εκτελείται από ένα χρήστη ο οποίος έχει αξία παρατήρησης για την επιχείρηση. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Ένα άτομο ή ένας οργανισμός που έχει εκτελέσει ή έχει τη δυνατότητα να εμπλακεί σε μια επιχειρηματική δραστηριότητα. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Ορισμός των KPI που έχει διαχωριστεί με μηδέν ή περισσότερες διαστάσεις (π.χ. μηνιαίοι ενεργοί χρήστες, Σύνολο δαπανών ανά πελάτη, μέση αξία κτήσης πελάτη) |
|[Τμήμα](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Προσδιορίζει μια ομάδα μελών με κοινά χαρακτηριστικά. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Μέλη που συμμετέχουν σε ένα δεδομένο τμήμα αγοράς. |

Για περισσότερες πληροφορίες, ανατρέξτε στην τεκμηρίωση σχετικά με τα [σχήματα οντοτήτων Customer Insights στο Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Προβολή οντοτήτων χρησιμοποιώντας τον πλοηγό οντότητας του Common Data Model

Προβολή οντοτήτων στο [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). Επιλέξτε μια οντότητα από την ενότητα "Πληροφορίες εφαρμογής" για να λάβετε τη λίστα των οντοτήτων στο Customer Insights και τους ορισμούς τους.

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="Πλοηγός οντότητας CDM που δείχνει την οντότητα CustomerActivity.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]