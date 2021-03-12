---
title: Προτεινόμενα τμήματα υποστηριζόμενα από εκμάθηση μηχανής
description: Αφήστε την Εκμάθηση μηχανής να σας βοηθήσει να βρείτε νέα και ενδιαφέροντα τμήματα με βάση τα χαρακτηριστικά των πελατών.
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268226"
---
# <a name="suggested-segments-preview"></a>Προτεινόμενα τμήματα (προεπισκόπηση)

Ανακαλύψτε ενδιαφέροντα τμήματα των πελατών σας με τη βοήθεια ενός μοντέλου AI. Αυτή η δυνατότητα με υποστήριξη εκμάθησης μηχανής προτείνει τμήματα που βασίζονται σε μεγέθη ή χαρακτηριστικά πελατών. Μπορεί να σας βοηθήσει να βελτιώσετε τους KPI σας ή να κατανοήσετε καλύτερα την επιρροή των χαρακτηριστικών στο πλαίσιο άλλων χαρακτηριστικών. 

> [!NOTE]
> Η δυνατότητα προτεινόμενων τμημάτων χρησιμοποιεί αυτοματοποιημένα μέσα για την αξιολόγηση δεδομένων και την πραγματοποίηση προβλέψεων με βάση αυτά τα δεδομένα και, ως εκ τούτου, έχει τη δυνατότητα να χρησιμοποιηθεί ως μέθοδος κατάρτισης προφίλ, όπως ορίζεται από τον Γενικό Κανονισμό για Προστασίας Δεδομένων ("ΓΚΠΔ"). Η χρήση αυτής της δυνατότητας από μέρους σας για την επεξεργασία δεδομένων ενδέχεται να υπόκειται σε ΓΚΠΔ ή άλλους νόμους ή κανονισμούς. Είστε υπεύθυνοι για τη διασφάλιση ότι η χρήση του Dynamics 365 Customer Insights, συμπεριλαμβανομένης αυτής της δυνατότητας, συμμορφώνεται με όλους τους ισχύοντες νόμους και κανονισμούς, συμπεριλαμβανομένων των νόμων που σχετίζονται με την προστασία της ιδιωτικής ζωής, τα προσωπικά δεδομένα, τα βιομετρικά δεδομένα, την προστασία των δεδομένων και την εμπιστευτικότητα των επικοινωνιών.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Σελίδα προτεινόμενων τμημάτων στο Customer Insights που εμφανίζει λεπτομέρειες μιας πρότασης σε ένα πλευρικό τμήμα παραθύρου.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Προτεινόμενα τμήματα για τη βελτίωση των KPI σας

Ως χρήστης πληροφοριών κοινού, πιθανότατα έχετε δημιουργήσει μια σειρά [μεγεθών](measures.md) που σας βοηθούν να παρακολουθείτε τους βασικούς δείκτες απόδοσης (KPI). Είναι σημαντικό να κατανοήσετε πώς ορισμένα χαρακτηριστικά επηρεάζουν αυτόν τον KPI για τη δημιουργία τμημάτων και την εκτέλεση μιας εξαιρετικά στοχευμένης καμπάνιας.   
Για παράδειγμα, μπορείτε να παρακολουθήσετε ένα μέγεθος που ονομάζεται *TotalSpendPerCustomer*. Ως επιχείρηση, θα θέλατε να δείτε αυτόν τον αριθμό να αυξάνεται. Η επιλογή ενός μεγέθους ως πρωτεύοντος χαρακτηριστικού, σας επιτρέπει να επιλέξετε τα χαρακτηριστικά που θέλετε να αξιολογήσετε για επιρροή. Ας πούμε *επίπεδο ιδιότητας μέλους*, *περίοδος συμμετοχής* και *επάγγελμα*. Το Customer Insights μπορεί στη συνέχεια να προτείνει ένα τμήμα που σας λέει ποια είναι η μεγαλύτερη επιρροή αυτού του μεγέθους. Για παράδειγμα, *Λογιστές* που είναι *χρυσά* μέλη και που βρίσκονται στην επιχείρησή σας για *τουλάχιστον πέντε χρόνια* είναι ο μεγαλύτερος παράγοντας επιρροής του *TotalSpendPerCustomer*. Θα λάβετε ένα εκτιμώμενο μέγεθος τμήματος για κάθε πρόταση. Μπορείτε να χρησιμοποιήσετε αυτές τις πληροφορίες για να δημιουργήσετε καμπάνιες για τα στοχευόμενα κοινά.

