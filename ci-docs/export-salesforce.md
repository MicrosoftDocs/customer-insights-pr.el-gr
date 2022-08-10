---
title: Εξαγωγή δεδομένων στο cloud μάρκετινγκ του Salesforce (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίζετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197038"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Εξαγωγή δεδομένων στο cloud μάρκετινγκ του Salesforce (έκδοση προεπισκόπησης)

Χρησιμοποιήστε τα δεδομένα πελατών σας στο Salesforce Marketing Cloud εξαγάγοντάς τα μέσω μιας θέσης πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP).

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [κεντρικός υπολογιστής SFTP για το Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Ρυθμίστε τη σύνδεση με το Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Salesforce Marketing Cloud**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Παρέχετε ένα **Όνομα χρήστη**, έναν **Κωδικό πρόσβασης**, ένα **Όνομα κεντρικού υπολογιστή** και έναν **Φάκελο εξαγωγής** για τον λογαριασμό SFTP.

1. Επιλέξτε **Επαλήθευση** για να δοκιμάσετε τη σύνδεση.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα SFTP. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Επιλέξτε εάν θέλετε να εξαγάγετε τα δεδομένα σας στο πεδίο **Gzipped** ή **Χωρίς συμπίεση** και τον **οριοθέτη πεδίων** για τα αρχεία που έχουν εξαχθεί.

1. Επιλέξτε τις οντότητες, για παράδειγμα τμήματα, που θέλετε να εξαγάγετε.

   > [!NOTE]
   > Κάθε επιλεγμένη οντότητα θα χωριστεί σε έως πέντε αρχεία εξόδου κατά την εξαγωγή.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Εισαγωγή δεδομένων του Customer Insights από τη θέση SFTP στο Salesforce Marketing Cloud

1. Δημιουργήστε [επεκτάσεις δεδομένων στο Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) για να εισαγάγετε το αρχείο δεδομένων Customer Insights από τη θέση SFTP.

2. [Εισαγάγετε τα δεδομένα από τη θέση SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) στην επέκταση δεδομένων του Salesforce Marketing Cloud.

3. Ρυθμίστε την αυτοματοποίηση, ώστε να εισαγάγετε τα δεδομένα στις επεκτάσεις δεδομένων. Μάθετε περισσότερα σχετικά με [τις αυτοματοποιήσεις απόθεσης αρχείων και τις προγραμματισμένες αυτοματοποιήσεις](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Καθορίστε [μια αυτοματοποίηση απόθεσης αρχείων](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ή μια  [προγραμματισμένη αυτοματοποίηση](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Ακολουθεί ένα παράδειγμα [αυτοματοποίησης με SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
