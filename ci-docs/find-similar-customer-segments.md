---
title: Εύρεση παρόμοιων πελατών με AI (έκδοση προεπισκόπησης) (περιέχει βίντεο)
description: Εύρεση παρόμοιων τμημάτων πελατών με τεχνητή νοημοσύνη.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170727"
---
# <a name="find-similar-customers-with-ai-preview"></a>Εύρεση παρόμοιων πελατών με AI (έκδοση προεπισκόπησης)

Εύρεση παρόμοιων πελατών στη βάση πελατών σας με χρήση τεχνητής νοημοσύνης. Χρειάζεστε τουλάχιστον ένα τμήμα που δημιουργείται για να χρησιμοποιήσετε αυτήν τη δυνατότητα. Η επέκταση των κριτηρίων ενός υπάρχοντος τμήματος βοηθά στην εύρεση πελατών που είναι παρόμοιοι με αυτό το τμήμα.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> To *Βρείτε παρόμοιους πελάτες* χρησιμοποιεί αυτοματοποιημένα μέσα για να αξιολογήσει δεδομένα και να κάνει προβλέψεις με βάση αυτά τα δεδομένα. Ως εκ τούτου, έχει τη δυνατότητα να χρησιμοποιηθεί ως μέθοδος δημιουργίας προφίλ, όπως αυτός ο όρος ορίζεται από τον Γενικό Κανονισμό Προστασίας Δεδομένων («GDPR»). Η χρήση αυτής της δυνατότητας από τον πελάτη για την επεξεργασία των δεδομένων μπορεί να υπόκειται στον ΓΚΠΔ ή άλλες νομοθεσίες ή κανονισμούς. Είστε υπεύθυνοι για τη διασφάλιση ότι η χρήση του Dynamics 365 Customer Insights, συμπεριλαμβανομένων προβλέψεων, συμμορφώνεται με όλους τους ισχύοντες νόμους και κανονισμούς, συμπεριλαμβανομένων των νόμων που σχετίζονται με την προστασία της ιδιωτικής ζωής, τα προσωπικά δεδομένα, τα βιομετρικά δεδομένα, την προστασία των δεδομένων και την εμπιστευτικότητα των επικοινωνιών.

## <a name="find-similar-customers"></a>Εύρεση παρόμοιων πελατών

1. Μεταβείτε στην επιλογή **Τμήματα** και επιλέξτε το τμήμα στο οποίο θέλετε να βασίσετε το νέο σας τμήμα. Αυτό είναι το *τμήμα προέλευσής* σας.

1. Επιλέξτε το **Βρείτε παρόμοιους πελάτες**.

1. Ελέγξτε το προτεινόμενο όνομα για το νέο τμήμα και αλλάξτε το, εάν είναι απαραίτητο.

