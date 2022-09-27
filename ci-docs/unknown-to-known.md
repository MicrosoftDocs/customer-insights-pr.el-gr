---
title: Εξατομικεύστε τις εμπειρίες σας με δεδομένα για γνωστούς και άγνωστους χρήστες
description: Ενσωματώστε τις πληροφορίες για πρώην άγνωστους χρήστες όταν γνωρίζετε την ταυτότητά τους.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224295"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Εξατομικεύστε τις εμπειρίες σας με δεδομένα για γνωστούς και άγνωστους χρήστες

Η διαχείριση δεδομένων πελατών δεν είναι μια νέα πρόκληση, αλλά γίνεται όλο και πιο δύσκολη καθώς οι χρήστες περιηγούνται στα διάφορα ψηφιακά κανάλια που προσφέρουν οι επωνυμίες. Ένας χρήστης που είναι γνωστός (με έλεγχο ταυτότητας) σε ένα κανάλι γίνεται άγνωστος (χωρίς έλεγχος ταυτότητας) σε άλλο εάν δεν είναι συνδεδεμένος. Το πρόβλημα συχνά είναι ότι οι μη επαληθευμένοι (άγνωστοι) χρήστες δεν έχουν κοινό αναγνωριστικό. Θα μπορούσε να χρησιμοποιηθεί για να συσχετίσει σημαντικά χαρακτηριστικά προφίλ και να δημιουργήσει ενοποιημένα προφίλ πελατών. Το Customer Insights βοηθά στην επίλυση αυτού του προβλήματος με την απορρόφηση δεδομένων από μεθόδους παρακολούθησης στα συστήματα προέλευσης. Ενοποιήστε γνωστά και άγνωστα προφίλ παρέχοντας στους οργανισμούς μια πλήρη προβολή των ενημερωμένων προφίλ και του ιστορικού συναλλαγών, συμπεριφορών και δημογραφικών στοιχείων τους. Προχωρά ακόμη και ένα βήμα παραπέρα παρέχοντας ανάλυση ταυτότητας που σας επιτρέπει να ενοποιείτε τη δραστηριότητα των πελατών σε πολλά κανάλια, συμπεριλαμβανομένου του ιστότοπού σας, των αγορών στο κατάστημα, των προγραμμάτων επιβράβευσης και ούτω καθεξής.

## <a name="sample-scenario"></a>Δείγμα σεναρίου

Ας σκεφτούμε μια αλυσίδα καφέ, η οποία έχει μια ευρεία βάση πελατών που αγοράζει καφέ και φαγητό σε καταστήματα και παραγγέλνει προϊόντα μέσω διαδικτύου. Συχνά, οι διαδικτυακοί επισκέπτες δεν ελέγχονται κατά την περιήγηση στα προϊόντα, καθιστώντας τους "άγνωστους χρήστες". Είναι δύσκολο για την αλυσίδα καφέ να προσφέρει εξατομικευμένες προσφορές και εμπειρίες εάν οι χρήστες είναι άγνωστοι. Από την άλλη πλευρά, οι πελάτες μπορούν να συνδεθούν στον λογαριασμό τους και να γίνουν "γνωστοί χρήστες" στην εταιρεία μπαίνοντας σε ένα σύστημα αφοσίωσης, το οποίο με τη σειρά του επιτρέπει πιο εξατομικευμένες εμπειρίες. Το Customer Insights μπορεί να βοηθήσει την αλυσίδα καφέ να λάβει πληροφορίες για γνωστούς και προηγουμένως άγνωστους χρήστες.

Με το Customer Insights, η εταιρεία μπορεί να συνδυάσει προφίλ πελατών με δεδομένα δραστηριότητας από μη επαληθευμένες (άγνωστες) περιόδους σύνδεσης, αφού συνδεθεί ένας χρήστης και γίνει γνωστός. Η αλυσίδα καφέ μπορεί να μεταφέρει δεδομένα από άλλες πηγές δεδομένων χρησιμοποιώντας ενσωματωμένες συνδέσεις στο Customer Insights για τη συγχώνευση ταυτοτήτων για πελάτες από διάφορα κανάλια.

## <a name="prerequisites"></a>Προϋποθέσεις

- Τα δεδομένα Ιστού συλλέγονται και περιέχουν "αναγνωριστικά επισκεπτών" για όλους τους επισκέπτες.
- Τα δεδομένα ιστού περιέχουν "επαληθευμένα αναγνωριστικά χρήστη" για συνδεδεμένους επισκέπτες. Αυτά τα αναγνωριστικά συνδέονται με το σύστημα αφοσίωσης.
- Δεδομένα συμβάντων υψηλής αξίας, όπως "Προβολή προϊόντος" και "Ολοκλήρωση αγοράς" ορίζονται και περιλαμβάνονται στα δεδομένα προέλευσης μαζί με τη χρονική σήμανση του συμβάντος και ένα αναγνωριστικό συμβάντος.

