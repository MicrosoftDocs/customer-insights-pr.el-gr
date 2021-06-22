---
title: Εξαγωγή δεδομένων Customer Insights στο DotDigital
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124411"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="17732-103">Εξαγωγή τμημάτων στο DotDigital (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="17732-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="17732-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών σσε βιβλία διευθύνσεων DotDigital και χρησιμοποιήστε τα για εκστρατείες, μάρκετινγκ μέσω ηλεκτρονικού ταχυδρομείου και για να δημιουργήσετε τμήματα πελατών με το DotDigital.</span><span class="sxs-lookup"><span data-stu-id="17732-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="17732-105">Προϋποθέσεις για μια σύνδεση</span><span class="sxs-lookup"><span data-stu-id="17732-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="17732-106">Έχετε έναν [λογαριασμό DotDigital](https://dotdigital.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="17732-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="17732-107">Υπάρχουν υπάρχοντα βιβλία διευθύνσεων στο DotDigital και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="17732-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="17732-108">Μπορείτε να βρείτε το αναγνωριστικό στη διεύθυνση URL, όταν επιλέγετε και ανοίγετε ένα βιβλίο διευθύνσεων.</span><span class="sxs-lookup"><span data-stu-id="17732-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="17732-109">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [βιβλία διευθύνσεων DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="17732-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="17732-110">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="17732-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="17732-111">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="17732-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="17732-112">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="17732-112">Known limitations</span></span>

- <span data-ttu-id="17732-113">Έως 1000000 προφίλ ανά εξαγωγή στο DotDigital.</span><span class="sxs-lookup"><span data-stu-id="17732-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="17732-114">Η εξαγωγή στο DotDigital περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="17732-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="17732-115">Η εξαγωγή τμημάτων με συνολικά 1 εκατομμύριο προφίλ μπορεί να διαρκέσει έως και τρεις ώρες λόγω περιορισμών από την πλευρά του παρόχου.</span><span class="sxs-lookup"><span data-stu-id="17732-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="17732-116">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο DotDigital εξαρτάται και περιορίζεται στη σύμβασή σας με το DotDigital.</span><span class="sxs-lookup"><span data-stu-id="17732-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="17732-117">Ρύθμιση σύνδεση στο DotDigital</span><span class="sxs-lookup"><span data-stu-id="17732-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="17732-118">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="17732-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="17732-119">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **DotDigital** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="17732-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="17732-120">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="17732-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="17732-121">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="17732-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="17732-122">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="17732-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="17732-123">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="17732-123">Choose who can use this connection.</span></span> <span data-ttu-id="17732-124">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="17732-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="17732-125">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="17732-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="17732-126">Πληκτρολογήστε το **όνομα χρήστη και τον κωδικό πρόσβασης DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="17732-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="17732-127">Εισαγάγετε το **[αναγνωριστικό βιβλίου διευθύνσεων του DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="17732-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="17732-128">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="17732-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="17732-129">Επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο DotDigital.</span><span class="sxs-lookup"><span data-stu-id="17732-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="17732-130">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="17732-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="17732-131">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="17732-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="17732-132">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="17732-132">Configure an export</span></span>

<span data-ttu-id="17732-133">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="17732-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="17732-134">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="17732-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="17732-135">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="17732-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17732-136">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="17732-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="17732-137">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα DotDigital.</span><span class="sxs-lookup"><span data-stu-id="17732-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="17732-138">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="17732-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="17732-139">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="17732-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="17732-140">Επαναλάβετε τα ίδια βήματα για άλλα προαιρετικά πεδία, όπως **Όνομα**, **Επώνυμο**, **Ονοματεπώνυμο**, **Φύλο** και **Ταχυδρομικός κώδικας**.</span><span class="sxs-lookup"><span data-stu-id="17732-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="17732-141">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="17732-141">Select the segments you want to export.</span></span> <span data-ttu-id="17732-142">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο DotDigital.</span><span class="sxs-lookup"><span data-stu-id="17732-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="17732-143">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="17732-143">Select **Save**.</span></span>

<span data-ttu-id="17732-144">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="17732-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="17732-145">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17732-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="17732-146">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="17732-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="17732-147">Στο DotDigital, μπορείτε πλέον να βρείτε τα τμήματά σας στα [βιβλία διευθύνσεων του DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="17732-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="17732-148">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="17732-148">Data privacy and compliance</span></span>

<span data-ttu-id="17732-149">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο DotDigital, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="17732-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="17732-150">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το DotDigital πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="17732-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="17732-151">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="17732-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="17732-152">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="17732-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
