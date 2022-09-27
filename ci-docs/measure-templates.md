---
title: Δημιουργία μετρήσεων από πρότυπα
description: Καθορίστε μετρήσεις χρησιμοποιώντας πρότυπα για υποθέσεις κοινής χρήσης.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170773"
---
# <a name="create-measures-from-templates"></a>Δημιουργία μετρήσεων από πρότυπα

Χρησιμοποιήστε προκαθορισμένα πρότυπα που χρησιμοποιούνται συνήθως [μέτρα](measures.md) να τα δημιουργήσετε. Τα πρότυπα αξιοποιούν αντιστοιχισμένα δεδομένα από την οντότητα *Ενοποιημένη δραστηριότητα*. Επομένως, βεβαιωθείτε ότι έχετε ρυθμίσει τις παραμέτρους [των δραστηριοτήτων των πελατών](activities.md) πριν δημιουργήσετε μια μέτρηση από ένα πρότυπο.

Τα πρότυπα μετρήσεων υποστηρίζονται μόνο σε περιβάλλοντα για **μεμονωμένους πελάτες**. Για να δημιουργήσετε προσαρμοσμένα μέτρα ή να δημιουργήσετε μέτρα για το B-to-B, βλ [Χρησιμοποιήστε εργαλείο δημιουργίας μέτρων](measure-builder.md).

Διαθέσιμα πρότυπα μετρήσεων:
- Μέση αξία συναλλαγής (ATV)
- Συνολική τιμή συναλλαγής
- Μέσο ημερήσιο έσοδο
- Μέσα μηνιαία έσοδα
- Μέσα ετήσια έσοδα
- Πλήθος συναλλαγών
- Κερδισμένοι πόντοι επιβράβευσης
- Εξαργυρωμένοι πόντοι επιβράβευσης
- Ισορροπία πόντων επιβράβευσης
- Ενεργή διάρκεια ζωής πελάτη
- Διάρκεια συνδρομής επιβράβευσης
- Χρόνος από την τελευταία αγορά

## <a name="build-a-new-measure-using-a-template"></a>Δημιουργία νέας μέτρησης με τη χρήση προτύπου

1. Μετάβαση στις **Μετρήσεις**.

1. Επιλέξτε **Νέα** κι επιλέξτε **Επιλογή προτύπου**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Στιγμιότυπο οθόνης του αναπτυσσόμενου μενού κατά τη δημιουργία ενός νέου μέτρου με επισήμανση στο πρότυπο.":::

1. Βρείτε το πρότυπο που ταιριάζει στις ανάγκες σας και επιλέξτε **Επιλογή προτύπου**.

1. Εξετάστε τα απαιτούμενα δεδομένα και επιλέξτε **Έναρξη**, εάν έχετε όλα τα δεδομένα στη θέση τους.

1. Επιλέξτε **Επεξεργασία λεπτομερειών** δίπλα στο όνομα της μέτρησης. Πληκτρολογήστε ένα όνομα για τη μέτρηση. Προαιρετικά, προσθέστε [ετικέτες](work-with-tags-columns.md#manage-tags) στη μέτρηση.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Παράθυρο διαλόγου επεξεργασίας στοιχείων.":::

1. Επιλέξτε **Τέλος**.

1. Στην ενότητα **Ορισμός χρονικής περιόδου**, ορίστε το χρονικό πλαίσιο των δεδομένων. Επιλέξτε εάν θέλετε η νέα μέτρηση να καλύπτει ολόκληρο το σύνολο δεδομένων επιλέγοντας **Οποτεδήποτε** ή εάν θέλετε η μέτρηση να εστιάσει σε μια **Συγκεκριμένη χρονική περίοδο**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Στιγμιότυπο οθόνης που δείχνει την ενότητα χρονικής περιόδου κατά τη ρύθμιση μιας μέτρησης από ένα πρότυπο.":::

1. Στην επόμενη ενότητα, επιλέξτε **Προσθήκη δεδομένων** για να επιλέξετε δραστηριότητες και να αντιστοιχίσετε τα αντίστοιχα δεδομένα από την οντότητα *Ενιαία δραστηριότητα*.

    1. Βήμα 1 από 2: Στην περιοχή **Τύπος δραστηριότητας**, επιλέξτε τον τύπο της οντότητας που θέλετε να χρησιμοποιήσετε. Για **Δραστηριότητες**, επιλέξτε τις οντότητες που θέλετε να αντιστοιχίσετε και, στη συνέχεια, επιλέξτε **Επόμενο**.
    1. Βήμα 2 από 2: Επιλέξτε το χαρακτηριστικό από την οντότητα *Ενοποιημένη δραστηριότητα* για το στοιχείο που απαιτείται από τον τύπο. Για παράδειγμα, για τη μέση τιμή συναλλαγής, είναι το χαρακτηριστικό που αντιπροσωπεύει την τιμή της συναλλαγής. Για **Χρονική σήμανση δραστηριότητας**, επιλέξτε το χαρακτηριστικό από την οντότητα *Ενοποιημένη Δραστηριότητα* που αντιπροσωπεύει την ημερομηνία και την ώρα της δραστηριότητας.
    1. Επιλέξτε **Αποθήκευση**.

    Όταν η αντιστοίχιση δεδομένων είναι επιτυχής, εμφανίζεται η κατάσταση **Πλήρης** και εμφανίζονται το όνομα των αντιστοιχισμένων δραστηριοτήτων και χαρακτηριστικών.

1. Επιλέξτε **Εκτέλεση** για τον υπολογισμό των αποτελεσμάτων του μέτρου. Επιλέξτε **Αποθήκευση του σχεδίου** εάν θέλετε να διατηρήσετε την τρέχουσα διαμόρφωση και να εκτελέσετε τη μέτρηση αργότερα. Η σελίδα **Μέτρα** εμφανίζει τη σελίδα.

## <a name="next-step"></a>Επόμενο βήμα

Χρησιμοποιήστε τα υπάρχοντα μέτρα για τη δημιουργία [ενός τμήματος πελατών](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]