## <a name="understand-what-influences-a-customer-attribute"></a>Κατανόηση του τι επηρεάζει ένα χαρακτηριστικό πελάτη

Μπορείτε να επιλέξετε ένα χαρακτηριστικό πελάτη αντί για ένα μέγεθος ως κύριο χαρακτηριστικό. Με βάση την επιλογή χαρακτηριστικών που έχουν επιρροή, το μοντέλο AI δημιουργεί μια σειρά προτάσεων που δείχνουν πώς τα επιλεγμένα χαρακτηριστικά επηρεάζουν το πρωτεύον χαρακτηριστικό.   
Για παράδειγμα, επιλέγετε *Μέλος Ανταμοιβών (Ναι/Όχι)* ως κύριο χαρακτηριστικό. Τα *θητεία*, *επάγγελμα* και *αριθμός των εισιτηρίων υποστήριξης* ορίζονται ως άλλα χαρακτηριστικά που επηρεάζουν. Το μοντέλο τεχνητής νοημοσύνης θα μπορούσε να προτείνει τμήματα που υποδεικνύουν ότι ως επί το πλείστον επαγγελματίες πληροφορικής με θητεία άνω των δύο ετών είναι μέλη ανταμοιβών. Μια άλλη πρόταση θα μπορούσε να τονίσει ότι οι λογιστές με θητεία άνω του ενός έτους και λιγότερα από τρία εισιτήρια υποστήριξης είναι μέλη ανταμοιβών. 

## <a name="artificial-intelligence-usage"></a>Χρήση τεχνητής νοημοσύνης

Χρησιμοποιώντας το πρωτεύον χαρακτηριστικό και τα χαρακτηριστικά που έχουν επιρροή, ένας αλγόριθμος δέντρου αποφάσεων προτείνει ενδιαφέροντα τμήματα. Οι προτάσεις βασίζονται σε κανόνες ή μοτίβα που ελήφθησαν από τον αλγόριθμο AI. Μόνο τμήματα που διαφέρουν σημαντικά από τον μέσο πληθυσμό εμφανίζονται ως προτάσεις. Η σύγκριση με τον μέσο πληθυσμό βασίζεται στο επιλεγμένο μέγεθος ή πρωτεύον χαρακτηριστικό.

### <a name="responsible-ai"></a>Υπεύθυνος AI

Τα προτεινόμενα τμήματα σάς επιτρέπουν να επιλέξετε χαρακτηριστικά για να δημιουργήσετε νέα τμήματα και να επεξεργαστείτε τα δεδομένα που επιλέγετε. Όταν επιλέγετε χαρακτηριστικά, συμπεριλαμβανομένων ευαίσθητων χαρακτηριστικών όπως η φυλή, ο σεξουαλικός προσανατολισμός ή το φύλο, πρέπει να διασφαλίσετε ότι μπορείτε και πρέπει να επεξεργαστείτε αυτά τα δεδομένα. Είστε υπεύθυνοι να συμμορφώνεστε με τυχόν νόμους που ισχύουν για τον οργανισμό σας και να τηρείτε τις αρχές και τις πολιτικές απορρήτου του οργανισμού σας.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Διαφορετικά αποτελέσματα για πρωτεύοντα χαρακτηριστικά με κατηγορικές και αριθμητικές τιμές

Οι προτάσεις τμημάτων είναι διαφορετικές εάν επιλέξετε ένα αριθμητικό χαρακτηριστικό ή ένα κατηγορικό χαρακτηριστικό ως πρωτεύον χαρακτηριστικό. Οι τιμές σε ένα κατηγορικό χαρακτηριστικό περιέχουν δύο ή περισσότερες κατηγορίες ή τύπους. Ένα αριθμητικό χαρακτηριστικό περιέχει ποσοτικά δεδομένα και έχει μια αίσθηση μέτρησης που σχετίζεται με αυτό.

