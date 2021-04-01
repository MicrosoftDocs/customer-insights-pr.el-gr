---
title: Εξαγωγή δεδομένων Customer Insights στο Google Ads
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598247"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="68b5d-103">Σύνδεση για το Google Ads (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="68b5d-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="68b5d-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στη λίστα κοινού του Google Ads και χρησιμοποιήστε τα για διαφήμιση στο Google Search, Gmail, YouTube και Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="68b5d-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="68b5d-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="68b5d-105">Prerequisites</span></span>

-   <span data-ttu-id="68b5d-106">Έχετε έναν [λογαριασμό Google Ads](https://ads.google.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="68b5d-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="68b5d-107">Υπάρχουν υπάρχοντα κοινά στο Google Ads και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="68b5d-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="68b5d-108">Για περισσότερες πληροφορίες, ανατρέξτε στα [ακροατήρια Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="68b5d-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="68b5d-109">Έχετε [ρυθμίσει τμήματα](segments.md)</span><span class="sxs-lookup"><span data-stu-id="68b5d-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="68b5d-110">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν πεδία που αντιπροσωπεύουν μια διεύθυνση ηλεκτρονικού ταχυδρομείου, όνομα και επώνυμο</span><span class="sxs-lookup"><span data-stu-id="68b5d-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="68b5d-111">Σύνδεση στο Google Ads</span><span class="sxs-lookup"><span data-stu-id="68b5d-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="68b5d-112">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="68b5d-113">Στο **Google Ads**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="68b5d-114">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="68b5d-115">Εισαγάγετε το **[αναγνωριστικό πελάτη Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="68b5d-116">Καταγράψτε το **[διακριτικό προγραμματιστή που ενέκρινε το Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="68b5d-117">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68b5d-118">Πληκτρολογήστε το **[αναγνωριστικό κοινού Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** και επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση με το Google Ads.</span><span class="sxs-lookup"><span data-stu-id="68b5d-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="68b5d-119">Επιλέξτε **Έλεγχος ταυτότητας με το Google Ads** και δώστε τα διαπιστευτήρια Google Ads.</span><span class="sxs-lookup"><span data-stu-id="68b5d-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="68b5d-120">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68b5d-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Εξαγωγή στιγμιότυπου οθόνης για σύνδεση Google Ads":::

1. <span data-ttu-id="68b5d-122">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="68b5d-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="68b5d-123">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="68b5d-123">Configure the connector</span></span>

1. <span data-ttu-id="68b5d-124">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="68b5d-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="68b5d-125">Επαναλάβετε τα ίδια βήματα για τα πεδία **'Ονομα** και **Επώνυμο**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="68b5d-126">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="68b5d-126">Select the segments you want to export.</span></span> <span data-ttu-id="68b5d-127">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Google Ads.</span><span class="sxs-lookup"><span data-stu-id="68b5d-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="68b5d-128">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="68b5d-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="68b5d-129">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="68b5d-129">Export the data</span></span>

<span data-ttu-id="68b5d-130">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="68b5d-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="68b5d-131">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68b5d-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68b5d-132">Στο Google Ads, μπορείτε πλέον να βρείτε τα τμήματά σας στα [ακροατήρια Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="68b5d-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68b5d-133">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="68b5d-133">Known limitations</span></span>

- <span data-ttu-id="68b5d-134">Έως 1000000 προφίλ ανά εξαγωγή στο Google Ads.</span><span class="sxs-lookup"><span data-stu-id="68b5d-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="68b5d-135">Η εξαγωγή στο Google Ads περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="68b5d-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="68b5d-136">Η εξαγωγή τμημάτων με συνολικά 1 εκατομμύριο προφίλ μπορεί να διαρκέσει έως και πέντε λεπτά λόγω περιορισμών από την πλευρά του παρόχου.</span><span class="sxs-lookup"><span data-stu-id="68b5d-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="68b5d-137">Η αντιστοίχιση στο Google Ads μπορεί να διαρκέσει έως και 48 ώρες.</span><span class="sxs-lookup"><span data-stu-id="68b5d-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68b5d-138">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="68b5d-138">Data privacy and compliance</span></span>

<span data-ttu-id="68b5d-139">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Google Ads, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="68b5d-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68b5d-140">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Google Ads πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="68b5d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="68b5d-141">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68b5d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68b5d-142">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="68b5d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]