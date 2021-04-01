---
title: Εξαγωγή δεδομένων του Customer Insights στο Adobe Campaign Standard
description: Μάθετε πώς να χρησιμοποιείτε τμήματα πληροφοριών κοινού στο Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596315"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="15209-103">Χρησιμοποιήστε τμήματα Customer Insights στο Adobe Campaign Standard (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="15209-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="15209-104">Ως χρήστης των πληροφοριών κοινού για Dynamics 365 Customer Insights, ενδέχεται να έχετε δημιουργήσει τμήματα για να κάνετε τις εκστρατείες μάρκετινγκ πιο αποτελεσματικές στοχεύοντας σε σχετικά κοινά.</span><span class="sxs-lookup"><span data-stu-id="15209-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="15209-105">Για να χρησιμοποιήσετε ένα τμήμα από πληροφορίες κοινού στο Adobe Experience Platform και σε εφαρμογές όπως το Adobe Campaign Standard, θα πρέπει να ακολουθήσετε μερικά βήματα που περιγράφονται σε αυτό το άρθρο.</span><span class="sxs-lookup"><span data-stu-id="15209-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Διάγραμμα διεργασίας των βημάτων που περιγράφονται σε αυτό το άρθρο.":::

## <a name="prerequisites"></a><span data-ttu-id="15209-107">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="15209-107">Prerequisites</span></span>

-   <span data-ttu-id="15209-108">Άδεια χρήσης του Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="15209-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="15209-109">Άδεια χρήσης του Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="15209-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="15209-110">Λογαριασμό χώρου αποθήκευσης αντικειμένων Blob Azure</span><span class="sxs-lookup"><span data-stu-id="15209-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="15209-111">Επισκόπηση εκστρατείας</span><span class="sxs-lookup"><span data-stu-id="15209-111">Campaign Overview</span></span>

<span data-ttu-id="15209-112">Για να κατανοήσετε καλύτερα πώς μπορείτε να χρησιμοποιήσετε τμήματα από πληροφορίες κοινού στο Adobe Experience Platform, δείτε ένα φανταστικό δείγμα εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="15209-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="15209-113">Ας υποθέσουμε ότι η εταιρεία σας προσφέρει μια μηνιαία υπηρεσία βάσει συνδρομής στους πελάτες σας στις Ηνωμένες Πολιτείες.</span><span class="sxs-lookup"><span data-stu-id="15209-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="15209-114">Θέλετε να προσδιορίσετε τους πελάτες, των οποίων οι συνδρομές πρέπει να ανανεωθούν μέσα στις επόμενες οκτώ ημέρες, αλλά δεν έχουν ανανεώσει ακόμα τη συνδρομή τους.</span><span class="sxs-lookup"><span data-stu-id="15209-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="15209-115">Για να διατηρήσετε αυτούς τους πελάτες, θέλετε να τους στείλετε μια διαφημιστική προσφορά μέσω ηλεκτρονικού ταχυδρομείου, χρησιμοποιώντας το Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="15209-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="15209-116">Σε αυτό το παράδειγμα, θέλουμε να εκτελέσουμε την εκστρατεία ηλεκτρονικού ταχυδρομείου προώθησης μία φορά.</span><span class="sxs-lookup"><span data-stu-id="15209-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="15209-117">Αυτό το άρθρο δεν καλύπτει την περίπτωση χρήσης της εκτέλεσης της εκστρατείας περισσότερες από μία φορές.</span><span class="sxs-lookup"><span data-stu-id="15209-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="15209-118">Ωστόσο, οι πληροφορίες κοινού και το Adobe Campaign Standard μπορούν να ρυθμιστούν ώστε να λειτουργούν και για ένα επαναλαμβανόμενο σενάριο εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="15209-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="15209-119">Προσδιορισμός του κοινού-στόχου</span><span class="sxs-lookup"><span data-stu-id="15209-119">Identify your target audience</span></span>

<span data-ttu-id="15209-120">Στο σενάριό μας, υποθέτουμε ότι οι διευθύνσεις ηλεκτρονικού ταχυδρομείου των πελατών είναι διαθέσιμες στις πληροφορίες κοινού και οι διαφημιστικές προτιμήσεις τους αναλύθηκαν για τον προσδιορισμό μελών του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="15209-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="15209-121">Το [τμήμα που ορίσατε στις πληροφορίες κοινού](segments.md) ονομάζεται **ChurnProneCustomers** και σχεδιάζετε να στείλετε σε αυτούς τους πελάτες την προώθηση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="15209-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμημάτων με το τμήμα ChurnProneCustomers που δημιουργήθηκε.":::

<span data-ttu-id="15209-123">Το μήνυμα ηλεκτρονικού ταχυδρομείου της προσφοράς που θέλετε να στείλετε θα περιέχει τις πληροφορίες όνομα, επώνυμο και την ημερομηνία λήξης της συνδρομής του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="15209-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="15209-124">Ενημερώνει τους πελάτες σχετικά με την έκπτωση που θα έχουν, εάν ανανεώσουν τη συνδρομή τους πριν λήξει.</span><span class="sxs-lookup"><span data-stu-id="15209-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="15209-125">Εξαγωγή του κοινού-στόχου</span><span class="sxs-lookup"><span data-stu-id="15209-125">Export your target audience</span></span>