Ο παρακάτω πίνακας δείχνει ένα απλοποιημένο παράδειγμα για το πώς θα μπορούσαν να αποτυπωθούν συμβάντα ιστού υψηλής αξίας.

|Αναγνωριστικό συμβάντος|EventTimeStamp|Αναγνωριστικό χρήστη|LoyaltyID|Όνομα συμβάντος|
|--|--|--|--|--|
|1|23-07-2022 10:00:00|abc123|--|Προβολή προϊόντος|
|2|23-07-2022 10:05:00|abc123|707|Είσοδος στην επιβράβευση|
|3|23-07-2022 10:10:00|abc123|707|Ολοκλήρωση αγοράς|
|4|23-07-2022 10:20:00|xyz789|--|Προβολή προϊόντος|

## <a name="data-ingestion"></a>Κατάποση δεδομένων

Τα δεδομένα σχετικά με τους πελάτες μπορούν να προέρχονται από τον ιστότοπό σας ως δεδομένα συμβάντων και μπορούν να αποθηκευτούν στις δικές σας υπηρεσίες ανάλυσης δεδομένων εσωτερικού ή τρίτου μέρους. Τα δεδομένα ιστού περιέχουν γνωστούς και άγνωστους χρήστες εάν ο ιστότοπος διαθέτει ροή ελέγχου ταυτότητας που ενσωματώνεται με μια υπηρεσία ελέγχου ταυτότητας. Για παράδειγμα, ένα σύστημα ηλεκτρονικού εμπορίου που απαιτεί από τους χρήστες να παρέχουν τα πλήρη στοιχεία τους για να ολοκληρώσουν μια συναλλαγή αγοράς. Ή ένα σύστημα επιβράβευσης που απαιτεί έλεγχο ταυτότητας για την επιβεβαίωση έγκυρου παραλήπτη των εκπτώσεων ανταμοιβών.

Τα δεδομένα συμβάντων στο παραπάνω παράδειγμά μας περιέχουν τα διακριτά αναγνωριστικά προφίλ των γνωστών και άγνωστων χρηστών. Στο συμβάν 1 και 4, οι χρήστες είναι άγνωστοι, ενώ στο συμβάν 2 και 3 ο χρήστης με το αναγνωριστικό abc123 εγγράφεται σε ένα πρόγραμμα επιβράβευσης.

:::image type="content" source="media/website-data-source.png" alt-text="Πηγές δεδομένων συμπεριλαμβανομένου του ιστότοπου Contoso.":::

Για περισσότερες πληροφορίες σχετικά με τις διαθέσιμες επιλογές για πρόσληψη δεδομένων, βλ [Επισκόπηση πηγών δεδομένων](data-sources.md).

## <a name="data-unification"></a>Ενοποίηση δεδομένων

Η σύγκλιση άγνωστων ταυτοτήτων με γνωστές ταυτότητες βοηθά στην ενεργοποίηση της εξατομίκευσης με βάση τις συμπεριφορές των χρηστών, ανεξάρτητα από την κατάσταση του προφίλ τους (γνωστή ή άγνωστη). Το εξατομικευμένο περιεχόμενο για όλους τους χρήστες βοηθά τους πελάτες να φτάνουν γρήγορα στα πιο σχετικά προϊόντα ή υπηρεσίες που τους ενδιαφέρουν εκείνη τη στιγμή.

Δεδομένου ότι ορισμένοι από τους χρήστες στα δεδομένα μας είναι γνωστοί, μπορούμε να χρησιμοποιήσουμε το Customer Insights για να συνδυάσουμε αυτά τα δεδομένα με το προφίλ του χρήστη. Για περισσότερες πληροφορίες σχετικά με την ενοποίηση των προφίλ πελατών, βλ [Επισκόπηση ενοποίησης δεδομένων](data-unification.md).

1. Επιλέξτε τα πεδία προέλευσης από την οντότητα δεδομένων ιστού. Χρησιμοποιήστε τα δεδομένα προφίλ που είναι αποθηκευμένα στα δεδομένα ιστού σας και επιλέξτε τα πεδία που αντιπροσωπεύουν αναγνωριστικά με δημογραφικά δεδομένα.

   :::image type="content" source="media/website-source-fields.png" alt-text="Πεδία πηγής για την πηγή δεδομένων ιστού.":::

