---
title: Εξαγωγή δεδομένων του Customer Insights στο Omnisend
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124493"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="e3337-103">Εξαγωγή τμημάτων στο Omnisend (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="e3337-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="e3337-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Omnisend και χρησιμοποιήστε τα για δραστηριότητες μάρκετινγκ.</span><span class="sxs-lookup"><span data-stu-id="e3337-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3337-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="e3337-105">Prerequisites</span></span>

-   <span data-ttu-id="e3337-106">Έχετε έναν [λογαριασμό Omnisend](https://www.omnisend.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή εκστρατείας.</span><span class="sxs-lookup"><span data-stu-id="e3337-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e3337-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="e3337-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e3337-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="e3337-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e3337-109">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="e3337-109">Known limitations</span></span>

- <span data-ttu-id="e3337-110">Μπορείτε να εξαγάγετε έως και 1 εκατομμύριο προφίλ ανά εξαγωγή στο Omnisend και μπορεί να χρειαστούν έως και 4 ώρες για να ολοκληρωθεί αυτό.</span><span class="sxs-lookup"><span data-stu-id="e3337-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="e3337-111">Η εξαγωγή στο Omnisend περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="e3337-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="e3337-112">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Omnisend εξαρτάται από τη σύμβασή σας με το Omnisend.</span><span class="sxs-lookup"><span data-stu-id="e3337-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="e3337-113">Ρύθμιση σύνδεσης στο Omnisend</span><span class="sxs-lookup"><span data-stu-id="e3337-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="e3337-114">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="e3337-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e3337-115">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Omnisend** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="e3337-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="e3337-116">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="e3337-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e3337-117">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="e3337-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e3337-118">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="e3337-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e3337-119">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="e3337-119">Choose who can use this connection.</span></span> <span data-ttu-id="e3337-120">Ως προεπιλογή, είναι μόνο διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="e3337-120">By default it's only administrators.</span></span> <span data-ttu-id="e3337-121">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e3337-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e3337-122">Πληκτρολογήστε το [κλειδί API του Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="e3337-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="e3337-123">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="e3337-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e3337-124">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Omnisend.</span><span class="sxs-lookup"><span data-stu-id="e3337-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="e3337-125">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e3337-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e3337-126">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="e3337-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e3337-127">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="e3337-127">Configure an export</span></span>

<span data-ttu-id="e3337-128">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="e3337-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e3337-129">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3337-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3337-130">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="e3337-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e3337-131">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="e3337-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e3337-132">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Omnisend.</span><span class="sxs-lookup"><span data-stu-id="e3337-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="e3337-133">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="e3337-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e3337-134">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="e3337-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e3337-135">Απαιτείται για την εξαγωγή τμημάτων στο Omnisend.</span><span class="sxs-lookup"><span data-stu-id="e3337-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="e3337-136">Προαιρετικά, μπορείτε να εξαγάγετε το Όνομα, το Επώνυμο, τη Διεύθυνση, τη Χώρα/Περιοχή, την Πολιτεία, την Πόλη και τον Ταχυδρομικό Κώδικα για να δημιουργήσετε πιο προσαρμοσμένα μηνύματα ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="e3337-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="e3337-137">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="e3337-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e3337-138">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="e3337-138">Select **Save**.</span></span>

<span data-ttu-id="e3337-139">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="e3337-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e3337-140">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3337-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3337-141">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e3337-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3337-142">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="e3337-142">Data privacy and compliance</span></span>

<span data-ttu-id="e3337-143">Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο Omnisend, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="e3337-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3337-144">Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το Omnisend θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="e3337-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3337-145">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3337-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e3337-146">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="e3337-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
