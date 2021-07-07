---
title: Εξαγωγή δεδομένων του Customer Insights στο Salesforce Marketing Cloud
description: Μάθετε πώς να ρυθμίζετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314615"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Εξαγωγή τμημάτων και άλλων δεδομένων στο Salesforce Marketing Cloud (έκδοση προεπισκόπησης)

Χρησιμοποιήστε τα δεδομένα πελατών σας στο Salesforce Marketing Cloud εξαγάγοντάς τα μέσω μιας θέσης πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP).

## <a name="prerequisites-for-connection"></a>Προϋποθέσεις για σύνδεση

- Διαθεσιμότητα κεντρικού υπολογιστή SFTP και των αντίστοιχων διαπιστευτηρίων διαχειριστή. [Πώς να ρυθμίσετε θέσεις SFTP για το Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Ο χρόνος εκτέλεσης μιας εξαγωγής εξαρτάται από την απόδοση του συστήματός σας. Συνιστούμε δύο πυρήνες CPU και 1 Gb μνήμης ως ελάχιστη διαμόρφωση του διακομιστή σας. 
- Η εξαγωγή οντοτήτων με έως 100 εκατομμύρια προφίλ πελατών μπορεί να διαρκέσει 90 λεπτά όταν χρησιμοποιείται η συνιστώμενη ελάχιστη ρύθμιση παραμέτρων. 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Ρύθμιση της σύνδεσης στο Salesforce Marketing Cloud

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Salesforce Marketing Cloud**, για να ρυθμίσετε τις παραμέτρους της σύνδεσης.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Παρέχετε ένα **Όνομα χρήστη**, έναν **Κωδικό πρόσβασης**, ένα **Όνομα κεντρικού υπολογιστή** και έναν **Φάκελο εξαγωγής** για τον λογαριασμό SFTP.

1. Επιλέξτε **Επαλήθευση** για να δοκιμάσετε τη σύνδεση.

1. Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα SFTP. Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.

1. Επιλέξτε εάν θέλετε να εξαγάγετε τα δεδομένα σας στο πεδίο **Gzipped** ή **Χωρίς συμπίεση** και τον **οριοθέτη πεδίων** για τα αρχεία που έχουν εξαχθεί.

1. Επιλέξτε τις οντότητες, για παράδειγμα τμήματα, που θέλετε να εξαγάγετε.

   > [!NOTE]
   > Κάθε επιλεγμένη οντότητα θα διαιρεθεί σε έως και πέντε αρχεία εξόδου κατά την εξαγωγή. 

1. Επιλέξτε **Αποθήκευση**.

Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.

Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab). Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Εισαγωγή δεδομένων του Customer Insights από τη θέση SFTP στο Salesforce Marketing Cloud

1. Δημιουργήστε [επεκτάσεις δεδομένων στο Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) για να εισαγάγετε το αρχείο δεδομένων Customer Insights από τη θέση SFTP.

2. [Εισαγάγετε τα δεδομένα από τη θέση SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) στην επέκταση δεδομένων του Salesforce Marketing Cloud. 

3. Ρυθμίστε την αυτοματοποίηση, ώστε να εισαγάγετε τα δεδομένα στις επεκτάσεις δεδομένων. Μάθετε περισσότερα σχετικά με [τις αυτοματοποιήσεις απόθεσης αρχείων και τις προγραμματισμένες αυτοματοποιήσεις](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Καθορίστε [μια αυτοματοποίηση απόθεσης αρχείων](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)ή μια [προγραμματισμένη αυτοματοποίηση](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Ακολουθεί ένα παράδειγμα [αυτοματοποίησης με SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Απόρρητο δεδομένων και συμμόρφωση

Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα μέσω SFTP, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα. Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι ο προορισμός εξαγωγής πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε. Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
