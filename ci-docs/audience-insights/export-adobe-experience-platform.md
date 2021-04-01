---
title: Εξαγωγή δεδομένων του Customer Insights στο Adobe Experience Platform
description: Μάθετε πώς να χρησιμοποιείτε τμήματα πληροφοριών κοινού στο Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596269"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Χρησιμοποιήστε τμήματα Customer Insights στο Adobe Experience Platform (έκδοση προεπισκόπησης)

Ως χρήστης των πληροφοριών κοινού για Dynamics 365 Customer Insights, ενδέχεται να έχετε δημιουργήσει τμήματα για να κάνετε τις εκστρατείες μάρκετινγκ πιο αποτελεσματικές στοχεύοντας σε σχετικά κοινά. Για να χρησιμοποιήσετε ένα τμήμα από πληροφορίες κοινού στο Adobe Experience Platform και σε εφαρμογές όπως το Adobe Campaign Standard, θα πρέπει να ακολουθήσετε μερικά βήματα που περιγράφονται σε αυτό το άρθρο.

:::image type="content" source="media/AEP-flow.png" alt-text="Διάγραμμα διεργασίας των βημάτων που περιγράφονται σε αυτό το άρθρο.":::

## <a name="prerequisites"></a>Προϋποθέσεις

-   Άδεια χρήσης του Dynamics 365 Customer Insights
-   Άδεια χρήσης του Adobe Experience Platform
-   Άδεια χρήσης του Adobe Campaign Standard
-   Λογαριασμό χώρου αποθήκευσης αντικειμένων Blob Azure

## <a name="campaign-overview"></a>Επισκόπηση εκστρατείας

Για να κατανοήσετε καλύτερα πώς μπορείτε να χρησιμοποιήσετε τμήματα από πληροφορίες κοινού στο Adobe Experience Platform, δείτε ένα φανταστικό δείγμα εκστρατείας.

Ας υποθέσουμε ότι η εταιρεία σας προσφέρει μια μηνιαία υπηρεσία βάσει συνδρομής στους πελάτες σας στις Ηνωμένες Πολιτείες. Θέλετε να προσδιορίσετε τους πελάτες, των οποίων οι συνδρομές πρέπει να ανανεωθούν μέσα στις επόμενες οκτώ ημέρες, αλλά δεν έχουν ανανεώσει ακόμα τη συνδρομή τους. Για να διατηρήσετε αυτούς τους πελάτες, θέλετε να τους στείλετε μια διαφημιστική προσφορά μέσω ηλεκτρονικού ταχυδρομείου, χρησιμοποιώντας το Adobe Experience Platform.

Σε αυτό το παράδειγμα, θέλουμε να εκτελέσουμε την εκστρατεία ηλεκτρονικού ταχυδρομείου προώθησης μία φορά. Αυτό το άρθρο δεν καλύπτει την περίπτωση χρήσης της εκτέλεσης της εκστρατείας περισσότερες από μία φορές.

## <a name="identify-your-target-audience"></a>Προσδιορισμός του κοινού-στόχου

Στο σενάριό μας, υποθέτουμε ότι οι διευθύνσεις ηλεκτρονικού ταχυδρομείου των πελατών είναι διαθέσιμες στις πληροφορίες κοινού και οι διαφημιστικές προτιμήσεις τους αναλύθηκαν για τον προσδιορισμό μελών του τμήματος.

Το [τμήμα που ορίσατε στις πληροφορίες κοινού](segments.md) ονομάζεται **ChurnProneCustomers** και σχεδιάζετε να στείλετε σε αυτούς τους πελάτες την προώθηση ηλεκτρονικού ταχυδρομείου.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμημάτων με το τμήμα ChurnProneCustomers που δημιουργήθηκε.":::

Το μήνυμα ηλεκτρονικού ταχυδρομείου της προσφοράς που θέλετε να στείλετε θα περιέχει τις πληροφορίες όνομα, επώνυμο και την ημερομηνία λήξης της συνδρομής του πελάτη. Ενημερώνει τους πελάτες σχετικά με την έκπτωση που θα έχουν, εάν ανανεώσουν τη συνδρομή τους πριν λήξει.

## <a name="export-your-target-audience"></a>Εξαγωγή του κοινού-στόχου

Με προσδιορισμένο το κοινό-στόχο μας, μπορούμε να ρυθμίσουμε τις παραμέτρους εξαγωγής από πληροφορίες κοινού σε έναν λογαριασμό χώρου αποθήκευσης αντικειμένων blob Azure.

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στο πλακίδιο του **Χώρου αποθήκευσης αντικειμένων blob Azure**, επιλέξτε **Ρύθμιση**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Πλακίδιο ρύθμισης παραμέτρων για χώρο αποθήκευσης αντικειμένων blob Azure.":::

