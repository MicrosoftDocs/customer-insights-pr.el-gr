---
title: Εξαγωγή δεδομένων του Customer Insights στο Adobe Campaign Standard
description: Μάθετε πώς να χρησιμοποιείτε τμήματα πληροφοριών κοινού στο Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760281"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Χρησιμοποιήστε τμήματα Customer Insights στο Adobe Campaign Standard (έκδοση προεπισκόπησης)

Ως χρήστης των πληροφοριών κοινού για Dynamics 365 Customer Insights, ενδέχεται να έχετε δημιουργήσει τμήματα για να κάνετε τις εκστρατείες μάρκετινγκ πιο αποτελεσματικές στοχεύοντας σε σχετικά κοινά. Για να χρησιμοποιήσετε ένα τμήμα από πληροφορίες κοινού στο Adobe Experience Platform και σε εφαρμογές όπως το Adobe Campaign Standard, θα πρέπει να ακολουθήσετε μερικά βήματα που περιγράφονται σε αυτό το άρθρο.

:::image type="content" source="media/ACS-flow.png" alt-text="Διάγραμμα διεργασίας των βημάτων που περιγράφονται σε αυτό το άρθρο.":::

## <a name="prerequisites"></a>Προϋποθέσεις

-   Άδεια χρήσης του Dynamics 365 Customer Insights
-   Άδεια χρήσης του Adobe Campaign Standard
-   Λογαριασμό χώρου αποθήκευσης αντικειμένων Blob Azure

## <a name="campaign-overview"></a>Επισκόπηση εκστρατείας

Για να κατανοήσετε καλύτερα πώς μπορείτε να χρησιμοποιήσετε τμήματα από πληροφορίες κοινού στο Adobe Experience Platform, δείτε ένα φανταστικό δείγμα εκστρατείας.

Ας υποθέσουμε ότι η εταιρεία σας προσφέρει μια μηνιαία υπηρεσία βάσει συνδρομής στους πελάτες σας στις Ηνωμένες Πολιτείες. Θέλετε να προσδιορίσετε τους πελάτες, των οποίων οι συνδρομές πρέπει να ανανεωθούν μέσα στις επόμενες οκτώ ημέρες, αλλά δεν έχουν ανανεώσει ακόμα τη συνδρομή τους. Για να διατηρήσετε αυτούς τους πελάτες, θέλετε να τους στείλετε μια διαφημιστική προσφορά μέσω ηλεκτρονικού ταχυδρομείου, χρησιμοποιώντας το Adobe Campaign Standard.

Σε αυτό το παράδειγμα, θέλουμε να εκτελέσουμε την εκστρατεία ηλεκτρονικού ταχυδρομείου προώθησης μία φορά. Αυτό το άρθρο δεν καλύπτει την περίπτωση χρήσης της εκτέλεσης της εκστρατείας περισσότερες από μία φορές. Ωστόσο, οι πληροφορίες κοινού και το Adobe Campaign Standard μπορούν να ρυθμιστούν ώστε να λειτουργούν και για ένα επαναλαμβανόμενο σενάριο εκστρατείας.

## <a name="identify-your-target-audience"></a>Προσδιορισμός του κοινού-στόχου

Στο σενάριό μας, υποθέτουμε ότι οι διευθύνσεις ηλεκτρονικού ταχυδρομείου των πελατών είναι διαθέσιμες στις πληροφορίες κοινού και οι διαφημιστικές προτιμήσεις τους αναλύθηκαν για τον προσδιορισμό μελών του τμήματος.

Το [τμήμα που ορίσατε στις πληροφορίες κοινού](segments.md) ονομάζεται **ChurnProneCustomers** και σχεδιάζετε να στείλετε σε αυτούς τους πελάτες την προώθηση ηλεκτρονικού ταχυδρομείου.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμημάτων με το τμήμα ChurnProneCustomers που δημιουργήθηκε.":::

Το μήνυμα ηλεκτρονικού ταχυδρομείου της προσφοράς που θέλετε να στείλετε θα περιέχει τις πληροφορίες όνομα, επώνυμο και την ημερομηνία λήξης της συνδρομής του πελάτη. Ενημερώνει τους πελάτες σχετικά με την έκπτωση που θα έχουν, εάν ανανεώσουν τη συνδρομή τους πριν λήξει.