1. Προσθέστε κανόνες για τη συγχώνευση διπλότυπων εγγραφών. Για δεδομένα ιστού, επιλέξτε τα πιο συμπληρωμένα δεδομένα.

1. Διαμόρφωση κανόνων και συνθηκών αντιστοίχισης. Τα δεδομένα συμβάντων προφίλ ιστού σε αυτό το παράδειγμα θα αντιστοιχιστούν σε αναγνωριστικά με τα προφίλ από άλλες πηγές δεδομένων που περιέχουν πληροφορίες πελατών. Ρυθμίστε κανόνες ακριβούς αντιστοίχισης σε αναγνωριστικά ως ξεχωριστούς κανόνες με καθεμία από τις άλλες οντότητες προφίλ που έχουν αντίστοιχο πρωτεύον κλειδί ή αντιστοίχιση αναγνωριστικού. Στο παράδειγμα, τα δεδομένα προφίλ συμβάντος ιστού χρησιμοποιούνται ως η τελευταία αντίστοιχη οντότητα, έτσι ώστε να συνδυάζονται πρώτα άλλα δεδομένα προφίλ.
   1. Η μη επιλογή του **Συμπεριλάβετε όλες τις εγγραφές** δημιουργεί ενοποιημένα προφίλ για γνωστούς χρήστες και περιλαμβάνει τα αντίστοιχα άγνωστα αναγνωριστικά χρηστών τους. Είναι χρήσιμο σε σενάρια όταν σας ενδιαφέρει να δείτε τις προηγούμενες δραστηριότητες συμπεριφοράς γνωστών χρηστών όταν ήταν ακόμη άγνωστοι.
   1. Η επιλογή του **Συμπεριλάβετε όλες τις εγγραφές** δημιουργεί ξεχωριστές εγγραφές προφίλ για άγνωστους χρήστες. Οι άγνωστοι χρήστες λαμβάνουν ένα μοναδικό αναγνωριστικό πελάτη. Στο μέλλον, όταν ένα γνωστό προφίλ συσχετίζεται στα δεδομένα προφίλ συμβάντων ιστού, τότε η πορεία του πρόσφατα γνωστού χρήστη μπορεί να προβληθεί και να χρησιμοποιηθεί για εξατομίκευση με βάση επίσης άγνωστα δεδομένα συμπεριφοράς του παρελθόντος.

:::image type="content" source="media/website-match-rule.png" alt-text="Κανόνας αντιστοίχισης για την οντότητα πηγής δεδομένων ιστότοπου.":::

## <a name="get-insights"></a>Λήψη πληροφοριών

Εάν δημιουργηθούν προφίλ πελατών για άγνωστους και γνωστούς χρήστες, τα δεδομένα συμβάντων ιστού υψηλής αξίας μπορούν να χρησιμοποιηθούν ως [δραστηριότητες](activities.md). Αυτές οι δραστηριότητες μπορούν να χρησιμοποιηθούν για τη δημιουργία περισσότερων πληροφοριών. Για παράδειγμα, πελάτες που επισκέφτηκαν έναν ιστότοπο πριν από έξι μήνες (όταν ήταν ακόμη άγνωστοι) ή πελάτες που δεν έχουν αναγνωριστικό επιβράβευσης δεν ολοκλήρωσαν ποτέ μια ολοκλήρωση αγοράς.

:::image type="content" source="media/website-known-unknown.png" alt-text="Στιγμιότυπο οθόνης της σελίδας πελάτη με γνωστούς και άγνωστους πελάτες.":::

[Εμπλουτίστε](enrichment-hub.md) τα δεδομένα σας, κατασκευάστε [μέτρα](measures.md)και δημιουργήστε [ενότητες](segments.md) για περαιτέρω ενεργοποίηση.

Για παράδειγμα, μπορείτε να δημιουργήσετε ενότητες γνωστών χρηστών που εξέτασαν ορισμένα προϊόντα αλλά δεν ολοκλήρωσαν ποτέ την αγορά.

Για περισσότερες πληροφορίες, βλ [Επισκόπηση ενοτήτων](segments.md).

## <a name="activate-insights"></a>Ενεργοποίηση πληροφοριών

Υπάρχουν διάφοροι τρόποι για να εξαγάγετε τα δεδομένα σας και να αναλάβετε δράση με βάση τις υποκείμενες πληροφορίες.

Για περισσότερες πληροφορίες, βλ [Επισκόπηση εξαγωγών](export-destinations.md).