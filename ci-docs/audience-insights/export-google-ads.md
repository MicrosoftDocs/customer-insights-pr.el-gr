---
title: Εξαγωγή δεδομένων Customer Insights στο Google Ads
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759693"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="84c17-103">Εξαγωγή τμημάτων στο Google Ads (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="84c17-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="84c17-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στη λίστα κοινού του Google Ads και χρησιμοποιήστε τα για διαφήμιση στο Google Search, Gmail, YouTube και Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="84c17-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="84c17-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="84c17-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="84c17-106">Έχετε έναν [λογαριασμό Google Ads](https://ads.google.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="84c17-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="84c17-107">Έχετε ένα [εγκεκριμένο διακριτικό προγραμματιστή Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="84c17-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="84c17-108">Πληροίτε τις απαιτήσεις της [Πολιτικής αντιστοίχισης πελατών](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="84c17-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="84c17-109">Πληροίτε τις απαιτήσεις των [μεγεθών λίστας εκ νέου μάρκετινγκ](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="84c17-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="84c17-110">Υπάρχουν υπάρχοντα κοινά στο Google Ads και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="84c17-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="84c17-111">Για περισσότερες πληροφορίες, ανατρέξτε στα [ακροατήρια Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="84c17-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="84c17-112">Έχετε [ρυθμίσει τμήματα](segments.md)</span><span class="sxs-lookup"><span data-stu-id="84c17-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="84c17-113">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν πεδία που αντιπροσωπεύουν μια διεύθυνση ηλεκτρονικού ταχυδρομείου, όνομα και επώνυμο</span><span class="sxs-lookup"><span data-stu-id="84c17-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="84c17-114">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="84c17-114">Known limitations</span></span>

- <span data-ttu-id="84c17-115">Έως 1000000 προφίλ ανά εξαγωγή στο Google Ads.</span><span class="sxs-lookup"><span data-stu-id="84c17-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="84c17-116">Η εξαγωγή στο Google Ads περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="84c17-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="84c17-117">Η εξαγωγή τμημάτων με συνολικά 1 εκατομμύριο προφίλ μπορεί να διαρκέσει έως και πέντε λεπτά λόγω περιορισμών από την πλευρά του παρόχου.</span><span class="sxs-lookup"><span data-stu-id="84c17-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="84c17-118">Η αντιστοίχιση στο Google Ads μπορεί να διαρκέσει έως και 48 ώρες.</span><span class="sxs-lookup"><span data-stu-id="84c17-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="84c17-119">Ρύθμιση σύνδεσης στο Google Ads</span><span class="sxs-lookup"><span data-stu-id="84c17-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="84c17-120">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="84c17-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="84c17-121">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Google Ads** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="84c17-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="84c17-122">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="84c17-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="84c17-123">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="84c17-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="84c17-124">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="84c17-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="84c17-125">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="84c17-125">Choose who can use this connection.</span></span> <span data-ttu-id="84c17-126">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="84c17-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="84c17-127">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="84c17-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="84c17-128">Εισαγάγετε το **[αναγνωριστικό πελάτη Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="84c17-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="84c17-129">Καταγράψτε το **[διακριτικό προγραμματιστή που ενέκρινε το Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="84c17-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="84c17-130">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="84c17-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="84c17-131">Επιλέξτε **Έλεγχος ταυτότητας με το Google Ads** και δώστε τα διαπιστευτήρια Google Ads.</span><span class="sxs-lookup"><span data-stu-id="84c17-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="84c17-132">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84c17-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="84c17-133">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="84c17-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="84c17-134">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="84c17-134">Configure an export</span></span>

<span data-ttu-id="84c17-135">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="84c17-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="84c17-136">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="84c17-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="84c17-137">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="84c17-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="84c17-138">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="84c17-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="84c17-139">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Google Ads.</span><span class="sxs-lookup"><span data-stu-id="84c17-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="84c17-140">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="84c17-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="84c17-141">Πληκτρολογήστε το **[αναγνωριστικό κοινού Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** και επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση με το Google Ads.</span><span class="sxs-lookup"><span data-stu-id="84c17-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="84c17-142">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="84c17-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="84c17-143">Επαναλάβετε τα ίδια βήματα για τα πεδία **'Ονομα** και **Επώνυμο**.</span><span class="sxs-lookup"><span data-stu-id="84c17-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="84c17-144">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="84c17-144">Select the segments you want to export.</span></span> <span data-ttu-id="84c17-145">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Google Ads.</span><span class="sxs-lookup"><span data-stu-id="84c17-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="84c17-146">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="84c17-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="84c17-147">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="84c17-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="84c17-148">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="84c17-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84c17-149">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="84c17-149">Data privacy and compliance</span></span>

<span data-ttu-id="84c17-150">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Google Ads, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="84c17-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84c17-151">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Google Ads πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="84c17-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="84c17-152">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84c17-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="84c17-153">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="84c17-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
