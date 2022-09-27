---
title: Δείγμα οδηγού πρόβλεψης απώλειας συναλλαγών
description: Χρησιμοποιήστε αυτό το δείγμα οδηγού για να δοκιμάσετε το έτοιμο μοντέλο πρόβλεψης απώλειας συναλλαγών.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741319"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Δείγμα οδηγού πρόβλεψης απώλειας συναλλαγών

Αυτός ο οδηγός θα σας εξηγήσει ένα παράδειγμα από άκρη σε άκρη της πρόβλεψης απώλειας συναλλαγών στο Customer Insights χρησιμοποιώντας τα δεδομένα που παρέχονται παρακάτω. Όλα τα δεδομένα που χρησιμοποιούνται σε αυτόν τον οδηγό δεν είναι πραγματικά δεδομένα πελάτη και είναι μέρος του συνόλου δεδομένων της Contoso που βρίσκονται στο περιβάλλον *Επίδειξη* εντός της συνδρομής σας στο Customer Insights.

## <a name="scenario"></a>Σενάριο

Η Contoso είναι μια εταιρεία που παράγει υψηλής ποιότητας καφέ και καφετιέρες, τα οποία πωλούν μέσω της τοποθεσίας Web της Contoso Coffee. Ο στόχος τους είναι να γνωρίζουν ποιοι πελάτες που αγοράζουν συνήθως τα προϊόντα τους σε τακτική βάση, θα σταματήσουν να είναι ενεργοί πελάτες στις επόμενες 60 ημέρες. Η γνώση του ποιος από τους πελάτες τους είναι **πιθανό να χαθεί**, μπορεί να τους βοηθήσει να σώσουν τις προσπάθειες μάρκετινγκ εστιάζοντας στη διατήρησή τους.

## <a name="prerequisites"></a>Προϋποθέσεις

- Τουλάχιστον [Δικαιώματα συμμετέχοντα](permissions.md) στο Customer Insights.
- Συνιστούμε να εφαρμόσετε τα παρακάτω βήματα [σε ένα νέο περιβάλλον](manage-environments.md).

## <a name="task-1---ingest-data"></a>Εργασία 1 - Λήψη δεδομένων

Εξετάστε τα άρθρα [σχετικά με την πρόσληψη δεδομένων](data-sources.md) και [την εισαγωγή προελεύσεων δεδομένων χρησιμοποιώντας συνδέσεις Power Query](connect-power-query.md) συγκεκριμένα. Οι παρακάτω πληροφορίες προϋποθέτουν ότι έχετε εξοικειωθεί με τη λήψη δεδομένων γενικά. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Λήψη δεδομένων πελατών από την πλατφόρμα eCommerce

1. Δημιουργήστε μια προέλευση δεδομένων με όνομα **eCommerce**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.

1. Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscontacts.

1. Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.

1. Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:

   - **DateOfBirth**: ημερομηνία
   - **CreatedOn**: ημερομηνία/ώρα/ζώνη

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Μετατροπή DoB σε ημερομηνία.":::

1. Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommerceContacts**

1. Αποθηκεύστε την προέλευση δεδομένων.

### <a name="ingest-online-purchase-data"></a>Λήψη δεδομένων ηλεκτρονικών αγορών

1. Προσθέστε ένα άλλο σύνολο δεδομένων στην ίδια προέλευση δεδομένων **eCommerce**. Επιλέξτε ξανά τη σύνδεση **Κείμενο/CSV**.

1. Εισαγάγετε τη διεύθυνση URL για δεδομένα **Ηλεκτρονικών αγορών** https://aka.ms/ciadclassonline.

1. Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.

1. Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:

   - **PurchasedOn**: ημερομηνία/ώρα
   - **TotalPrice**: νομισματική μονάδα
   
1. Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommercePurchases**.

1. Αποθηκεύστε την προέλευση δεδομένων.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Λήψη δεδομένων πελατών από το σχήμα πίστης

1. Δημιουργήστε μια προέλευση δεδομένων με όνομα **LoyaltyScheme**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.

1. Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.

1. Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:

   - **DateOfBirth**: ημερομηνία
   - **RewardsPoints**: ακέραιος αριθμός
   - **CreatedOn**: ημερομηνία/ώρα

1. Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **loyCustomers**.

1. Αποθηκεύστε την προέλευση δεδομένων.