## <a name="export-your-target-audience"></a>Εξαγωγή του κοινού-στόχου

### <a name="configure-a-connection"></a>Ρύθμιση παραμέτρων μιας σύνδεσης

Με προσδιορισμένο το κοινό-στόχο μας, μπορούμε να ρυθμίσουμε τις παραμέτρους εξαγωγής από πληροφορίες κοινού σε έναν λογαριασμό χώρου αποθήκευσης αντικειμένων blob Azure.

1. Στις πληροφορίες κοινού, μεταβείτε στο **Διαχειριστής** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** κι επιλέξτε **Εκστρατεία Adobe** για να ρυθμίσετε τις παραμέτρους της σύνδεσης ή επιλέξτε **Ρύθμιση** στο πλακίδιο **Εκστρατεία Adobe** 

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Πλακίδιο ρύθμισης παραμέτρων για το Adobe Campaign Standard.":::

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Εισαγάγετε το **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Κοντέινερ** του λογαριασμού χώρου αποθήκευσης αντικειμένου blob Azure όπου θέλετε να εξαγάγετε το τμήμα.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Στιγμιότυπο οθόνης της ρύθμισης παραμέτρων λογαριασμού χώρου αποθήκευσης."::: 

   - Για να μάθετε περισσότερα σχετικά με το πώς μπορείτε να βρείτε το όνομα του λογαριασμού αποθήκευσηςAzure Blob και το κλειδί λογαριασμού, δείτε [Διαχείριση ρυθμίσεων λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).

   - Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

### <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα "Εκστρατεία Adobe". Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.

1. Επιλέξτε το τμήμα που θέλετε να εξαγάγετε. Σε αυτό το παράδειγμα, είναι **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη επιλογής τμήματος με επιλεγμένο το τμήμα ChurnProneCustomers.":::

1. Επιλέξτε **Επόμενο**.

1. Τώρα αντιστοιχουμε τα πεδία **προέλευσης** από το τμήμα πληροφοριών κοινού στα ονόματα πεδίων **προορισμού** του σχήματος προφίλ "Adobe Campaign Standard".

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Αντιστοίχιση πεδίου για τη σύνδεση Adobe Campaign Standard.":::

   Εάν θέλετε να προσθέσετε περισσότερα χαρακτηριστικά, επιλέξτε **Προσθήκη χαρακτηριστικού**. Το όνομα προορισμού μπορεί να είναι διαφορετικό από το όνομα του πεδίου προέλευσης, ώστε να εξακολουθείτε να μπορείτε να αντιστοιχίσετε έξοδο τμημάτων από πληροφορίες κοινού στο Adobe Campaign Standard, εάν τα πεδία δεν έχουν το ίδιο όνομα στα δύο συστήματα.

   > [!NOTE]
   > Η διεύθυνση ηλεκτρονικού ταχυδρομείου χρησιμοποιείται ως πεδίο ταυτότητας, αλλά μπορείτε να χρησιμοποιήσετε οποιοδήποτε άλλο αναγνωριστικό από το προφίλ πελάτη πληροφοριών κοινού για την αντιστοίχιση δεδομένων στο Adobe Campaign Standard.

1. Επιλέξτε **Αποθήκευση**.

Αφού αποθηκεύσετε τον προορισμό εξαγωγής, τον βρίσκετε στα **Δεδομένα** > **Εξαγωγές**.

