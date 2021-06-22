---
title: Εξαγωγή δεδομένων Customer Insights στο Microsoft Advertising
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124492"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="b2075-103">Εξαγωγή τμημάτων στο Microsoft Advertising (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="b2075-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="b2075-104">Εξαγάγετε τμήματα του Customer Insights στο Microsoft Advertising για να δημιουργήσετε κοινά Customer Match.</span><span class="sxs-lookup"><span data-stu-id="b2075-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="b2075-105">Χρησιμοποιήστε αυτά τα κοινά για τις διαφημιστικές εκστρατείες σας.</span><span class="sxs-lookup"><span data-stu-id="b2075-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2075-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="b2075-106">Prerequisites</span></span>

-   <span data-ttu-id="b2075-107">Ένας [λογαριασμός Microsoft Advertising](https://ads.microsoft.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="b2075-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b2075-108">Να έχετε αποδεχτεί τους όρους χρήσης του Customer Match.</span><span class="sxs-lookup"><span data-stu-id="b2075-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="b2075-109">[Διαμορφωμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="b2075-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b2075-110">Τα ενοποιημένα προφίλ πελατών στα τμήματα αγοράς που έχουν εξαχθεί περιέχουν ένα πεδίο με μια διεύθυνση email.</span><span class="sxs-lookup"><span data-stu-id="b2075-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b2075-111">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="b2075-111">Known limitations</span></span>

- <span data-ttu-id="b2075-112">Μπορείτε να εξαγάγετε έως και 500 χιλιάδες προφίλ ανά εξαγωγή στο Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b2075-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="b2075-113">Η εξαγωγή στο Microsoft Advertising περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="b2075-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="b2075-114">Η εξαγωγή έως 500 χιλιάδων προφίλ στο Microsoft Advertising μπορεί να χρειαστεί έως και 10 λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="b2075-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="b2075-115">Ρυθμίστε τη σύνδεση στο Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="b2075-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="b2075-116">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="b2075-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b2075-117">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Microsoft Advertising** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="b2075-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="b2075-118">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="b2075-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b2075-119">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="b2075-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b2075-120">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="b2075-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b2075-121">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="b2075-121">Choose who can use this connection.</span></span> <span data-ttu-id="b2075-122">Η προεπιλογή είναι "διαχειριστές".</span><span class="sxs-lookup"><span data-stu-id="b2075-122">The default is administrators.</span></span> <span data-ttu-id="b2075-123">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b2075-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b2075-124">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="b2075-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b2075-125">Επιλέξτε **Σύνδεση** για προετοιμασία της σύνδεσης στο Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b2075-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="b2075-126">Επιλέξτε **Έλεγχος ταυτότητας με το Microsoft Advertising** και δώστε τα διαπιστευτήρια διαχειριστή σας για το Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b2075-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="b2075-127">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b2075-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b2075-128">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="b2075-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b2075-129">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="b2075-129">Configure an export</span></span>

<span data-ttu-id="b2075-130">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="b2075-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b2075-131">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b2075-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b2075-132">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b2075-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b2075-133">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="b2075-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b2075-134">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b2075-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="b2075-135">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="b2075-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b2075-136">Επιλέξτε τα τμήματα για εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b2075-136">Select the segments to export.</span></span> <span data-ttu-id="b2075-137">Τα κοινά Customer Match στο Microsoft Advertising δημιουργούνται αυτόματα με το όνομα των τμημάτων που έχουν επιλεγεί για εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b2075-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="b2075-138">Κάθε τμήμα θα έχει ως αποτέλεσμα ένα ξεχωριστό κοινό Customer Match.</span><span class="sxs-lookup"><span data-stu-id="b2075-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="b2075-139">Πληκτρολογήστε το **Αναγνωριστικό πελάτη Microsoft Αdvertising και το αναγνωριστικό λογαριασμού**.</span><span class="sxs-lookup"><span data-stu-id="b2075-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="b2075-140">Μπορείτε να βρείτε το αναγνωριστικό πελάτη (`cid`) και το αναγνωριστικό λογαριασμού (`aid`) στις παραμέτρους της διεύθυνσης URL όταν είστε συνδεδεμένοι στο Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b2075-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="b2075-141">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Email**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη με τη διεύθυνση email ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="b2075-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="b2075-142">Απαιτείται η εξαγωγή τμημάτων στο Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="b2075-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="b2075-143">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="b2075-143">Select **Save**.</span></span>

<span data-ttu-id="b2075-144">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b2075-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b2075-145">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b2075-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b2075-146">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b2075-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b2075-147">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="b2075-147">Data privacy and compliance</span></span>

<span data-ttu-id="b2075-148">Όταν δίνετε τη δυνατότητα στο Dynamics 365 Customer Insights να μεταβιβάζει δεδομένα στο Microsoft Advertising, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων ενδεχομένως ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="b2075-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b2075-149">Η Microsoft θα μεταφέρει αυτά τα δεδομένα σύμφωνα με τις οδηγίες σας, αλλά είστε υπεύθυνοι για τη διασφάλιση ότι το Microsoft Advertising θα καλύπτει οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="b2075-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b2075-150">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b2075-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b2075-151">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψει τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="b2075-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
