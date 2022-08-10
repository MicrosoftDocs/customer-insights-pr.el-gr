---
title: Εξαγάγετε τμήματα του Customer Insights στο Adobe Campaign Standard (έκδοση προεπισκόπησης)
description: Μάθετε πώς να χρησιμοποιείτε τα τμήματα του Customer Insights στο Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195520"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Εξαγάγετε τμήματα του Customer Insights στο Adobe Campaign Standard (έκδοση προεπισκόπησης)

Εξαγωγή τμημάτων που στοχεύουν σε σχετικό κοινό Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Διάγραμμα διεργασίας των βημάτων που περιγράφονται σε αυτό το άρθρο.":::

## <a name="prerequisites"></a>Προϋποθέσεις

- Μια άδεια Adobe Campaign Standard.
- Ένα όνομα [Λογαριασμού Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) και κλειδί λογαριασμού. Για να βρείτε το όνομα και το κλειδί, βλ [Διαχειριστείτε τις ρυθμίσεις λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).
- Ένα [Κοντέινερ Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Επισκόπηση εκστρατείας

Για να κατανοήσετε καλύτερα τον τρόπο με τον οποίο μπορείτε να χρησιμοποιήσετε τμήματα από το Customer Insights στο Adobe Experience Platform, δείτε ένα φανταστικό δείγμα εκστρατείας.

Ας υποθέσουμε ότι η εταιρεία σας προσφέρει μια μηνιαία υπηρεσία βάσει συνδρομής στους πελάτες σας στις Ηνωμένες Πολιτείες. Θέλετε να προσδιορίσετε τους πελάτες, των οποίων οι συνδρομές πρέπει να ανανεωθούν μέσα στις επόμενες οκτώ ημέρες, αλλά δεν έχουν ανανεώσει ακόμα τη συνδρομή τους. Για να διατηρήσετε αυτούς τους πελάτες, θέλετε να τους στείλετε μια διαφημιστική προσφορά μέσω ηλεκτρονικού ταχυδρομείου, χρησιμοποιώντας το Adobe Campaign Standard.

Σε αυτό το παράδειγμα, θέλουμε να εκτελέσουμε την εκστρατεία ηλεκτρονικού ταχυδρομείου προώθησης μία φορά. Αυτό το άρθρο δεν καλύπτει την περίπτωση χρήσης της εκτέλεσης της εκστρατείας περισσότερες από μία φορές. Ωστόσο, το Customer Insights και το Adobe Campaign Standard μπορούν να ρυθμιστούν ώστε να λειτουργούν και για ένα επαναλαμβανόμενο σενάριο εκστρατείας.

## <a name="identify-your-target-audience"></a>Προσδιορισμός του κοινού-στόχου

Στο σενάριό μας, υποθέτουμε ότι οι διευθύνσεις ηλεκτρονικού ταχυδρομείου των πελατών είναι διαθέσιμες στο Customer Insights και οι διαφημιστικές προτιμήσεις τους αναλύθηκαν για τον προσδιορισμό των μελών του τμήματος αγοράς.

Το [τμήμα αγοράς που ορίσατε στο Customer Insights](segments.md) ονομάζεται **ChurnProneCustomers** και σχεδιάζετε να στείλετε σε αυτούς τους πελάτες την προώθηση μέσω ηλεκτρονικού ταχυδρομείου.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμημάτων με το τμήμα ChurnProneCustomers που δημιουργήθηκε.":::

Το μήνυμα ηλεκτρονικού ταχυδρομείου της προσφοράς που θέλετε να στείλετε θα περιέχει τις πληροφορίες όνομα, επώνυμο και την ημερομηνία λήξης της συνδρομής του πελάτη. Ενημερώνει τους πελάτες σχετικά με την έκπτωση που θα έχουν, εάν ανανεώσουν τη συνδρομή τους πριν λήξει.

## <a name="export-your-target-audience"></a>Εξαγωγή του κοινού-στόχου

### <a name="set-up-connection-to-adobe-campaign"></a>Ρύθμιση σύνδεσης σε Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Adobe Campaign**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εισάγετε το **Όνομα λογαριασμού**, **Κλειδί λογαριασμού**, και **Κοντέινερ** για τον λογαριασμό σας στο Blob Storage.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Στιγμιότυπο οθόνης της ρύθμισης παραμέτρων λογαριασμού χώρου αποθήκευσης.":::

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

### <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Adobe Campaign. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Επιλέξτε το τμήμα που θέλετε να εξαγάγετε. Σε αυτό το παράδειγμα, είναι **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη επιλογής τμήματος με επιλεγμένο το τμήμα ChurnProneCustomers.":::

1. Επιλέξτε **Επόμενο**.

1. Αντιστοιχίστε τα πεδία **Πηγή** από το τμήμα Customer Insights στα ονόματα πεδίων **Στόχος** στο σχήμα προφίλ Adobe Campaign Standard .

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Αντιστοίχιση πεδίου για τη σύνδεση Adobe Campaign Standard.":::

   Εάν θέλετε να προσθέσετε περισσότερα χαρακτηριστικά, επιλέξτε **Προσθήκη χαρακτηριστικού**. Το όνομα προορισμού μπορεί να είναι διαφορετικό από το όνομα του πεδίου προέλευσης, ώστε να μπορείτε ακόμα να αντιστοιχίσετε το αποτέλεσμα τμήματος αγοράς από το Customer Insights στο Adobe Campaign Standard, εάν τα πεδία δεν έχουν το ίδιο όνομα στα δύο συστήματα.

   > [!NOTE]
   > Η διεύθυνση ηλεκτρονικού ταχυδρομείου χρησιμοποιείται ως πεδίο ταυτότητας, αλλά μπορείτε να χρησιμοποιήσετε οποιοδήποτε άλλο αναγνωριστικό από το προφίλ πελάτη για να αντιστοιχίσετε δεδομένα στο Adobe Campaign Standard.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Βεβαιωθείτε ότι ο αριθμός των καρτελών στο τμήμα που έχει εξαχθεί βρίσκεται εντός του επιτρεπόμενου ορίου της άδειας χρήσης του Adobe Campaign Standard.

Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ του χώρου αποθήκευσης αντικειμένων blob Azure που διαμορφώσατε παραπάνω. Η ακόλουθη διαδρομή φακέλου δημιουργείται αυτόματα στο κοντέινερ σας: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Ρύθμιση παραμέτρων Adobe Campaign Standard

Τα εξαγόμενα τμήματα περιέχουν τις στήλες που επιλέξατε κατά τη διαμόρφωση της εξαγωγής. Αυτά τα δεδομένα μπορούν να χρησιμοποιηθούν για [τη δημιουργία προφίλ στο Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Για να χρησιμοποιήσετε το τμήμα στο Adobe Campaign Standard , [επεκτείνετε το σχήμα του προφίλ](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) σε Adobe Campaign Standard  για να συμπεριλάβει δύο επιπλέον πεδία.

Στο παράδειγμά μας, αυτά τα πεδία είναι Όνομα τμήματος και Ημερομηνία τμήματος. Θα χρησιμοποιήσουμε αυτά τα πεδία για να προσδιορίσουμε τα προφίλ στο Adobe Campaign Standard που θέλουμε να στοχεύσετε για αυτήν την εκστρατεία.

Εάν δεν υπάρχουν άλλες εγγραφές Adobe Campaign Standard, εκτός από αυτές που πρόκειται να εισαγάγετε, παραλείψτε αυτό το βήμα.

## <a name="import-data-into-adobe-campaign-standard"></a>Εισαγωγή δεδομένων στο Adobe Campaign Standard

Εισαγάγετε τα προετοιμασμένα δεδομένα κοινού από το Customer Insights Adobe Campaign Standard σε [δημιουργήστε προφίλ χρησιμοποιώντας μια ροή εργασίας](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Η ροή εργασιών εισαγωγής στην παρακάτω εικόνα έχει ρυθμιστεί ώστε να εκτελείται κάθε οκτώ ώρες και να αναζητά τμήματα Customer Insights που έχουν εξαχθεί (αρχείο .csv στον χώρο αποθήκευσης Azure Blob). Η ροή εργασιών εξάγει το περιεχόμενο του αρχείου .csv σε μια καθορισμένη σειρά στηλών. Αυτή η ροή εργασίας έχει δημιουργηθεί για την εκτέλεση βασικού χειρισμού σφαλμάτων και τη διασφάλιση ότι κάθε καρτέλα έχει μια διεύθυνση ηλεκτρονικού ταχυδρομείου πριν από τη διόρθωση των δεδομένων στο Adobe Campaign Standard. Η ροή εργασίας εξάγει επίσης το όνομα του τμήματος από το όνομα αρχείου πριν να μετατραπεί σε δεδομένα προφίλ Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Στιγμιότυπο οθόνης μιας ροής εργασίας εισαγωγής στο περιβάλλον εργασίας χρήστη Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Ανάκτηση του κοινού Adobe Campaign Standard

Μόλις εισαχθούν τα δεδομένα στο Adobe Campaign Standard, [δημιουργήστε μια ροή εργασίας](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) και [αναζητήστε](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) πελάτες με βάση το Όνομα τμήματος και την Ημερομηνία τμήματος για να επιλεγούν προφίλ που προσδιορίστηκαν για τη δειγματική μας καμπάνια.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Δημιουργία και αποστολή του μηνύματος ηλεκτρονικού ταχυδρομείου χρησιμοποιώντας το Adobe Campaign Standard

Δημιουργήστε το περιεχόμενο του μηνύματος ηλεκτρονικού ταχυδρομείου και, στη συνέχεια, [δοκιμάστε και στείλτε](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) το μήνυμα ηλεκτρονικού ταχυδρομείου σας.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Δείγμα μηνύματος ηλεκτρονικού ταχυδρομείου με προσφορά ανανέωσης από Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
