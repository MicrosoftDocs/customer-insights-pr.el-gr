---
title: Εξαγωγή δεδομένων του Customer Insights στο ActiveCampaign
description: Μάθετε πώς να ρυθμίζετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314617"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="50d48-103">Εξαγωγή τμημάτων στο ActiveCampaign (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="50d48-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="50d48-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο ActiveCampaign και χρησιμοποιήστε τα για δραστηριότητες μάρκετινγκ.</span><span class="sxs-lookup"><span data-stu-id="50d48-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50d48-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="50d48-105">Prerequisites</span></span>

-   <span data-ttu-id="50d48-106">Έχετε έναν [λογαριασμό ActiveCampaign](https://www.activecampaign.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="50d48-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="50d48-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="50d48-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="50d48-108">Τα ενοποιημένα προφίλ πελατών στα τμήματα αγοράς που έχουν εξαχθεί περιέχουν ένα πεδίο με μια διεύθυνση email.</span><span class="sxs-lookup"><span data-stu-id="50d48-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="50d48-109">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="50d48-109">Known limitations</span></span>

- <span data-ttu-id="50d48-110">Μπορείτε να εξαγάγετε έως και 1 εκατομμύριο προφίλ ανά εξαγωγή στο ActiveCampaign και για να ολοκληρωθεί μπορεί να χρειαστούν έως και 90 λεπτά.</span><span class="sxs-lookup"><span data-stu-id="50d48-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="50d48-111">Η εξαγωγή στο ActiveCampaign περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="50d48-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="50d48-112">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο ActiveCampaign εξαρτάται από τη σύμβαση με το ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="50d48-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="50d48-113">Ρυθμίστε τη σύνδεση στο ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="50d48-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="50d48-114">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="50d48-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="50d48-115">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **ActiveCampaign**, για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="50d48-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="50d48-116">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="50d48-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="50d48-117">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="50d48-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="50d48-118">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="50d48-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="50d48-119">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="50d48-119">Choose who can use this connection.</span></span> <span data-ttu-id="50d48-120">Ως προεπιλογή, είναι μόνο διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="50d48-120">By default, it's only administrators.</span></span> <span data-ttu-id="50d48-121">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="50d48-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="50d48-122">Πληκτρολογήστε το [κλειδί API ActiveCampaign και το όνομα κεντρικού υπολογιστή τελικού σημείου REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="50d48-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="50d48-123">Το όνομα κεντρικού υπολογιστή τελικού σημείου REST είναι μόνο το όνομα κεντρικού υπολογιστή, χωρίς https://.</span><span class="sxs-lookup"><span data-stu-id="50d48-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="50d48-124">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="50d48-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="50d48-125">Επιλέξτε **Σύνδεση** για να επιβεβαιώσετε τη σύνδεση στο ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="50d48-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="50d48-126">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="50d48-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="50d48-127">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="50d48-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="50d48-128">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="50d48-128">Configure an export</span></span>

<span data-ttu-id="50d48-129">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="50d48-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="50d48-130">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="50d48-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="50d48-131">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="50d48-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="50d48-132">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="50d48-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="50d48-133">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="50d48-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="50d48-134">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="50d48-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="50d48-135">Εισαγάγετε το [**αναγνωριστικό λίστας ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="50d48-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="50d48-136">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="50d48-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="50d48-137">Απαιτείται εξαγωγή τμημάτων στο ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="50d48-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="50d48-138">Προαιρετικά, μπορείτε να εξαγάγετε το Όνομα, το Επώνυμο και το Τηλέφωνο, για να δημιουργήσετε πιο εξατομικευμένα μηνύματα ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="50d48-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="50d48-139">Επιλέξτε Προσθήκη χαρακτηριστικού για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="50d48-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="50d48-140">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="50d48-140">Select **Save**.</span></span>

<span data-ttu-id="50d48-141">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="50d48-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="50d48-142">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="50d48-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="50d48-143">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="50d48-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="50d48-144">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="50d48-144">Data privacy and compliance</span></span>

<span data-ttu-id="50d48-145">Όταν ενεργοποιείτε τη δυνατότητα του Dynamics 365 Customer Insights για μεταβίβαση δεδομένων στο ActiveCampaign, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβάνων πιθανώς ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="50d48-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="50d48-146">Η Microsoft θα μεταφέρει τέτοιου είδους δεδομένα κατόπιν οδηγιών σας, αλλά εσείς φέρετε την ευθύνη για τη διασφάλιση ότι το ActiveCampaign ανταποκρίνεται σε οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="50d48-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="50d48-147">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="50d48-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="50d48-148">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="50d48-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
