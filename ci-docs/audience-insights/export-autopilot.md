---
title: Εξαγωγή δεδομένων Customer Insights στο Autopilot
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760143"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="46ccb-103">Εξαγωγή τμημάτων στο Autopilot (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="46ccb-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="46ccb-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στο Autopilot και χρησιμοποιήστε τα για μάρκετινγκ ηλεκτρονικού ταχυδρομείου στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="46ccb-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="46ccb-105">Προϋποθέσεις για μια σύνδεση</span><span class="sxs-lookup"><span data-stu-id="46ccb-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="46ccb-106">Έχετε έναν [λογαριασμό Autopilot](https://www.autopilothq.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="46ccb-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="46ccb-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="46ccb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="46ccb-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="46ccb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="46ccb-109">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="46ccb-109">Known limitations</span></span>

- <span data-ttu-id="46ccb-110">Μπορείτε να εξαγάγετε έως και 100.000 προφίλ συνολικά στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="46ccb-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="46ccb-111">Η εξαγωγή στο Autopilot περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="46ccb-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="46ccb-112">Η εξαγωγή έως και 100.000 προφίλ στο Autopilot μπορεί να διαρκέσει έως και λίγες ώρες για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="46ccb-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="46ccb-113">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Autopilot εξαρτάται και περιορίζεται στη σύμβασή σας με το Autopilot.</span><span class="sxs-lookup"><span data-stu-id="46ccb-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="46ccb-114">Ρύθμιση σύνδεση στο Autopilot</span><span class="sxs-lookup"><span data-stu-id="46ccb-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="46ccb-115">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="46ccb-116">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Autopilot** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="46ccb-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="46ccb-117">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="46ccb-118">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46ccb-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="46ccb-119">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="46ccb-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="46ccb-120">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46ccb-120">Choose who can use this connection.</span></span> <span data-ttu-id="46ccb-121">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="46ccb-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="46ccb-122">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="46ccb-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="46ccb-123">Πληκτρολογήστε το [κλειδί API του Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="46ccb-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="46ccb-124">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46ccb-125">Επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="46ccb-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="46ccb-126">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46ccb-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="46ccb-127">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46ccb-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="46ccb-128">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="46ccb-128">Configure an export</span></span>

<span data-ttu-id="46ccb-129">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="46ccb-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="46ccb-130">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="46ccb-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="46ccb-131">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="46ccb-132">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="46ccb-133">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Autopilot.</span><span class="sxs-lookup"><span data-stu-id="46ccb-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="46ccb-134">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="46ccb-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="46ccb-135">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="46ccb-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="46ccb-136">Επαναλάβετε τα ίδια βήματα για άλλα προαιρετικά πεδία, όπως **Όνομα**, **Επώνυμο**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="46ccb-137">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="46ccb-137">Select the segments you want to export.</span></span> <span data-ttu-id="46ccb-138">**Συνιστούμε ιδιαίτερα να μην εξάγετε περισσότερα από 100.000 προφίλ πελατών συνολικά** στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="46ccb-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="46ccb-139">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="46ccb-139">Select **Save**.</span></span>

<span data-ttu-id="46ccb-140">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="46ccb-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="46ccb-141">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="46ccb-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="46ccb-142">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="46ccb-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46ccb-143">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="46ccb-143">Data privacy and compliance</span></span>

<span data-ttu-id="46ccb-144">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Autopilot, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="46ccb-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46ccb-145">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Autopilot πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="46ccb-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="46ccb-146">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="46ccb-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="46ccb-147">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="46ccb-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
