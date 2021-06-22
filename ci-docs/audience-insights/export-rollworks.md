---
title: Εξαγωγή δεδομένων του Customer Insights στο RollWorks
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124089"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="01aeb-103">Εξαγωγή τμημάτων στο RollWorks (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="01aeb-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="01aeb-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο RollWorks και χρησιμοποιήστε τα για διαφήμιση.</span><span class="sxs-lookup"><span data-stu-id="01aeb-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="01aeb-105">Προϋποθέσεις για μια σύνδεση</span><span class="sxs-lookup"><span data-stu-id="01aeb-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="01aeb-106">Έχετε έναν [λογαριασμό RollWorks](https://www.rollworks.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="01aeb-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="01aeb-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="01aeb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="01aeb-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="01aeb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="01aeb-109">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="01aeb-109">Known limitations</span></span>

- <span data-ttu-id="01aeb-110">Μπορείτε να εξαγάγετε έως και 250.000 προφίλ ανά εξαγωγή στο RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="01aeb-111">Δεν μπορείτε να εξαγάγετε τμήματα με λιγότερα από 100 προφίλ στο RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="01aeb-112">Η εξαγωγή στο RollWorks περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="01aeb-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="01aeb-113">Η εξαγωγή έως 250.000 προφίλ στο RollWorks μπορεί να χρειαστεί έως και 10 λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="01aeb-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="01aeb-114">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο RollWorks εξαρτάται και περιορίζεται από τη σύμβαση με το RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="01aeb-115">Ρύθμιση σύνδεσης στο RollWorks</span><span class="sxs-lookup"><span data-stu-id="01aeb-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="01aeb-116">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="01aeb-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="01aeb-117">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **RollWorks** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="01aeb-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="01aeb-118">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="01aeb-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="01aeb-119">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="01aeb-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="01aeb-120">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="01aeb-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="01aeb-121">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="01aeb-121">Choose who can use this connection.</span></span> <span data-ttu-id="01aeb-122">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="01aeb-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="01aeb-123">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="01aeb-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="01aeb-124">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="01aeb-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="01aeb-125">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="01aeb-126">Επιλέξτε **Έλεγχος ταυτότητας με το RollWorks** και δώστε τα διαπιστευτήρια διαχειριστή σας για το RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="01aeb-127">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="01aeb-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="01aeb-128">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="01aeb-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="01aeb-129">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="01aeb-129">Configure an export</span></span>

<span data-ttu-id="01aeb-130">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="01aeb-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="01aeb-131">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="01aeb-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="01aeb-132">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="01aeb-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="01aeb-133">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="01aeb-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="01aeb-134">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="01aeb-135">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="01aeb-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="01aeb-136">Εισαγάγετε το **αναγνωριστικό διαφημιστή RollWorks** [Διαφημίσιμο RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="01aeb-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="01aeb-137">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="01aeb-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="01aeb-138">Απαιτείται η εξαγωγή τμημάτων στο RollWorks.</span><span class="sxs-lookup"><span data-stu-id="01aeb-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="01aeb-139">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="01aeb-139">Select the segments you want to export.</span></span> <span data-ttu-id="01aeb-140">Επιλέξτε ένα τμήμα με τουλάχιστον 100 μέλη.</span><span class="sxs-lookup"><span data-stu-id="01aeb-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="01aeb-141">Δεν μπορείτε να εξαγάγετε μικρότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="01aeb-141">You can't export smaller segments.</span></span> <span data-ttu-id="01aeb-142">Επιπλέον, το μέγιστο μέγεθος ενός τμήματος προς εξαγωγή είναι 250.000 μέλη ανά εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="01aeb-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="01aeb-143">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="01aeb-143">Select **Save**.</span></span>

<span data-ttu-id="01aeb-144">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="01aeb-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="01aeb-145">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01aeb-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="01aeb-146">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="01aeb-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="01aeb-147">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="01aeb-147">Data privacy and compliance</span></span>

<span data-ttu-id="01aeb-148">Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο RollWorks, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="01aeb-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="01aeb-149">Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το RollWorks θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="01aeb-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="01aeb-150">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="01aeb-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="01aeb-151">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="01aeb-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