Τώρα μπορείτε να [εξαγάγετε το τμήμα κατ' απαίτηση](export-destinations.md#run-exports-on-demand). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md).

> [!NOTE]
> Βεβαιωθείτε ότι ο αριθμός των καρτελών στο εξαχθέν τμήμα βρίσκεται εντός του επιτρεπόμενου ορίου της άδειας χρήσης που έχετε για το Adobe Campaign Standard.

Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ του χώρου αποθήκευσης αντικειμένων blob Azure που ρυθμίσατε παραπάνω. Η παρακάτω διαδρομή φακέλου δημιουργείται αυτόματα στο κοντέινερ σας:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Ρύθμιση παραμέτρων Adobe Campaign Standard

Όταν εξάγεται ένα τμήμα από πληροφορίες κοινού, περιέχει τις στήλες που επιλέξατε κατά τον ορισμό του προορισμού εξαγωγής στο προηγούμενο βήμα. Αυτά τα δεδομένα μπορούν να χρησιμοποιηθούν για [τη δημιουργία προφίλ στο Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Για να χρησιμοποιήσετε το τμήμα στο Adobe Campaign Standard, θα πρέπει να επεκτείνουμε το σχήμα προφίλ στο Adobe Campaign Standard και να συμπεριλάβουμε δύο επιπλέον πεδία. Μάθετε πώς να [επεκτείνετε τον πόρο προφίλ](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) με νέα πεδία στο Adobe Campaign Standard.

Στο παράδειγμά μας, τα πεδία αυτά είναι *Όνομα τμήματος και Ημερομηνία τμήματος (προαιρετικά).*

Θα χρησιμοποιήσουμε αυτά τα πεδία για να εντοπίσουμε τα προφίλ στο Adobe Campaign Standard που θέλουμε να στοχεύσετε για αυτήν την εκστρατεία.

Εάν δεν υπάρχουν άλλες καρτέλες στο Adobe Campaign Standard, εκτός από τις καρτέλες που πρόκειται να εισαγάγετε, μπορείτε να παραλείψετε αυτό το βήμα.

## <a name="import-data-into-adobe-campaign-standard"></a>Εισαγωγή δεδομένων στο Adobe Campaign Standard

Τώρα που όλα είναι έτοιμα, θα πρέπει να εισαγάγετε τα προετοιμασμένα δεδομένα κοινού ααπό τις πληροφορίες κοινού στο Adobe Campaign Standard για τη δημιουργία προφίλ. Μάθετε [πώς να εισάγετε προφίλ στο Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) χρησιμοποιώντας μια ροή εργασιών.

Η ροή εργασιών εισαγωγής στην παρακάτω εικόνα έχει ρυθμιστεί ώστε να εκτελείται κάθε 8 ώρες και αναζητά τμήματα πληροφοριών κοινού που έχουν εξαχθεί (αρχείο .csv στον χώρο αποθήκευσης αντικειμένων Blob Azure). Η ροή εργασιών εξάγει το περιεχόμενο του αρχείου .csv σε μια καθορισμένη σειρά στηλών. Αυτή η ροή εργασιών έχει δημιουργηθεί για την εκτέλεση βασικού χειρισμού σφαλμάτων και τη διασφάλιση ότι κάθε καρτέλα έχει μια διεύθυνση ηλεκτρονικού ταχυδρομείου πριν από την ανασύνθεση των δεδομένων στο Adobe Campaign Standard. Η ροή εργασιών εξάγει επίσης το όνομα του τμήματος από το όνομα αρχείου πριν να μετατραπεί σε δεδομένα προφίλ ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Στιγμιότυπο οθόνης μιας ροής εργασιών εισαγωγής στο περιβάλλον εργασίας χρήστη Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Ανάκτηση του κοινού στο Adobe Campaign Standard

Μετά την εισαγωγή των δεδομένων στο Adobe Campaign Standard, [μπορείτε να δημιουργήσετε μια ροή εργασιών](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) και [να υποβάλετε ερωτήματα](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) στους πελάτες με βάση το *όνομα τμήματος* και την *ημερομηνία τμήματος*, για να επιλέξουν τα προφίλ που έχουν αναγνωριστεί για το δείγμα εκστρατείας μας.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Δημιουργία και αποστολή του μηνύματος ηλεκτρονικού ταχυδρομείου χρησιμοποιώντας το Adobe Campaign Standard

Δημιουργήστε το περιεχόμενο του μηνύματος ηλεκτρονικού ταχυδρομείου και, στη συνέχεια, [δοκιμάστε και στείλτε](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) το μήνυμα ηλεκτρονικού ταχυδρομείου σας.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Δείγμα μηνύματος ηλεκτρονικού ταχυδρομείου με προσφορά ανανέωσης από το Adobe Campaign Standard.":::