1. Δώστε ένα **εμφανιζόμενο όνομα** για αυτόν τον νέο προορισμό εξαγωγής και, στη συνέχεια, καταχωρήστε το **όνομα λογαριασμού**, το **κλειδί λογαριασμού** και το **κοντέινερ** του λογαριασμού χώρου αποθήκευσης αντικειμένων blob Azure στον οποίο θέλετε να εξαγάγετε το τμήμα.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Στιγμιότυπο οθόνης της ρύθμισης παραμέτρων λογαριασμού χώρου αποθήκευσης."::: 

   - Για να μάθετε περισσότερα σχετικά με το πώς μπορείτε να βρείτε το όνομα του λογαριασμού αποθήκευσηςAzure Blob και το κλειδί λογαριασμού, δείτε [Διαχείριση ρυθμίσεων λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).

   - Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε το τμήμα που θέλετε να εξαγάγετε. Σε αυτό το παράδειγμα, είναι **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη επιλογής τμήματος με επιλεγμένο το τμήμα ChurnProneCustomers.":::

1. Επιλέξτε **Αποθήκευση**.

Αφού αποθηκεύσετε τον προορισμό εξαγωγής, τον βρίσκετε στην τοποθεσία **Admin** > **Εξαγωγές** > **Οι προορισμοί εξαγωγών μου**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Στιγμιότυπο οθόνης με τη λίστα των εξαγωγών και του δείγματος τμήματος που έχει επισημανθεί.":::

Τώρα μπορείτε να [εξαγάγετε το τμήμα κατ' απαίτηση](export-destinations.md#export-data-on-demand). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md).

> [!NOTE]
> Βεβαιωθείτε ότι ο αριθμός των καρτελών στο εξαχθέν τμήμα βρίσκεται εντός του επιτρεπόμενου ορίου της άδειας χρήσης που έχετε για το Adobe Campaign Standard.

Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ του χώρου αποθήκευσης αντικειμένων blob Azure που ρυθμίσατε παραπάνω. Η παρακάτω διαδρομή φακέλου δημιουργείται αυτόματα στο κοντέινερ σας:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Το *model.json* για τις οντότητες που έχουν εξαχθεί βρίσκεται στο επίπεδο *%ExportDestinationName%*.

Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Καθορισμός μοντέλου δεδομένων εμπειρίας (XDM) στο Adobe Experience Platform

Για να μπορούν να χρησιμοποιηθούν τα εξαχθέντα δεδομένα από τις πληροφορίες κοινού στο Adobe Experience Platform, πρέπει να ορίσουμε το σχήμα του μοντέλου δεδομένων εμπειρίας και [να ρυθμίσουμε τα δεδομένα για το προφίλ πελάτη σε πραγματικό χρόνο](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Μάθετε [τι είναι το XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) και κατανοήστε τα [βασικά στοιχεία της σύνθεσης σχημάτων](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Εισαγωγή δεδομένων στο Adobe Experience Platform

Τώρα που όλα είναι έτοιμα, θα πρέπει να εισαγάγετε τα προετοιμασμένα δεδομένα κοινού ααπό τις πληροφορίες κοινού στο Adobe Experience Platform.

Πρώτα, [δημιουργήστε μια σύνδεση προέλευσης χώρου αποθήκευσης αντικειμένων Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Αφού καθορίσετε τη σύνδεση προέλευσης, [ρυθμίστε τις παραμέτρους μιας ροής δεδομένων](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) για μια σύνδεση δέσμης χώρου αποθήκευσης cloud για την εισαγωγή της εξόδου του τμήματος από πληροφορίες κοινού στο Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Δημιουργία ενός κοινού στο Adobe Campaign Standard

Για να στείλουμε το μήνυμα ηλεκτρονικού ταχυδρομείου για αυτήν την εκστρατεία, θα χρησιμοποιήσουμε το Adobe Campaign Standard. Μετά την εισαγωγή των δεδομένων στο Adobe Experience Platform, θα πρέπει να [δημιουργήσουμε ένα κοινό](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) στο Adobe Campaign Standard χρησιμοποιώντας τα δεδομένα στο Adobe Experience Platform.

Μάθετε πώς να [χρησιμοποιείτε το εργαλείο δόμησης τμημάτων](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) στο Adobe Campaign Standard για να ορίσετε ένα κοινό με βάση τα δεδομένα στο Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Δημιουργία και αποστολή του μηνύματος ηλεκτρονικού ταχυδρομείου χρησιμοποιώντας το Adobe Campaign Standard

Δημιουργήστε το περιεχόμενο του μηνύματος ηλεκτρονικού ταχυδρομείου και, στη συνέχεια, [δοκιμάστε και στείλτε](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) το μήνυμα ηλεκτρονικού ταχυδρομείου σας.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Δείγμα μηνύματος ηλεκτρονικού ταχυδρομείου με προσφορά ανανέωσης από το Adobe Campaign Standard.":::