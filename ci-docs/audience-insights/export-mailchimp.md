---
title: Εξαγωγή δεδομένων Customer Insights στο Mailchimp
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124227"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="e1adf-103">Εξαγωγή τμημάτων στο Mailchimp (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="e1adf-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="e1adf-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στο Mailchimp για να δημιουργήσετε ενημερωτικά δελτία και εκστρατείες ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="e1adf-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e1adf-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="e1adf-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e1adf-106">Έχετε έναν [λογαριασμό Mailchimp](https://mailchimp.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="e1adf-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e1adf-107">Υπάρχουν υπάρχοντα κοινά στο Mailchimp και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="e1adf-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="e1adf-108">Για περισσότερες πληροφορίες, ανατρέξτε στα [ακροατήρια Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e1adf-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="e1adf-109">Έχετε [ρυθμίσει τμήματα](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e1adf-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e1adf-110">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="e1adf-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e1adf-111">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="e1adf-111">Known limitations</span></span>

- <span data-ttu-id="e1adf-112">Έως 1000000 προφίλ ανά εξαγωγή σε Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e1adf-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="e1adf-113">Η εξαγωγή στο Mailchimp περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="e1adf-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="e1adf-114">Η εξαγωγή τμημάτων με 1 εκ. προφίλ μπορεί να διαρκέσει έως τρεις ώρες.</span><span class="sxs-lookup"><span data-stu-id="e1adf-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="e1adf-115">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Mailchimp εξαρτάται και περιορίζεται στη σύμβασή σας με το Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e1adf-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="e1adf-116">Ρύθμιση σύνδεσης στο Mailchimp</span><span class="sxs-lookup"><span data-stu-id="e1adf-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="e1adf-117">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="e1adf-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e1adf-118">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Autopilot** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="e1adf-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="e1adf-119">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="e1adf-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e1adf-120">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="e1adf-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e1adf-121">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="e1adf-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e1adf-122">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="e1adf-122">Choose who can use this connection.</span></span> <span data-ttu-id="e1adf-123">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="e1adf-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e1adf-124">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e1adf-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e1adf-125">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="e1adf-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e1adf-126">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e1adf-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="e1adf-127">Επιλέξτε **Έλεγχος ταυτότητας με Mailchimp** και δώστε τα διαπιστευτήρια Mailchimp σας.</span><span class="sxs-lookup"><span data-stu-id="e1adf-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="e1adf-128">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e1adf-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e1adf-129">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="e1adf-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="e1adf-130">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="e1adf-130">Configure the connector</span></span>

<span data-ttu-id="e1adf-131">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="e1adf-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e1adf-132">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e1adf-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e1adf-133">Μεταβείτε στα **Δεδομένα**> **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="e1adf-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="e1adf-134">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="e1adf-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e1adf-135">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e1adf-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="e1adf-136">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="e1adf-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e1adf-137">Εισαγάγετε το **[Αναγνωριστικό κοινού Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="e1adf-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="e1adf-138">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="e1adf-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e1adf-139">Προαιρετικά, μπορείτε να εξαγάγετε μηνύματα **Όνομα** και **Επώνυμο** για να δημιουργήσετε πιο προσαρμοσμένα μηνύματα ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="e1adf-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="e1adf-140">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="e1adf-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e1adf-141">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="e1adf-141">Select the segments you want to export.</span></span> <span data-ttu-id="e1adf-142">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e1adf-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="e1adf-143">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="e1adf-143">Select **Save**.</span></span>

<span data-ttu-id="e1adf-144">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="e1adf-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e1adf-145">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1adf-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1adf-146">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e1adf-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e1adf-147">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="e1adf-147">Data privacy and compliance</span></span>

<span data-ttu-id="e1adf-148">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Mailchimp, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="e1adf-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e1adf-149">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Mailchimp πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="e1adf-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e1adf-150">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e1adf-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e1adf-151">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="e1adf-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