<span data-ttu-id="15209-126">Με προσδιορισμένο το κοινό-στόχο μας, μπορούμε να ρυθμίσουμε τις παραμέτρους εξαγωγής από πληροφορίες κοινού σε έναν λογαριασμό χώρου αποθήκευσης αντικειμένων blob Azure.</span><span class="sxs-lookup"><span data-stu-id="15209-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="15209-127">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="15209-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="15209-128">Στο πλακίδιο **Adobe Campaign**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="15209-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Πλακίδιο ρύθμισης παραμέτρων για το Adobe Campaign Standard.":::

1. <span data-ttu-id="15209-130">Δώστε ένα **εμφανιζόμενο όνομα** για αυτόν τον νέο προορισμό εξαγωγής και, στη συνέχεια, καταχωρήστε το **όνομα λογαριασμού**, το **κλειδί λογαριασμού** και το **κοντέινερ** του λογαριασμού χώρου αποθήκευσης αντικειμένων blob Azure στον οποίο θέλετε να εξαγάγετε το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="15209-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Στιγμιότυπο οθόνης της ρύθμισης παραμέτρων λογαριασμού χώρου αποθήκευσης."::: 

   - <span data-ttu-id="15209-132">Για να μάθετε περισσότερα σχετικά με το πώς μπορείτε να βρείτε το όνομα του λογαριασμού αποθήκευσηςAzure Blob και το κλειδί λογαριασμού, δείτε [Διαχείριση ρυθμίσεων λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="15209-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="15209-133">Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="15209-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="15209-134">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="15209-134">Select **Next**.</span></span>

1. <span data-ttu-id="15209-135">Επιλέξτε το τμήμα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="15209-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="15209-136">Σε αυτό το παράδειγμα, είναι **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="15209-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη επιλογής τμήματος με επιλεγμένο το τμήμα ChurnProneCustomers.":::

1. <span data-ttu-id="15209-138">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="15209-138">Select **Next**.</span></span>

1. <span data-ttu-id="15209-139">Τώρα αντιστοιχουμε τα πεδία **προέλευσης** από το τμήμα πληροφοριών κοινού στα ονόματα πεδίων **προορισμού** του σχήματος προφίλ "Adobe Campaign Standard".</span><span class="sxs-lookup"><span data-stu-id="15209-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Αντιστοίχιση πεδίου για τη σύνδεση Adobe Campaign Standard.":::

   <span data-ttu-id="15209-141">Εάν θέλετε να προσθέσετε περισσότερα χαρακτηριστικά, επιλέξτε **Προσθήκη χαρακτηριστικού**.</span><span class="sxs-lookup"><span data-stu-id="15209-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="15209-142">Το όνομα προορισμού μπορεί να είναι διαφορετικό από το όνομα του πεδίου προέλευσης, ώστε να εξακολουθείτε να μπορείτε να αντιστοιχίσετε έξοδο τμημάτων από πληροφορίες κοινού στο Adobe Campaign Standard, εάν τα πεδία δεν έχουν το ίδιο όνομα στα δύο συστήματα.</span><span class="sxs-lookup"><span data-stu-id="15209-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="15209-143">Η διεύθυνση ηλεκτρονικού ταχυδρομείου χρησιμοποιείται ως πεδίο ταυτότητας, αλλά μπορείτε να χρησιμοποιήσετε οποιοδήποτε άλλο αναγνωριστικό από το προφίλ πελάτη πληροφοριών κοινού για την αντιστοίχιση δεδομένων στο Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="15209-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="15209-144">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="15209-144">Select **Save**.</span></span>

<span data-ttu-id="15209-145">Αφού αποθηκεύσετε τον προορισμό εξαγωγής, τον βρίσκετε στην τοποθεσία **Admin** > **Εξαγωγές** > **Οι προορισμοί εξαγωγών μου**.</span><span class="sxs-lookup"><span data-stu-id="15209-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Στιγμιότυπο οθόνης με τη λίστα των εξαγωγών και του δείγματος τμήματος που έχει επισημανθεί.":::

<span data-ttu-id="15209-147">Τώρα μπορείτε να [εξαγάγετε το τμήμα κατ' απαίτηση](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="15209-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="15209-148">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md).</span><span class="sxs-lookup"><span data-stu-id="15209-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="15209-149">Βεβαιωθείτε ότι ο αριθμός των καρτελών στο εξαχθέν τμήμα βρίσκεται εντός του επιτρεπόμενου ορίου της άδειας χρήσης που έχετε για το Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="15209-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="15209-150">Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ του χώρου αποθήκευσης αντικειμένων blob Azure που ρυθμίσατε παραπάνω.</span><span class="sxs-lookup"><span data-stu-id="15209-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="15209-151">Η παρακάτω διαδρομή φακέλου δημιουργείται αυτόματα στο κοντέινερ σας:</span><span class="sxs-lookup"><span data-stu-id="15209-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="15209-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="15209-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="15209-153">Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="15209-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="15209-154">Ρύθμιση παραμέτρων Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="15209-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="15209-155">Όταν εξάγεται ένα τμήμα από πληροφορίες κοινού, περιέχει τις στήλες που επιλέξατε κατά τον ορισμό του προορισμού εξαγωγής στο προηγούμενο βήμα.</span><span class="sxs-lookup"><span data-stu-id="15209-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="15209-156">Αυτά τα δεδομένα μπορούν να χρησιμοποιηθούν για [τη δημιουργία προφίλ στο Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="15209-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="15209-157">Για να χρησιμοποιήσετε το τμήμα στο Adobe Campaign Standard, θα πρέπει να επεκτείνουμε το σχήμα προφίλ στο Adobe Campaign Standard και να συμπεριλάβουμε δύο επιπλέον πεδία.</span><span class="sxs-lookup"><span data-stu-id="15209-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="15209-158">Μάθετε πώς να [επεκτείνετε τον πόρο προφίλ](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) με νέα πεδία στο Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="15209-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="15209-159">Στο παράδειγμά μας, τα πεδία αυτά είναι *Όνομα τμήματος και Ημερομηνία τμήματος (προαιρετικά).*</span><span class="sxs-lookup"><span data-stu-id="15209-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="15209-160">Θα χρησιμοποιήσουμε αυτά τα πεδία για να εντοπίσουμε τα προφίλ στο Adobe Campaign Standard που θέλουμε να στοχεύσετε για αυτήν την εκστρατεία.</span><span class="sxs-lookup"><span data-stu-id="15209-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="15209-161">Εάν δεν υπάρχουν άλλες καρτέλες στο Adobe Campaign Standard, εκτός από τις καρτέλες που πρόκειται να εισαγάγετε, μπορείτε να παραλείψετε αυτό το βήμα.</span><span class="sxs-lookup"><span data-stu-id="15209-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="15209-162">Εισαγωγή δεδομένων στο Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="15209-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="15209-163">Τώρα που όλα είναι έτοιμα, θα πρέπει να εισαγάγετε τα προετοιμασμένα δεδομένα κοινού ααπό τις πληροφορίες κοινού στο Adobe Campaign Standard για τη δημιουργία προφίλ.</span><span class="sxs-lookup"><span data-stu-id="15209-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="15209-164">Μάθετε [πώς να εισάγετε προφίλ στο Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) χρησιμοποιώντας μια ροή εργασιών.</span><span class="sxs-lookup"><span data-stu-id="15209-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="15209-165">Η ροή εργασιών εισαγωγής στην παρακάτω εικόνα έχει ρυθμιστεί ώστε να εκτελείται κάθε 8 ώρες και αναζητά τμήματα πληροφοριών κοινού που έχουν εξαχθεί (αρχείο .csv στον χώρο αποθήκευσης αντικειμένων Blob Azure).</span><span class="sxs-lookup"><span data-stu-id="15209-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="15209-166">Η ροή εργασιών εξάγει το περιεχόμενο του αρχείου .csv σε μια καθορισμένη σειρά στηλών.</span><span class="sxs-lookup"><span data-stu-id="15209-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="15209-167">Αυτή η ροή εργασιών έχει δημιουργηθεί για την εκτέλεση βασικού χειρισμού σφαλμάτων και τη διασφάλιση ότι κάθε καρτέλα έχει μια διεύθυνση ηλεκτρονικού ταχυδρομείου πριν από την ανασύνθεση των δεδομένων στο Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="15209-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="15209-168">Η ροή εργασιών εξάγει επίσης το όνομα του τμήματος από το όνομα αρχείου πριν να μετατραπεί σε δεδομένα προφίλ ACS.</span><span class="sxs-lookup"><span data-stu-id="15209-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Στιγμιότυπο οθόνης μιας ροής εργασιών εισαγωγής στο περιβάλλον εργασίας χρήστη Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="15209-170">Ανάκτηση του κοινού στο Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="15209-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="15209-171">Μετά την εισαγωγή των δεδομένων στο Adobe Campaign Standard, [μπορείτε να δημιουργήσετε μια ροή εργασιών](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) και [να υποβάλετε ερωτήματα](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) στους πελάτες με βάση το *όνομα τμήματος* και την *ημερομηνία τμήματος*, για να επιλέξουν τα προφίλ που έχουν αναγνωριστεί για το δείγμα εκστρατείας μας.</span><span class="sxs-lookup"><span data-stu-id="15209-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="15209-172">Δημιουργία και αποστολή του μηνύματος ηλεκτρονικού ταχυδρομείου χρησιμοποιώντας το Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="15209-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="15209-173">Δημιουργήστε το περιεχόμενο του μηνύματος ηλεκτρονικού ταχυδρομείου και, στη συνέχεια, [δοκιμάστε και στείλτε](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) το μήνυμα ηλεκτρονικού ταχυδρομείου σας.</span><span class="sxs-lookup"><span data-stu-id="15209-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Δείγμα μηνύματος ηλεκτρονικού ταχυδρομείου με προσφορά ανανέωσης από το Adobe Campaign Standard.":::