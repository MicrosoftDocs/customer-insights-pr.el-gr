---
title: Εξαγωγή τμημάτων στο Adobe Experience Platform (έκδοση προεπισκόπησης)
description: Μάθετε πώς να χρησιμοποιείτε τα τμήματα του Customer Insights στο Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195290"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Εξαγωγή τμημάτων στο Adobe Experience Platform (έκδοση προεπισκόπησης)

Εξαγωγή τμημάτων που στοχεύουν σε σχετικό κοινό Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Διάγραμμα διεργασίας των βημάτων που περιγράφονται σε αυτό το άρθρο.":::

## <a name="prerequisites"></a>Προϋποθέσεις

- Μία άδεια Adobe Experience Platform.
- Μια άδεια Adobe Campaign Standard.
- Ένα όνομα [Λογαριασμού Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) και κλειδί λογαριασμού. Για να βρείτε το όνομα και το κλειδί, βλ [Διαχειριστείτε τις ρυθμίσεις λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).
- Ένα [Κοντέινερ Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Επισκόπηση εκστρατείας

Για να κατανοήσετε καλύτερα τον τρόπο με τον οποίο μπορείτε να χρησιμοποιήσετε τμήματα από το Customer Insights στο Adobe Experience Platform, δείτε ένα φανταστικό δείγμα εκστρατείας.

Ας υποθέσουμε ότι η εταιρεία σας προσφέρει μια μηνιαία υπηρεσία βάσει συνδρομής στους πελάτες σας στις Ηνωμένες Πολιτείες. Θέλετε να προσδιορίσετε τους πελάτες, των οποίων οι συνδρομές πρέπει να ανανεωθούν μέσα στις επόμενες οκτώ ημέρες, αλλά δεν έχουν ανανεώσει ακόμα τη συνδρομή τους. Για να διατηρήσετε αυτούς τους πελάτες, θέλετε να τους στείλετε μια διαφημιστική προσφορά μέσω ηλεκτρονικού ταχυδρομείου, χρησιμοποιώντας το Adobe Experience Platform.

Σε αυτό το παράδειγμα, θέλουμε να εκτελέσουμε την εκστρατεία ηλεκτρονικού ταχυδρομείου προώθησης μία φορά. Αυτό το άρθρο δεν καλύπτει την περίπτωση χρήσης της εκτέλεσης της εκστρατείας περισσότερες από μία φορές.

## <a name="identify-your-target-audience"></a>Προσδιορισμός του κοινού-στόχου

Στο σενάριό μας, υποθέτουμε ότι οι διευθύνσεις ηλεκτρονικού ταχυδρομείου των πελατών είναι διαθέσιμες στο Customer Insights και οι διαφημιστικές προτιμήσεις τους αναλύθηκαν για τον προσδιορισμό των μελών του τμήματος αγοράς.

Το [τμήμα αγοράς που ορίσατε στο Customer Insights](segments.md) ονομάζεται **ChurnProneCustomers** και σχεδιάζετε να στείλετε σε αυτούς τους πελάτες την προώθηση μέσω ηλεκτρονικού ταχυδρομείου.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμημάτων με το τμήμα ChurnProneCustomers που δημιουργήθηκε.":::

Το μήνυμα ηλεκτρονικού ταχυδρομείου της προσφοράς που θέλετε να στείλετε θα περιέχει τις πληροφορίες όνομα, επώνυμο και την ημερομηνία λήξης της συνδρομής του πελάτη. Ενημερώνει τους πελάτες σχετικά με την έκπτωση που θα έχουν, εάν ανανεώσουν τη συνδρομή τους πριν λήξει.

## <a name="export-your-target-audience"></a>Εξαγωγή του κοινού-στόχου

Θα διαμορφώσουμε την εξαγωγή από το Customer Insights σε έναν λογαριασμό Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Ρυθμίστε τη σύνδεση στο Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Αποθήκευση Azure Blob**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εισαγάγετε **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Κοντέινερ** για τον λογαριασμό χώρου αποθήκευσης αντικειμένου blob όπου θέλετε να εξαγάγετε το τμήμα.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Στιγμιότυπο οθόνης της ρύθμισης παραμέτρων λογαριασμού χώρου αποθήκευσης.":::

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

### <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα χώρος αποθήκευσης αντικειμένων blob Azure. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Επιλέξτε το τμήμα που θέλετε να εξαγάγετε. Σε αυτό το παράδειγμα, είναι **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη επιλογής τμήματος με επιλεγμένο το τμήμα ChurnProneCustomers.":::

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Βεβαιωθείτε ότι ο αριθμός των καρτελών στο τμήμα που έχει εξαχθεί βρίσκεται εντός του επιτρεπόμενου ορίου της άδειας χρήσης του Adobe Campaign Standard.

Τα εξαγόμενα δεδομένα αποθηκεύονται στο κοντέινερ αποθήκευσης Azure Blob που έχετε διαμορφώσει. Οι παρακάτω διαδρομές φακέλων δημιουργούνται αυτόματα στο κοντέινερ που διαθέτετε:

- Για τις οντότητες προέλευσης και τις οντότητες που δημιουργούνται από το σύστημα: 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Το *model.json* για τις οντότητες που έχουν εξαχθεί βρίσκεται στο επίπεδο *%ExportDestinationName%*.

  Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Καθορισμός μοντέλου δεδομένων εμπειρίας (XDM) στο Adobe Experience Platform

Προτού τα εξαγόμενα δεδομένα από το Customer Insights μπορούν να χρησιμοποιηθούν εντός Adobe Experience Platform, ορίστε το σχήμα Μοντέλου Δεδομένων Εμπειρίας και [διαμορφώστε τα δεδομένα για το προφίλ πελάτη σε πραγματικό χρόνο](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Μάθετε [τι είναι το XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) και κατανοήστε τα [βασικά στοιχεία της σύνθεσης σχημάτων](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Εισαγωγή δεδομένων στο Adobe Experience Platform

Εισαγάγετε τα προετοιμασμένα δεδομένα κοινού από το Customer Insights Adobe Experience Platform.

1. [Δημιουργήστε μια σύνδεση πηγής Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Διαμορφώστε μια ροή δεδομένων](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) για μια μαζική σύνδεση αποθήκευσης cloud για εισαγωγή της εξόδου τμήματος από το Customer Insights Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Δημιουργήστε ένα κοινό στο Adobe Campaign Standard

Για να στείλουμε το μήνυμα ηλεκτρονικού ταχυδρομείου για αυτήν την εκστρατεία, θα χρησιμοποιήσουμε το Adobe Campaign Standard.

1. [Δημιουργήστε ένα κοινό](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) σε Adobe Campaign Standard χρησιμοποιώντας τα δεδομένα στο Adobe Experience Platform.

1. [Χρησιμοποιήστε το εργαλείο δημιουργίας τμημάτων](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) σε Adobe Campaign Standard για να ορίσετε ένα κοινό με βάση τα δεδομένα Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Δημιουργία και αποστολή του μηνύματος ηλεκτρονικού ταχυδρομείου χρησιμοποιώντας το Adobe Campaign Standard

Δημιουργήστε το περιεχόμενο του μηνύματος ηλεκτρονικού ταχυδρομείου και, στη συνέχεια, [δοκιμάστε και στείλτε](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) το μήνυμα ηλεκτρονικού ταχυδρομείου σας.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Δείγμα μηνύματος ηλεκτρονικού ταχυδρομείου με προσφορά ανανέωσης από Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
