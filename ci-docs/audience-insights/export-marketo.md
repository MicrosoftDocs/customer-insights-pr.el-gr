---
title: Εξαγωγή δεδομένων Customer Insights στο Marketo
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059316"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="2a555-103">Εξαγωγή τμημάτων στο Marketo (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="2a555-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="2a555-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών για τη δημιουργία εκστρατειών, την παροχή μάρκετινγκ μέσω ηλεκτρονικού ταχυδρομείου και τη χρήση συγκεκριμένων ομάδων πελατών με το Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a555-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2a555-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="2a555-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="2a555-106">Έχετε έναν [λογαριασμό Marketo](https://login.marketo.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="2a555-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2a555-107">Υπάρχουν υπάρχουσες λίστες στο Marketo και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="2a555-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="2a555-108">Για περισσότερες πληροφορίες, ανατρέξτε στις [λίστες Marketplace](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="2a555-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="2a555-109">Έχετε [ρυθμίσει τμήματα](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2a555-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="2a555-110">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="2a555-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2a555-111">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="2a555-111">Known limitations</span></span>

- <span data-ttu-id="2a555-112">Έως 1000000 προφίλ ανά εξαγωγή σε Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a555-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="2a555-113">Η εξαγωγή στο Marketo περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="2a555-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="2a555-114">Η εξαγωγή τμημάτων με σύνολο 1000000 προφίλ μπορεί να διαρκέσει έως και 3 ώρες.</span><span class="sxs-lookup"><span data-stu-id="2a555-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="2a555-115">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Marketo εξαρτάται και περιορίζεται στη σύμβασή σας με το Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a555-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="2a555-116">Ρύθμιση σύνδεσης στο Marketo</span><span class="sxs-lookup"><span data-stu-id="2a555-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="2a555-117">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="2a555-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2a555-118">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Marketo** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="2a555-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="2a555-119">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="2a555-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2a555-120">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="2a555-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2a555-121">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="2a555-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2a555-122">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="2a555-122">Choose who can use this connection.</span></span> <span data-ttu-id="2a555-123">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="2a555-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2a555-124">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2a555-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2a555-125">Εισαγάγετε το **[αναγνωριστικό πελάτη Marketo, τον μυστικό κωδικό πελάτη και το όνομα κεντρικού υπολογιστή τελικού σημείου REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="2a555-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="2a555-126">Το όνομα κεντρικού υπολογιστή τελικού σημείου REST είναι μόνο το όνομα κεντρικού υπολογιστή, χωρίς `https://`.</span><span class="sxs-lookup"><span data-stu-id="2a555-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="2a555-127">Παράδειγμα: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="2a555-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="2a555-128">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε την **Προστασία προσωπικών δεδομένων και τη συμμόρφωση** και επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a555-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="2a555-129">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2a555-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2a555-130">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="2a555-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2a555-131">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="2a555-131">Configure an export</span></span>

<span data-ttu-id="2a555-132">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="2a555-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2a555-133">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2a555-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2a555-134">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="2a555-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2a555-135">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="2a555-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2a555-136">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a555-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="2a555-137">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="2a555-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2a555-138">Εισαγάγετε το **[αναγνωριστικό λίστας Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="2a555-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="2a555-139">Το αναγνωριστικό λίστας είναι μια αμιγώς αριθμητική τιμή.</span><span class="sxs-lookup"><span data-stu-id="2a555-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="2a555-140">Για παράδειγμα, εάν το αναγνωριστικό λίστας Marketo είναι ST12345A7, καταργήστε το χαρακτήρα πριν και μετά τα αριθμητικά και πληκτρολογήστε `12345`.</span><span class="sxs-lookup"><span data-stu-id="2a555-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="2a555-141">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="2a555-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="2a555-142">Προαιρετικά, μπορείτε να εξαγάγετε μηνύματα **Όνομα**, **Επώνυμο**, **Πόλη**, **Νομός** και **Χώρα/Περιοχή** για να δημιουργήσετε πιο προσαρμοσμένα μηνύματα ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="2a555-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="2a555-143">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="2a555-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2a555-144">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="2a555-144">Select the segments you want to export.</span></span> <span data-ttu-id="2a555-145">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a555-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="2a555-146">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="2a555-146">Select **Save**.</span></span>

<span data-ttu-id="2a555-147">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="2a555-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2a555-148">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2a555-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2a555-149">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2a555-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="2a555-150">Στο Marketo, μπορείτε πλέον να βρείτε τα τμήματά σας στις [λίστες Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="2a555-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2a555-151">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="2a555-151">Data privacy and compliance</span></span>

<span data-ttu-id="2a555-152">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδώσετε δεδομένα στο Marketo, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="2a555-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2a555-153">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Marketo πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="2a555-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2a555-154">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2a555-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2a555-155">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="2a555-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