1. Προαιρετικά, προσθέστε [ετικέτες](work-with-tags-columns.md#manage-tags) στο νέο τμήμα.

1. Ελέγξτε τα πεδία που καθορίζουν το νέο σας τμήμα. Αυτά τα πεδία ορίζουν τη βάση στην οποία το σύστημα θα προσπαθήσει να βρει παρόμοιους πελάτες στο τμήμα προέλευσής σας. Το σύστημα επιλέγει τα προτεινόμενα πεδία από προεπιλογή. Εάν χρειάζεται, προσθέστε περισσότερα πεδία.
  Τα πεδία που μπορούν να μειώσουν σημαντικά την απόδοση του μοντέλου εξαιρούνται αυτόματα:
  
   - Πεδία με τους ακόλουθους τύπους δεδομένων: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Πεδία με προτεραιότητα (ο αριθμός των στοιχείων σε ένα πεδίο) μικρότερη από 2 ή μεγαλύτερη από 30

1. Επιλέξτε αν θέλετε να συμπεριλάβετε το **Όλοι οι πελάτες** εκτός από το τμήμα πηγής ή μόνο τους πελάτες σε ένα **διαφορετικό τμήμα** στο νέο σας τμήμα.

1. Από προεπιλογή, το σύστημα προτείνει την συμπερίληψη μόνο του 20% του μεγέθους του κοινού προορισμού στην έξοδό σας. Επεξεργαστείτε αυτό το όριο, όπως απαιτείται. Η αύξηση του ορίου θα μειώσει την ακρίβεια.

1. Συμπεριλάβετε πελάτες στο τμήμα προέλευσης επιλέγοντας το πλαίσιο ελέγχου **Συμπερίληψη μελών από το τμήμα προέλευσης επιπλέον των πελατών με παρόμοια χαρακτηριστικά**.

1. Επιλέξτε **Εκτέλεση** στο κάτω μέρος της σελίδας για να ξεκινήσετε μια [εργασία δυαδικής ταξινόμησης](#about-similarity-scores) (μια μέθοδος μηχανικής μάθησης) που αναλύει το σύνολο δεδομένων.

## <a name="view-the-similar-segment"></a>Προβολή του αντίστοιχου τμήματος

Μετά την επεξεργασία του παρόμοιου τμήματος, θα βρείτε το νέο τμήμα που παρατίθεται στη σελίδα **Τμήματα** με τον τύπο **Επέκταση**.

Επιλέξτε **Προβολή** για να δείτε την κατανομή των αποτελεσμάτων σε [βαθμολογίες ομοιότητας](#about-similarity-scores) και τιμές βαθμολογίας ομοιότητας κάτω από το **Προεπισκόπηση μελών τμήματος**.

:::image type="content" source="media/expanded-segment.png" alt-text="Τμήμα παρόμοιων πελατών.":::

## <a name="manage-a-similar-segment"></a>Διαχειριστείτε ένα παρόμοιο τμήμα

[Εργαστείτε και διαχειριστείτε ένα παρόμοιο τμήμα](segments.md#manage-existing-segments) όπως κάνετε με άλλα τμήματα. Για παράδειγμα, εξαγάγετε το τμήμα ή δημιουργήστε μια μέτρηση.

Επεξεργαστείτε, ανανεώστε, μετονομάστε, κατεβάστε και διαγράψτε ένα παρόμοιο τμήμα. Η επεξεργασία ενός παρόμοιου τμήματος επεξεργάζεται ξανά τα δεδομένα σας. Γίνεται ενημέρωση του τμήματος που δημιουργήθηκε προηγουμένως με ανανεωμένα δεδομένα.

## <a name="about-similarity-scores"></a>Πληροφορίες για τις βαθμολογίες ομοιότητας

Το μοντέλο δυαδικής ταξινόμησης Εκμάθηση μηχανής αντιστοιχίζει μια βαθμολογία σε πελάτες παρόμοιου τμήματος. Η βαθμολογία βασίζεται στην ομοιότητα με τους πελάτες στο τμήμα προέλευσης.

- Οι βαθμολογίες ομοιότητας κάτω του 0,55 είναι πελάτες που το σύστημα ταξινόμησε ως *δεν είναι παρόμοιοι* με τους πελάτες στο τμήμα προέλευσης
- Οι βαθμολογίες ομοιότητας μεταξύ 0,55 – 0,7 ταξινομούνται ως *κάπως παρόμοιοι*
- Οι βαθμολογίες ομοιότητας μεταξύ 0,7 – 0,85 ταξινομούνται ως *παρόμοιοι*
- Οι βαθμολογίες ομοιότητας μεταξύ 0,85 – 1 είναι πελάτες που το σύστημα ταξινόμησε ως *πολύ παρόμοιοι*

Οι πελάτες με βαθμολογίες ομοιότητας κάτω από 0,4 δεν περιλαμβάνονται στην έξοδο του μοντέλου. Το σύστημα δεν τους θεωρεί αρκετά παρόμοιους με το τμήμα προέλευσης.

[!INCLUDE [footer-include](includes/footer-banner.md)]