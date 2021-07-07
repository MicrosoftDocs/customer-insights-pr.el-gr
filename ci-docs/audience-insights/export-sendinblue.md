---
title: Εξαγωγή δεδομένων του Customer Insights στο Sendinblue
description: Μάθετε πώς να ρυθμίζετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314616"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="2c019-103">Εξαγωγή τμημάτων στο Sendinblue (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="2c019-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="2c019-104">Εξαγάγετε τα τμήματα των ενοποιημένων προφίλ πελατών για να δημιουργήσετε εκστρατείες, να παρέχετε μάρκετινγκ μέσω ηλεκτρονικού ταχυδρομείου και να χρησιμοποιήσετε συγκεκριμένες ομάδες πελατών με το Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2c019-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2c019-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="2c019-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="2c019-106">Έχετε έναν [λογαριασμό Sendinblue](https://www.sendinblue.com/) και τα αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="2c019-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2c019-107">Υπάρχουν υπάρχουσες λίστες στο Sendinblue και τα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="2c019-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="2c019-108">Έχετε [ρυθμίσει τμήματα](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2c019-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="2c019-109">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="2c019-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2c019-110">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="2c019-110">Known limitations</span></span>

- <span data-ttu-id="2c019-111">Έως 1 εκατομμύριο προφίλ ανά εξαγωγή στο Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2c019-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="2c019-112">Η εξαγωγή στο Sendinblue περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="2c019-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="2c019-113">Η εξαγωγή τμημάτων με συνολικό αριθμό 1 εκατομμυρίων προφίλ μπορεί να διαρκέσει έως και 90 λεπτά.</span><span class="sxs-lookup"><span data-stu-id="2c019-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="2c019-114">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Sendinblue εξαρτάται και περιορίζεται από τη σύμβαση με το Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2c019-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="2c019-115">Ρύθμιση σύνδεσης με το Sendinblue</span><span class="sxs-lookup"><span data-stu-id="2c019-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="2c019-116">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="2c019-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2c019-117">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Sendinblue**, για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="2c019-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="2c019-118">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="2c019-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2c019-119">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="2c019-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2c019-120">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="2c019-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2c019-121">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="2c019-121">Choose who can use this connection.</span></span> <span data-ttu-id="2c019-122">Ως προεπιλογή, είναι μόνο διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="2c019-122">By default it's only administrators.</span></span> <span data-ttu-id="2c019-123">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2c019-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2c019-124">Πληκτρολογήστε το **[κλειδί API Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="2c019-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="2c019-125">Επιλέξτε **Συμφωνώ με** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση** και επιλέξτε **Σύνδεση**, για να αρχικοποιήσετε τη σύνδεση με το Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2c019-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="2c019-126">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2c019-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2c019-127">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="2c019-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2c019-128">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="2c019-128">Configure an export</span></span>

<span data-ttu-id="2c019-129">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="2c019-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2c019-130">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2c019-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2c019-131">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="2c019-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2c019-132">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="2c019-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2c019-133">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2c019-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="2c019-134">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="2c019-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2c019-135">Εισαγάγετε το **αναγνωριστικό λίστας Sendinblue**.</span><span class="sxs-lookup"><span data-stu-id="2c019-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="2c019-136">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="2c019-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="2c019-137">Προαιρετικά, μπορείτε να εξαγάγετε το **Όνομα**, το **Επώνυμο** και το **Τηλέφωνο**, για να δημιουργήσετε πιο εξατομικευμένα μηνύματα ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="2c019-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="2c019-138">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="2c019-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2c019-139">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="2c019-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="2c019-140">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="2c019-140">Select **Save**.</span></span>

<span data-ttu-id="2c019-141">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="2c019-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2c019-142">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2c019-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2c019-143">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2c019-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2c019-144">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="2c019-144">Data privacy and compliance</span></span>

<span data-ttu-id="2c019-145">Όταν ενεργοποιείτε τη δυνατότητα του Dynamics 365 Customer Insights για μεταβίβαση δεδομένων στο Sendinblue, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβάνων πιθανώς ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="2c019-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2c019-146">Η Microsoft θα μεταφέρει τέτοιου είδους δεδομένα κατόπιν οδηγιών σας, αλλά εσείς φέρετε την ευθύνη για τη διασφάλιση ότι το Sendinblue ανταποκρίνεται σε οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="2c019-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2c019-147">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2c019-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2c019-148">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="2c019-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