## <a name="task-2---data-unification"></a>Εργασία 2 - Ενοποίηση δεδομένων

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Εργασία 3 - Ρύθμιση παραμέτρων πρόβλεψης απώλειας συναλλαγών

Με τα ενοποιημένα προφίλ πελατών στη θέση τους, μπορούμε τώρα να εκτελέσουμε την πρόβλεψη της απώλειας της συναλλαγής. Για αναλυτικά βήματα, ανατρέξτε στο [Πρόβλεψη απώλειας συναλλαγής](predict-transactional-churn.md). 

1. Μεταβείτε στο **Ευφυΐα** > **Ανακάλυψη** και επιλέξτε για χρήση του **Μοντέλου απώλειας πελατών**.

1. Επιλέξτε την επιλογή **Συναλλαγών** και επιλέξτε **Έναρξη**.

1. Ονομάστε το μοντέλο **Πρόβλεψη απώλειας συναλλαγών OOB eCommerce** και την οντότητα εξόδου **OOBeCommerceChurnPrediction**.

1. Καθορίστε δύο συνθήκες για το μοντέλο απώλειας:

   * **Παράθυρο πρόβλεψης**: **τουλάχιστον 60** ημέρες. Αυτή η ρύθμιση καθορίζει το βάθος στο μέλλον για το οποίο θέλουμε να προβλέπουμε την απώλεια πελατών.

   * **Ορισμός απώλειας**: **τουλάχιστον 60** ημέρες. Η διάρκεια χωρίς την αγορά μετά από την οποία ένας πελάτης θεωρείται ότι χάθηκε.

     :::image type="content" source="media/model-levers.PNG" alt-text="Επιλέξτε τους μοχλούς μοντέλου Παράθυρο πρόβλεψης και Ορισμός απώλειας.":::

1. Επιλέξτε **Ιστορικό αγορών (απαιτείται)** και επιλέξτε **Προσθήκη δεδομένων** για το ιστορικό αγορών.

1. Προσθέστε την οντότητα **eCommercePurchases: eCommerce** και αντιστοιχίστε τα πεδία από το eCommerce στα αντίστοιχα πεδία που απαιτούνται από το μοντέλο.

1. Συνδυάστε την οντότητα **eCommercePurchases : eCommerce** με το **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Συμμετοχή σε οντότητες eCommerce.":::

1. Επιλέξτε **Επόμενο** για να ορίσετε το χρονοδιάγραμμα μοντέλου.

   Το μοντέλο πρέπει να εκπαιδεύεται τακτικά για την εκμάθηση νέων μοτίβων όταν λαμβάνονται νέα δεδομένα. Για αυτό το παράδειγμα, επιλέξτε **Μηνιαία**.

1. Αφού εξετάσετε όλες τις λεπτομέρειες, επιλέξτε **Αποθήκευση και εκτέλεση**.

## <a name="task-4---review-model-results-and-explanations"></a>Εργασία 4 - Αναθεώρηση αποτελεσμάτων μοντέλου και επεξηγήσεις

Αφήστε το μοντέλο να ολοκληρώσει την εκπαίδευση και τη βαθμολόγηση των δεδομένων. Τώρα μπορείτε να εξετάσετε τις επεξηγήσεις του μοντέλου απώλειας. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Επανεξέταση μιας κατάστασης πρόβλεψης και αποτελέσματα](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Εργασία 5 - Δημιουργία τμήματος πελατών με υψηλό κίνδυνο απώλειας

Η εκτέλεση του μοντέλου παραγωγής δημιουργεί μια νέα οντότητα την οποία μπορείτε να δείτε στα **Δεδομένα** > **Οντότητες**.   

Μπορείτε να δημιουργήσετε ένα νέο τμήμα με βάση την οντότητα που δημιουργήθηκε από το μοντέλο.

1.  Μετάβαση στα **Τμήματα**. Επιλέξτε **Νέο** και επιλέξτε **Δημιουργία από** > **Ευφυΐα**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Δημιουργία τμήματος με την έξοδο μοντέλου.":::

1. Επιλέξτε το τελικό σημείο **OOBeCommerceChurnPrediction** και ορίστε το τμήμα: 
   - Πεδίο: ChurnScore
   - Τελεστής: μεγαλύτερο από
   - Τιμή: 0,6

Τώρα έχετε ένα τμήμα που ενημερώνεται δυναμικά και προσδιορίζει πελάτες υψηλού κινδύνου απώλειας.

Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και διαχείριση τμημάτων](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]