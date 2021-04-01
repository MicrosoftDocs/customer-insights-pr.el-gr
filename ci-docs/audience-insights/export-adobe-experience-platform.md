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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="70678-103">Χρησιμοποιήστε τμήματα Customer Insights στο Adobe Experience Platform (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="70678-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="70678-104">Ως χρήστης των πληροφοριών κοινού για Dynamics 365 Customer Insights, ενδέχεται να έχετε δημιουργήσει τμήματα για να κάνετε τις εκστρατείες μάρκετινγκ πιο αποτελεσματικές στοχεύοντας σε σχετικά κοινά.</span><span class="sxs-lookup"><span data-stu-id="70678-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="70678-105">Για να χρησιμοποιήσετε ένα τμήμα από πληροφορίες κοινού στο Adobe Experience Platform και σε εφαρμογές όπως το Adobe Campaign Standard, θα πρέπει να ακολουθήσετε μερικά βήματα που περιγράφονται σε αυτό το άρθρο.</span><span class="sxs-lookup"><span data-stu-id="70678-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Διάγραμμα διεργασίας των βημάτων που περιγράφονται σε αυτό το άρθρο.":::

## <a name="prerequisites"></a><span data-ttu-id="70678-107">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="70678-107">Prerequisites</span></span>

-   <span data-ttu-id="70678-108">Άδεια χρήσης του Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="70678-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="70678-109">Άδεια χρήσης του Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="70678-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="70678-110">Άδεια χρήσης του Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="70678-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="70678-111">Λογαριασμό χώρου αποθήκευσης αντικειμένων Blob Azure</span><span class="sxs-lookup"><span data-stu-id="70678-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="70678-112">Επισκόπηση εκστρατείας</span><span class="sxs-lookup"><span data-stu-id="70678-112">Campaign Overview</span></span>

<span data-ttu-id="70678-113">Για να κατανοήσετε καλύτερα πώς μπορείτε να χρησιμοποιήσετε τμήματα από πληροφορίες κοινού στο Adobe Experience Platform, δείτε ένα φανταστικό δείγμα εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="70678-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="70678-114">Ας υποθέσουμε ότι η εταιρεία σας προσφέρει μια μηνιαία υπηρεσία βάσει συνδρομής στους πελάτες σας στις Ηνωμένες Πολιτείες.</span><span class="sxs-lookup"><span data-stu-id="70678-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="70678-115">Θέλετε να προσδιορίσετε τους πελάτες, των οποίων οι συνδρομές πρέπει να ανανεωθούν μέσα στις επόμενες οκτώ ημέρες, αλλά δεν έχουν ανανεώσει ακόμα τη συνδρομή τους.</span><span class="sxs-lookup"><span data-stu-id="70678-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="70678-116">Για να διατηρήσετε αυτούς τους πελάτες, θέλετε να τους στείλετε μια διαφημιστική προσφορά μέσω ηλεκτρονικού ταχυδρομείου, χρησιμοποιώντας το Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="70678-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="70678-117">Σε αυτό το παράδειγμα, θέλουμε να εκτελέσουμε την εκστρατεία ηλεκτρονικού ταχυδρομείου προώθησης μία φορά.</span><span class="sxs-lookup"><span data-stu-id="70678-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="70678-118">Αυτό το άρθρο δεν καλύπτει την περίπτωση χρήσης της εκτέλεσης της εκστρατείας περισσότερες από μία φορές.</span><span class="sxs-lookup"><span data-stu-id="70678-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="70678-119">Προσδιορισμός του κοινού-στόχου</span><span class="sxs-lookup"><span data-stu-id="70678-119">Identify your target audience</span></span>

<span data-ttu-id="70678-120">Στο σενάριό μας, υποθέτουμε ότι οι διευθύνσεις ηλεκτρονικού ταχυδρομείου των πελατών είναι διαθέσιμες στις πληροφορίες κοινού και οι διαφημιστικές προτιμήσεις τους αναλύθηκαν για τον προσδιορισμό μελών του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="70678-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="70678-121">Το [τμήμα που ορίσατε στις πληροφορίες κοινού](segments.md) ονομάζεται **ChurnProneCustomers** και σχεδιάζετε να στείλετε σε αυτούς τους πελάτες την προώθηση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="70678-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμημάτων με το τμήμα ChurnProneCustomers που δημιουργήθηκε.":::

<span data-ttu-id="70678-123">Το μήνυμα ηλεκτρονικού ταχυδρομείου της προσφοράς που θέλετε να στείλετε θα περιέχει τις πληροφορίες όνομα, επώνυμο και την ημερομηνία λήξης της συνδρομής του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="70678-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="70678-124">Ενημερώνει τους πελάτες σχετικά με την έκπτωση που θα έχουν, εάν ανανεώσουν τη συνδρομή τους πριν λήξει.</span><span class="sxs-lookup"><span data-stu-id="70678-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="70678-125">Εξαγωγή του κοινού-στόχου</span><span class="sxs-lookup"><span data-stu-id="70678-125">Export your target audience</span></span>

<span data-ttu-id="70678-126">Με προσδιορισμένο το κοινό-στόχο μας, μπορούμε να ρυθμίσουμε τις παραμέτρους εξαγωγής από πληροφορίες κοινού σε έναν λογαριασμό χώρου αποθήκευσης αντικειμένων blob Azure.</span><span class="sxs-lookup"><span data-stu-id="70678-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="70678-127">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="70678-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="70678-128">Στο πλακίδιο του **Χώρου αποθήκευσης αντικειμένων blob Azure**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="70678-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Πλακίδιο ρύθμισης παραμέτρων για χώρο αποθήκευσης αντικειμένων blob Azure.":::

1. <span data-ttu-id="70678-130">Δώστε ένα **εμφανιζόμενο όνομα** για αυτόν τον νέο προορισμό εξαγωγής και, στη συνέχεια, καταχωρήστε το **όνομα λογαριασμού**, το **κλειδί λογαριασμού** και το **κοντέινερ** του λογαριασμού χώρου αποθήκευσης αντικειμένων blob Azure στον οποίο θέλετε να εξαγάγετε το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="70678-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Στιγμιότυπο οθόνης της ρύθμισης παραμέτρων λογαριασμού χώρου αποθήκευσης."::: 

   - <span data-ttu-id="70678-132">Για να μάθετε περισσότερα σχετικά με το πώς μπορείτε να βρείτε το όνομα του λογαριασμού αποθήκευσηςAzure Blob και το κλειδί λογαριασμού, δείτε [Διαχείριση ρυθμίσεων λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="70678-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="70678-133">Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="70678-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="70678-134">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="70678-134">Select **Next**.</span></span>

1. <span data-ttu-id="70678-135">Επιλέξτε το τμήμα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="70678-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="70678-136">Σε αυτό το παράδειγμα, είναι **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="70678-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη επιλογής τμήματος με επιλεγμένο το τμήμα ChurnProneCustomers.":::

1. <span data-ttu-id="70678-138">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="70678-138">Select **Save**.</span></span>

<span data-ttu-id="70678-139">Αφού αποθηκεύσετε τον προορισμό εξαγωγής, τον βρίσκετε στην τοποθεσία **Admin** > **Εξαγωγές** > **Οι προορισμοί εξαγωγών μου**.</span><span class="sxs-lookup"><span data-stu-id="70678-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Στιγμιότυπο οθόνης με τη λίστα των εξαγωγών και του δείγματος τμήματος που έχει επισημανθεί.":::

<span data-ttu-id="70678-141">Τώρα μπορείτε να [εξαγάγετε το τμήμα κατ' απαίτηση](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="70678-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="70678-142">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md).</span><span class="sxs-lookup"><span data-stu-id="70678-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70678-143">Βεβαιωθείτε ότι ο αριθμός των καρτελών στο εξαχθέν τμήμα βρίσκεται εντός του επιτρεπόμενου ορίου της άδειας χρήσης που έχετε για το Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="70678-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="70678-144">Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ του χώρου αποθήκευσης αντικειμένων blob Azure που ρυθμίσατε παραπάνω.</span><span class="sxs-lookup"><span data-stu-id="70678-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="70678-145">Η παρακάτω διαδρομή φακέλου δημιουργείται αυτόματα στο κοντέινερ σας:</span><span class="sxs-lookup"><span data-stu-id="70678-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="70678-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="70678-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="70678-147">Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="70678-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="70678-148">Το *model.json* για τις οντότητες που έχουν εξαχθεί βρίσκεται στο επίπεδο *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="70678-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="70678-149">Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="70678-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="70678-150">Καθορισμός μοντέλου δεδομένων εμπειρίας (XDM) στο Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="70678-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="70678-151">Για να μπορούν να χρησιμοποιηθούν τα εξαχθέντα δεδομένα από τις πληροφορίες κοινού στο Adobe Experience Platform, πρέπει να ορίσουμε το σχήμα του μοντέλου δεδομένων εμπειρίας και [να ρυθμίσουμε τα δεδομένα για το προφίλ πελάτη σε πραγματικό χρόνο](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="70678-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="70678-152">Μάθετε [τι είναι το XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) και κατανοήστε τα [βασικά στοιχεία της σύνθεσης σχημάτων](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="70678-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="70678-153">Εισαγωγή δεδομένων στο Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="70678-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="70678-154">Τώρα που όλα είναι έτοιμα, θα πρέπει να εισαγάγετε τα προετοιμασμένα δεδομένα κοινού ααπό τις πληροφορίες κοινού στο Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="70678-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="70678-155">Πρώτα, [δημιουργήστε μια σύνδεση προέλευσης χώρου αποθήκευσης αντικειμένων Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="70678-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="70678-156">Αφού καθορίσετε τη σύνδεση προέλευσης, [ρυθμίστε τις παραμέτρους μιας ροής δεδομένων](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) για μια σύνδεση δέσμης χώρου αποθήκευσης cloud για την εισαγωγή της εξόδου του τμήματος από πληροφορίες κοινού στο Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="70678-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="70678-157">Δημιουργία ενός κοινού στο Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="70678-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="70678-158">Για να στείλουμε το μήνυμα ηλεκτρονικού ταχυδρομείου για αυτήν την εκστρατεία, θα χρησιμοποιήσουμε το Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="70678-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="70678-159">Μετά την εισαγωγή των δεδομένων στο Adobe Experience Platform, θα πρέπει να [δημιουργήσουμε ένα κοινό](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) στο Adobe Campaign Standard χρησιμοποιώντας τα δεδομένα στο Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="70678-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="70678-160">Μάθετε πώς να [χρησιμοποιείτε το εργαλείο δόμησης τμημάτων](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) στο Adobe Campaign Standard για να ορίσετε ένα κοινό με βάση τα δεδομένα στο Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="70678-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="70678-161">Δημιουργία και αποστολή του μηνύματος ηλεκτρονικού ταχυδρομείου χρησιμοποιώντας το Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="70678-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="70678-162">Δημιουργήστε το περιεχόμενο του μηνύματος ηλεκτρονικού ταχυδρομείου και, στη συνέχεια, [δοκιμάστε και στείλτε](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) το μήνυμα ηλεκτρονικού ταχυδρομείου σας.</span><span class="sxs-lookup"><span data-stu-id="70678-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Δείγμα μηνύματος ηλεκτρονικού ταχυδρομείου με προσφορά ανανέωσης από το Adobe Campaign Standard.":::