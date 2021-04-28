---
title: Εξαγωγή δεδομένων του Customer Insights στο Snapchat
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760535"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="fcd19-103">Εξαγωγή λιστών τμημάτων στο Snapchat (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="fcd19-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="fcd19-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο Snapchat και χρησιμοποιήστε τα για διαφήμιση.</span><span class="sxs-lookup"><span data-stu-id="fcd19-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="fcd19-105">Προϋποθέσεις για μια σύνδεση</span><span class="sxs-lookup"><span data-stu-id="fcd19-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="fcd19-106">Έχετε έναν [επιχειρηματικό λογαριασμό Snapchat](https://business.snapchat.com/), έναν [διαφημιστικό λογαριασμό Snapchat ](https://ads.snapchat.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="fcd19-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fcd19-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="fcd19-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fcd19-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="fcd19-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fcd19-109">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="fcd19-109">Known limitations</span></span>

- <span data-ttu-id="fcd19-110">Η εξαγωγή στο Snapchat περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="fcd19-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="fcd19-111">Η εξαγωγή έως 1 εκατομμυρίων προφίλ στο Snapchat μπορεί να χρειαστεί έως και 15 λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="fcd19-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="fcd19-112">Ρύθμιση σύνδεσης στο Snapchat</span><span class="sxs-lookup"><span data-stu-id="fcd19-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="fcd19-113">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="fcd19-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fcd19-114">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Snapchat** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="fcd19-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="fcd19-115">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="fcd19-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fcd19-116">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fcd19-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fcd19-117">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="fcd19-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fcd19-118">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fcd19-118">Choose who can use this connection.</span></span> <span data-ttu-id="fcd19-119">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="fcd19-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fcd19-120">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fcd19-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fcd19-121">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="fcd19-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fcd19-122">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Snapchat.</span><span class="sxs-lookup"><span data-stu-id="fcd19-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="fcd19-123">Επιλέξτε **Έλεγχος ταυτότητας με το Snapchat** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Snapchat.</span><span class="sxs-lookup"><span data-stu-id="fcd19-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="fcd19-124">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fcd19-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fcd19-125">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fcd19-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fcd19-126">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="fcd19-126">Configure an export</span></span>

<span data-ttu-id="fcd19-127">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="fcd19-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fcd19-128">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fcd19-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fcd19-129">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="fcd19-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fcd19-130">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="fcd19-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fcd19-131">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Snapchat.</span><span class="sxs-lookup"><span data-stu-id="fcd19-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="fcd19-132">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="fcd19-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fcd19-133">Πληκτρολογήστε το [**αναγνωριστικό κοινού Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="fcd19-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="fcd19-134">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="fcd19-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fcd19-135">Απαιτείται η εξαγωγή τμημάτων στο Snapchat.</span><span class="sxs-lookup"><span data-stu-id="fcd19-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="fcd19-136">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="fcd19-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="fcd19-137">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="fcd19-137">Select **Save**.</span></span>

<span data-ttu-id="fcd19-138">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="fcd19-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fcd19-139">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fcd19-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fcd19-140">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fcd19-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fcd19-141">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="fcd19-141">Data privacy and compliance</span></span>

<span data-ttu-id="fcd19-142">Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο Snapchat, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="fcd19-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fcd19-143">Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το Snapchat θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="fcd19-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fcd19-144">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fcd19-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="fcd19-145">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="fcd19-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