Με ένα αριθμητικό χαρακτηριστικό, όπως *ετήσιο εισόδημα* ή *περίοδος συμμετοχής* ως κύριο χαρακτηριστικό, το σύστημα προτείνει τμήματα που έχουν υψηλότερη ή χαμηλότερη μέση τιμή του αριθμητικού χαρακτηριστικού, σε σύγκριση με όλους τους πελάτες.

Ένα κατηγορικό χαρακτηριστικό, όπως η *ικανοποίηση των πελατών* ως κύριο χαρακτηριστικό, έχει ως αποτέλεσμα προτεινόμενα τμήματα που έχουν υψηλότερο ή χαμηλότερο ποσοστό πελατών που ανήκουν σε μια συγκεκριμένη κατηγορία, σε σύγκριση με το ποσοστό όλων των πελατών που ανήκουν στην ίδια κατηγορία. Για παράδειγμα, η *ικανοποίηση των πελατών* επιλέγεται ως το κύριο χαρακτηριστικό και αποτελείται από τρεις κατηγορίες (*Χαμηλή*, *Μεσαία* και *Υψηλή*). Για κάθε κατηγορία, θα προτείνονται τμήματα που έχουν σημαντικά υψηλότερο ή χαμηλότερο ποσοστό πελατών που ανήκουν σε αυτή την κατηγορία σε σύγκριση με το ποσοστό όλων των πελατών της ίδιας κατηγορίας. Εάν το 22% όλων των πελατών έχει *υψηλή* ικανοποίηση, τότε, μόνο τμήματα που έχουν σημαντικά υψηλότερο ή χαμηλότερο ποσοστό πελατών με *υψηλή* ικανοποίηση, σε σύγκριση με το 22%, θα προταθούν για αυτή την κατηγορία. Ομοίως, θα προταθούν τμήματα για καθεμία από τις άλλες κατηγορίες (*Χαμηλή* και *Μεσαία*) εάν είναι στατιστικά σημαντικά.

> [!NOTE]
> Επί του παρόντος, υποστηρίζουμε μόνο κύρια κατηγορικά χαρακτηριστικά που έχουν έως και 10 κατηγορίες. Εάν θέλετε να δείτε προτάσεις τμημάτων με βάση ένα πρωτεύον χαρακτηριστικό με περισσότερες από 10 κατηγορίες, συνιστούμε να ομαδοποιήσετε ορισμένες από τις κατηγορίες για να μειώσετε τον αριθμό των κατηγοριών σε 10 ή λιγότερες. Αυτός ο περιορισμός ισχύει μόνο σε πρωτεύοντα χαρακτηριστικά. Για τον επηρεασμό των κατηγορικών χαρακτηριστικών, υποστηρίζουμε επί του παρόντος έως 100 κατηγορίες το μέγιστο.

## <a name="generate-suggested-segments"></a>Δημιουργήστε τα προτεινόμενα τμήματα

1. Μετάβαση στα **Τμήματα**.

1. Επιλέξτε την καρτέλα **Προτάσεις (προεπισκόπηση)**.

1. Επιλέξτε **Λάβετε νέες προτάσεις** για να ξεκινήσετε την καθοδηγούμενη εμπειρία.

1. Επιλέξτε ένα μέγεθος ή ένα χαρακτηριστικό πελάτη ως κύριο χαρακτηριστικό και επιλέξτε **Επόμενο**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Επιλογή του πρωτεύοντος χαρακτηριστικού για προτάσεις για τα προτεινόμενα τμήματα.":::

1. Επιλέξτε τα χαρακτηριστικά που επηρεάζουν και επιλέξτε **Αποθήκευση**.
   
   > [!TIP]
   > Η επιλογή πολλαπλών χαρακτηριστικών που επηρεάζουν βελτιώνει τις πιθανότητες αξιολόγησης του τρόπου με τον οποίο επηρεάζουν το πρωτεύον χαρακτηριστικό. Μην συμπεριλαμβάνετε χαρακτηριστικά που δεν επηρεάζουν το πρωτεύον χαρακτηριστικό. Για παράδειγμα, εάν όλοι οι πελάτες σας προέρχονται από μια συγκεκριμένη χώρα, μην συμπεριλάβετε το χαρακτηριστικό *χώρα*, επειδή δεν θα έχει καμία επίπτωση στην έξοδο.

