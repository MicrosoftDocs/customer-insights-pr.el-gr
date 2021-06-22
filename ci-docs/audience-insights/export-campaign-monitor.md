---
title: Εξαγωγή δεδομένων του Customer Insights στο Campaign Monitor
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124181"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="a3513-103">Εξαγωγή τμημάτων στο Campaign Monitor (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="a3513-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="a3513-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Campaign Monitor και χρησιμοποιήστε τα για δραστηριότητες μάρκετινγκ.</span><span class="sxs-lookup"><span data-stu-id="a3513-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3513-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="a3513-105">Prerequisites</span></span>

-   <span data-ttu-id="a3513-106">Έχετε έναν [λογαριασμό Campaign Monitor](https://www.campaignmonitor.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="a3513-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a3513-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="a3513-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a3513-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="a3513-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a3513-109">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="a3513-109">Known limitations</span></span>

- <span data-ttu-id="a3513-110">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ ανά εξαγωγή στο Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a3513-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="a3513-111">Η εξαγωγή στο Campaign Monitor περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="a3513-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="a3513-112">Η εξαγωγή έως 1 εκατομμυρίων προφίλ στο Campaign Monitor μπορεί να χρειαστεί έως και 20 λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="a3513-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="a3513-113">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στην Εποπτεία εκστρατείας εξαρτάται και περιορίζεται από τη σύμβαση με την Εποπτεία εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="a3513-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="a3513-114">Ρύθμιση σύνδεσης στο Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="a3513-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="a3513-115">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="a3513-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a3513-116">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Campaign Monitor** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="a3513-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="a3513-117">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="a3513-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a3513-118">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="a3513-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a3513-119">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="a3513-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a3513-120">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="a3513-120">Choose who can use this connection.</span></span> <span data-ttu-id="a3513-121">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="a3513-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a3513-122">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a3513-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a3513-123">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="a3513-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a3513-124">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a3513-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="a3513-125">Επιλέξτε **Έλεγχος ταυτότητας με το Campaign Monitor** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a3513-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="a3513-126">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3513-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a3513-127">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="a3513-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a3513-128">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="a3513-128">Configure an export</span></span>

<span data-ttu-id="a3513-129">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="a3513-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a3513-130">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a3513-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a3513-131">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="a3513-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3513-132">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="a3513-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a3513-133">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a3513-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="a3513-134">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="a3513-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a3513-135">Εισαγάγετε το [**Αναγνωριστικό λίστας Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="a3513-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="a3513-136">[Δημιουργήστε το κλειδί API](https://www.campaignmonitor.com/api/getting-started/) από τις **Ρυθμίσεις λογαριασμού** στο Campaign Monitor πρώτα για να προβάλετε το αναγνωριστικό λίστας API.</span><span class="sxs-lookup"><span data-stu-id="a3513-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="a3513-137">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="a3513-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a3513-138">Απαιτείται η εξαγωγή τμημάτων στο Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a3513-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="a3513-139">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="a3513-139">Select **Save**.</span></span>

<span data-ttu-id="a3513-140">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="a3513-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a3513-141">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a3513-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a3513-142">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a3513-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a3513-143">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="a3513-143">Data privacy and compliance</span></span>

<span data-ttu-id="a3513-144">Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο Campaign Monitor, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="a3513-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a3513-145">Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το Campaign Monitor θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="a3513-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a3513-146">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a3513-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a3513-147">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="a3513-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
