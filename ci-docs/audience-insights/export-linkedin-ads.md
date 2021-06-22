---
title: Εξαγωγή δεδομένων του Customer Insights στο LinkedIn Ads
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124494"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="82d95-103">Εξαγωγή τμημάτων στο LinkedIn Ads (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="82d95-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="82d95-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο LinkedIn Ads, για να δημιουργήσετε αντιστοιχισμένο κοινό.</span><span class="sxs-lookup"><span data-stu-id="82d95-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="82d95-105">Χρησιμοποιήστε τα αντιστοιχισμένο κοινό για στόχευση εταιρειών και στόχευση επαφών.</span><span class="sxs-lookup"><span data-stu-id="82d95-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="82d95-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="82d95-106">Prerequisites</span></span>

-   <span data-ttu-id="82d95-107">Έχετε έναν [λογαριασμό LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="82d95-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="82d95-108">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="82d95-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="82d95-109">Τα προφίλ πελατών στα τμήματα που έχουν εξαχθεί περιέχουν ένα πεδίο με μια διεύθυνση email.</span><span class="sxs-lookup"><span data-stu-id="82d95-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="82d95-110">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="82d95-110">Known limitations</span></span>

- <span data-ttu-id="82d95-111">Μπορείτε να εξαγάγετε έως και 100 χιλιάδες προφίλ ανά εξαγωγή στο LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="82d95-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="82d95-112">Η εξαγωγή στο LinkedIn Ads περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="82d95-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="82d95-113">Η εξαγωγή έως 100 χιλιάδων προφίλ στο LinkedIn Ads μπορεί να χρειαστεί έως και 10 λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="82d95-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="82d95-114">Ρυθμίστε τη σύνδεση στο LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="82d95-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="82d95-115">Στις πληροφορίες κοινού, μεταβείτε στο **Διαχειριστής** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="82d95-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="82d95-116">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **LinkedIn Ads** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="82d95-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="82d95-117">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="82d95-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="82d95-118">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="82d95-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="82d95-119">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="82d95-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="82d95-120">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="82d95-120">Choose who can use this connection.</span></span> <span data-ttu-id="82d95-121">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="82d95-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="82d95-122">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="82d95-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="82d95-123">Καταχωρίστε το [Αναγνωριστικό λογαριασμού LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="82d95-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="82d95-124">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="82d95-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="82d95-125">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="82d95-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="82d95-126">Επιλέξτε **Έλεγχος ταυτότητας με το LinkedIn** και καταχωρίστε τα διαπιστευτήρια διαχειριστή για το LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="82d95-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="82d95-127">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82d95-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="82d95-128">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="82d95-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="82d95-129">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="82d95-129">Configure an export</span></span>

<span data-ttu-id="82d95-130">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="82d95-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="82d95-131">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="82d95-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="82d95-132">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="82d95-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="82d95-133">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="82d95-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="82d95-134">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="82d95-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="82d95-135">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="82d95-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="82d95-136">Επιλέξτε αν θέλετε να εξαγάγετε δεδομένα για να κάνετε [στόχευση επαφών](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ή [στόχευση εταιρείας](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) στο LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="82d95-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="82d95-137">Στην ενότητα **Αντιστοίχιση δεδομένων**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αναπαριστά τη διεύθυνση email ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="82d95-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="82d95-138">Απαιτείται για την εξαγωγή τμημάτων στο LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="82d95-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="82d95-139">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="82d95-139">Select the segments you want to export.</span></span> <span data-ttu-id="82d95-140">Τα κοινά που έχουν αντιστοιχιστεί στο LinkedIn Campaign Manager θα δημιουργηθούν αυτόματα με το όνομα των τμημάτων που επιλέξατε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="82d95-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="82d95-141">Κάθε τμήμα θα έχει ως αποτέλεσμα ένα ξεχωριστό αντιστοιχισμένο κοινό.</span><span class="sxs-lookup"><span data-stu-id="82d95-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="82d95-142">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="82d95-142">Select **Save**.</span></span>

<span data-ttu-id="82d95-143">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="82d95-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="82d95-144">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="82d95-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="82d95-145">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="82d95-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="82d95-146">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="82d95-146">Data privacy and compliance</span></span>

<span data-ttu-id="82d95-147">Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο LinkedIn Ads, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="82d95-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="82d95-148">Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το LinkedIn Ads καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="82d95-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="82d95-149">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="82d95-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="82d95-150">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψει τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="82d95-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