1. Ανάλογα με τον αριθμό των προφίλ πελατών και τα επιλεγμένα χαρακτηριστικά, μπορεί να χρειαστούν λίγα λεπτά για την επεξεργασία των επιλεγμένων χαρακτηριστικών. 

## <a name="view-details-of-a-suggested-segment"></a>Προβολή λεπτομερειών ενός προτεινόμενου τμήματος

Μόλις το μοντέλο AI δημιουργήσει τις προτάσεις, θα τις βρείτε καταχωρημένες στο **Τμήματα** > **Προτάσεις (προεπισκόπηση)**.
 
Επιλέξτε ένα προτεινόμενο τμήμα αγοράς για να εξετάσετε τις λεπτομέρειες αυτής της πρότασης, συμπεριλαμβανομένης της σύγκρισης της μέσης τιμής και του αριθμού των μελών του τμήματος. Μπορείτε επίσης να αναθεωρήσετε τις τιμές χαρακτηριστικών ή τους κανόνες που το μοντέλο AI έμαθε να προτείνει το επιλεγμένο τμήμα.

## <a name="save-a-suggestion-as-a-segment"></a>Αποθήκευση μιας πρότασης ως τμήματος

1. Μεταβείτε στα **Τμήματα** > **Προτάσεις (προεπισκόπηση)**.

1. Επιλέξτε το τμήμα αγοράς που θέλετε να αποθηκεύσετε. 

1. Στο πλευρικό τμήμα παραθύρου, επιλέξτε **Αποθήκευση ως τμήματος**. 

1. Μετά την αποθήκευση του τμήματος, θα εμφανίζεται στη λίστα τμημάτων αγοράς στην καρτέλα **Όλα τα τμήματα**. Τώρα μπορεί να [ανανεωθεί, να επεξεργαστεί ή να διαγραφεί όπως οποιοδήποτε άλλο τμήμα](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Ανανέωση ή επεξεργασία ενός συνόλου προτάσεων

1. Μεταβείτε στα **Τμήματα** > **Προτάσεις (προεπισκόπηση)**.

1. Επιλέξτε **Ανανέωση προτάσεων** για να ανανεώσετε τις προτάσεις, διατηρώντας παράλληλα τα ρυθμισμένα χαρακτηριστικά. Εναλλακτικά, επιλέξτε **Επεξεργασία χαρακτηριστικών** για να τροποποιήσετε τα ρυθμισμένα χαρακτηριστικά. Το σύστημα θα επαναλάβει την εκτέλεση του μοντέλου AI, θα δημιουργήσει προτάσεις τμήματος με βάση τα πιο πρόσφατα δεδομένα και θα αντικαταστήσει τις τρέχουσες προτάσεις.

## <a name="limitations"></a>Περιορισμοί

1. Εκτιμώμενη ασυμφωνία μεγέθους τμήματος: Αν επιλέξετε ένα πρωτεύον χαρακτηριστικό που περιέχει κενές τιμές, μπορεί να επηρεάσει το εκτιμώμενο μέγεθος τμήματος αγοράς στις προτάσεις τμήματος αγοράς. Κατά την αποθήκευση αυτού του τμήματος, το πραγματικό μέγεθος του τμήματος μπορεί να είναι διαφορετικό από την αρχική εκτίμηση.
 
2. Τα κύρια χαρακτηριστικά τύπου Boolean δεν λειτουργούν: Προς το παρόν, υποστηρίζουμε μόνο τύπους συμβολοσειρών και αριθμητικών δεδομένων ως πρωτεύον χαρακτηριστικό.

3. Τα προτεινόμενα τμήματα δεν είναι αρκετά διακριτά: Λάβετε υπόψη ότι τα επιλεγμένα χαρακτηριστικά και η κατανομή των τιμών αυτών των χαρακτηριστικών επηρεάζουν τα αποτελέσματα. Μπορείτε να αλλάξετε τα χαρακτηριστικά που επηρεάζουν ή ακόμα και το κύριο χαρακτηριστικό σας για να έχετε διαφορετικά αποτελέσματα.



[!INCLUDE[footer-include](../includes/footer-banner.md)]