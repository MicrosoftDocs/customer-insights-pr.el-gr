---
title: Έλεγοχς της ενοποίησης δεδομένων
description: Ελέγξτε τα βήματα ενοποίησης δεδομένων, δημιουργήστε ενοποιημένα προφίλ πελατών και ελέγξτε τα αποτελέσματα
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303967"
---
# <a name="review-data-unification"></a>Έλεγοχς της ενοποίησης δεδομένων

Ελέγξτε τη σύνοψη των αλλαγών, δημιουργήστε το ενοποιημένο προφίλ και εξετάστε τα αποτελέσματα.

## <a name="review-and-create-customer-profiles"></a>Έλεγχος και δημιουργία προφίλ πελατών

Αυτό το τελευταίο βήμα στη διεργασία ενοποίησης εμφανίζει μια σύνοψη των βημάτων της διεργασίας και σας δίνει την ευκαιρία να κάνετε αλλαγές πριν δημιουργήσετε το ενοποιημένο προφίλ.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Στιγμιότυπο οθόνης Ελεγχός και Δημιουργία προφίλ πελατών.":::

1. Επιλέξτε **Επεξεργασία** σε οποιοδήποτε από τα βήματα ενοποίησης δεδομένων για να ελέγξετε και να κάνετε τυχόν αλλαγές.

1. Εάν είστε ικανοποιημένοι με τις επιλογές σας, επιλέξτε **Δημιουργία προφίλ πελατών** (ή **Δημιουργία προφίλ λογαριασμών** για Β2Β). Η σελίδα **Ενοποίηση** εμφανίζεται ενώ δημιουργείται το ενοποιημένο προφίλ πελάτη.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Στιγμιότυπο οθόνης της σελίδας Ενοποίησης με πλακίδια που εμφανίζονται Σε ουρά ή Ανανέωση.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ο αλγόριθμος της ενοποίησης απαιτεί λίγο χρόνο για να ολοκληρωθεί και δεν μπορείτε να αλλάξετε τη ρύθμιση του μέχρι να ολοκληρωθεί.

## <a name="view-the-results-of-data-unification"></a>Προβολή των αποτελεσμάτων της ενοποίησης δεδομένων

Μετά την ενοποίηση, η σελίδα **Δεδομένα** > **Ενοποίηση** εμφανίζει τον αριθμό των ενοποιημένων προφίλ πελατών (ή προφίλ λογαριασμών για Β2Β). Τα αποτελέσματα κάθε βήματος της διεργασίας ενοποίησης εμφανίζονται σε κάθε πλακίδιο. Για παράδειγμα, τα **Πεδία προέλευσης** δείχνουν τον αριθμό των αντιστοιχισμένων χαρακτηριστικών (πεδίων) και οι **Διπλότυπες καρτέλες** δείχνουν τον αριθμό των διπλότυπων καρτελών που εντοπίστηκαν.

:::image type="content" source="media/m3_unified.png" alt-text="Στιγμιότυπο οθόνης της σελίδας Ενοποίηση δεδομένων μετά την ενοποίηση των δεδομένων.":::

> [!TIP]
> Το πλακίδιο **Συνθήκες αντιστοίχισης** εμφανίζεται μόνο εάν έχουν επιλεγεί πολλαπλές οντότητες.

Συνιστούμε να ελέγξετε τα αποτελέσματα, ιδιαίτερα την ποιότητα των [κανόνων αντιστοίχισης](data-unification-update.md#manage-match-rules) και να τους βελτιώσετε εάν είναι απαραίτητο.

Όταν είναι απαραίτητο, [κάντε αλλαγές στις ρυθμίσεις ενοποίησης](data-unification-update.md) και εκτελέστε ξανά το ενοποιημένο προφίλ.

### <a name="verify-output-entities-from-data-unification"></a>Επαλήθευση οντοτήτων εξόδου από την επεξεργασία δεδομένων

Μεταβείτε στα **Δεδομένα** > **Οντότητες** για να επαληθεύσετε τις οντότητες εξόδου.

Η ενοποιημένη οντότητα προφίλ πελάτη ονομάζεται *Πελάτης* στην ενότητα **Προφίλ**. Η πρώτη επιτυχημένη εκτέλεση ενοποίησης δημιουργεί την ενοποιημένη οντότητα *Πελάτης*. Όλες οι επόμενες εκτελέσεις αναπτύσσουν τη συγκεκριμένη οντότητα.

Οι οντότητες για την κατάργηση διπλοτύπων και τον συνδυασμό δημιουργούνται και εμφανίζονται στην ενότητα **Σύστημα**. Η οντότητα κατάργησης διπλοτύπων για κάθε οντότητα προέλευσης δημιουργείται με το όνομα **Deduplication_DataSource_Entity**. Η οντότητα **ConflationMatchPairs** περιέχει πληροφορίες σχετικά με αντιστοιχίσεις μεταξύ οντοτήτων.

Μια οντότητα εξόδου κατάργησης διπλοτύπων περιέχει τις ακόλουθες πληροφορίες:
- Αναγνωριστικά / Κλειδιά
  - Πεδία πρωτεύοντος κλειδιού και εναλλακτικού αναγνωριστικού. Το πεδίο εναλλακτικού αναγνωριστικού αποτελείται από όλα τα εναλλακτικά αναγνωριστικά που έχουν αναγνωριστεί για μια καρτέλα.
  - Το πεδίο Deduplication_GroupId εμφανίζει την ομάδα ή το σύμπλεγμα που προσδιορίζεται μέσα σε μια οντότητα που ομαδοποιεί όλες τις παρόμοιες εγγραφές με βάση τα καθορισμένα πεδία κατάργησης διπλοτύπων. Χρησιμοποιείται για σκοπούς επεξεργασίας συστήματος. Εάν δεν ορίζονται μη αυτόματοι κανόνες κατάργησης διπλοτύπων και ισχύουν κανόνες κατάργησης διπλοτύπων οριζόμενοι από το σύστημα, ενδέχεται να μην βρείτε αυτό το πεδίο στην οντότητα εξόδου κατάργησης διπλοτύπων.
  - Deduplication_WinnerId: Αυτό το πεδίο περιέχει το αναγνωριστικό νικητή από τις προσδιορισμένες ομάδες ή συμπλέγματα. Εάν η Deduplication_WinnerId είναι ίδια με την τιμή πρωτεύοντος κλειδιού για μια εγγραφή, αυτό σημαίνει ότι η εγγραφή είναι η νικητήρια εγγραφή.
- Πεδία που χρησιμοποιούνται για τον ορισμό των κανόνων κατάργησης διπλοτύπων.
- Πεδία Κανόνα και Βαθμολογίας για να δηλώσετε ποιοι από τους κανόνες κατάργησης διπλοτύπων εφαρμόστηκαν και η βαθμολογία που επιστράφηκε από τον αλγόριθμο αντιστοίχισης.

## <a name="next-step"></a>Επόμενο βήμα

- Για Β2Β, εκτελέστε προαιρετικά [ενοποίηση επαφών](data-unification-contacts.md).

- Για B2C [δραστηριότητες](activities.md), [εμπλουτισμούς](enrichment-hub.md), [σχέσεις](relationships.md) ή [μετρήσεις](measures.md) για την απόκτηση περισσότερων πληροφοριών σχετικά με τους πελάτες σας.

[!INCLUDE[footer-include](includes/footer-banner.md)]