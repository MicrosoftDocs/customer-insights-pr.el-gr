---
title: Εξαγωγή δεδομένων από το Customer Insights
description: 'Διαχειριστείτε εξαγωγές για κοινή χρήση δεδομένων. '
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016614"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="8b497-103">Επισκόπηση εξαγωγών (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="8b497-103">Exports (preview) overview</span></span>

<span data-ttu-id="8b497-104">Η σελίδα **Εξαγωγές** εμφανίζει όλες τις ρυθμισμένες εξαγωγές.</span><span class="sxs-lookup"><span data-stu-id="8b497-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="8b497-105">Οι εξαγωγές μοιράζονται συγκεκριμένα δεδομένα με διάφορες εφαρμογές.</span><span class="sxs-lookup"><span data-stu-id="8b497-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="8b497-106">Μπορούν να περιλαμβάνουν προφίλ πελατών ή οντότητες, σχήματα και λεπτομέρειες αντιστοίχισης.</span><span class="sxs-lookup"><span data-stu-id="8b497-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="8b497-107">Κάθε εξαγωγή απαιτεί μια [σύνδεση, που έχει ρυθμιστεί από έναν διαχειριστή, για τη διαχείριση του ελέγχου ταυτότητας και την πρόσβαση](connections.md).</span><span class="sxs-lookup"><span data-stu-id="8b497-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="8b497-108">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές** για να δείτε τη σελίδα εξαγωγών.</span><span class="sxs-lookup"><span data-stu-id="8b497-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="8b497-109">Όλοι οι ρόλοι χρηστών έχουν πρόσβαση για προβολή ρυθμισμένες εξαγωγές.</span><span class="sxs-lookup"><span data-stu-id="8b497-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="8b497-110">Χρήση του πεδίου αναζήτησης στη γραμμή εντολών για την εύρεση εξαγωγών σύμφωνα με το όνομα, το όνομα σύνδεσης ή τον τύπο σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="8b497-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="8b497-111">Ρύθμιση νέας εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="8b497-111">Set up a new export</span></span>

<span data-ttu-id="8b497-112">Για να ρυθμίσετε ή να επεξεργαστείτε μια εξαγωγή, θα πρέπει να έχετε διαθέσιμες συνδέσεις.</span><span class="sxs-lookup"><span data-stu-id="8b497-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="8b497-113">Οι συνδέσεις εξαρτώνται από τον [ρόλο του χρήστη](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="8b497-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="8b497-114">Οι διαχειριστές έχουν πρόσβαση σε όλες τις συνδέσεις.</span><span class="sxs-lookup"><span data-stu-id="8b497-114">Administrators have access to all connections.</span></span> <span data-ttu-id="8b497-115">Επίσης, μπορούν να δημιουργήσουν νέες συνδέσεις κατά τη ρύθμιση μιας εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="8b497-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="8b497-116">Οι συμβάλλοντες μπορούν να έχουν πρόσβαση σε συγκεκριμένες συνδέσεις.</span><span class="sxs-lookup"><span data-stu-id="8b497-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="8b497-117">Εξαρτώνται από τους διαχειριστές για τη ρύθμιση παραμέτρων και την κοινή χρήση συνδέσεων.</span><span class="sxs-lookup"><span data-stu-id="8b497-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="8b497-118">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8b497-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="8b497-119">Οι χρήστες μπορούν μόνο να προβάλλουν τις υπάρχουσες εξαγωγές, αλλά όχι να τις δημιουργήσουν.</span><span class="sxs-lookup"><span data-stu-id="8b497-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="8b497-120">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="8b497-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8b497-121">Επιλέξτε **Προσθήκη εξαγωγής** για να δημιουργήσετε έναν νέο προορισμό εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="8b497-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="8b497-122">Στο τμήμα παραθύρου **Ρύθμιση εξαγωγής**, επιλέξτε τη σύνδεση που θα χρησιμοποιήσετε.</span><span class="sxs-lookup"><span data-stu-id="8b497-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="8b497-123">Η διαχείριση των [συνδεων](connections.md) γίνεται από τους διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="8b497-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="8b497-124">Δώστε τις απαιτούμενες λεπτομέρειες και επιλέξτε **Αποθήκευση** για να δημιουργήσετε την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="8b497-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="8b497-125">Επεξεργασία μιας εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="8b497-125">Edit an export</span></span>

1. <span data-ttu-id="8b497-126">Επιλέξτε τα κατακόρυφα αποσιωπητικά για τον προορισμό εξαγωγής που θέλετε να επεξεργαστείτε.</span><span class="sxs-lookup"><span data-stu-id="8b497-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="8b497-127">Επιλέξτε **Επεξεργασία** από το αναπτυσσόμενο μενού.</span><span class="sxs-lookup"><span data-stu-id="8b497-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="8b497-128">Αλλάξτε τις τιμές που θέλετε να ενημερώσετε κι επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="8b497-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="8b497-129">Προβολή εξαγωγών και λεπτομερειών εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="8b497-129">View Exports and export details</span></span>

<span data-ttu-id="8b497-130">Μετά τη δημιουργία προορισμών εξαγωγής, εμφανίζονται στην περιοχή **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="8b497-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="8b497-131">Όλοι οι χρήστες μπορούν να δουν ποια δεδομένα κοινοποιούνται και την πιο πρόσφατη κατάστασή τους.</span><span class="sxs-lookup"><span data-stu-id="8b497-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="8b497-132">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="8b497-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8b497-133">Οι χρήστες χωρίς δικαιώματα επεξεργασίας επιλέγουν **Προβολή** αντί για **Επεξεργασία**, δείτε τις λεπτομέρειες της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="8b497-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="8b497-134">Αυτό το πλαϊνό τμήμα παραθύρου εμφανίζει τη ρύθμιση αυτής της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="8b497-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="8b497-135">Χωρίς δικαιώματα επεξεργασίας, δεν μπορείτε να αλλάξετε τις τιμές.</span><span class="sxs-lookup"><span data-stu-id="8b497-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="8b497-136">Επιλέξτε **Κλείσιμο** για να επιστρέψετε στη σελίδα "Εξαγωγές".</span><span class="sxs-lookup"><span data-stu-id="8b497-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="8b497-137">Εκτέλεση εξαγωγών κατ' απαίτηση</span><span class="sxs-lookup"><span data-stu-id="8b497-137">Run exports on demand</span></span>

<span data-ttu-id="8b497-138">Μετά τη ρύθμιση των παραμέτρων μιας εξαγωγής, θα εκτελείται κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab), εφόσον έχει μια σύνδεση εργασίας.</span><span class="sxs-lookup"><span data-stu-id="8b497-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="8b497-139">Για να εξαγάγετε δεδομένα χωρίς να περιμένετε την προγραμματισμένη ανανέωση, μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="8b497-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="8b497-140">Έχετε δύο επιλογές:</span><span class="sxs-lookup"><span data-stu-id="8b497-140">You have two options:</span></span>

- <span data-ttu-id="8b497-141">Για να εκτελέσετε όλες τις εξαγωγές, επιλέξτε **Εκτέλεση όλων** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="8b497-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="8b497-142">Για να εκτελέσετε μία μεμονωμένη εξαγωγή, επιλέξτε τα αποσιωπητικά (...) σε ένα στοιχείο λίστας και, στη συνέχεια, επιλέξτε **Εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="8b497-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="8b497-143">Κατάργηση εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="8b497-143">Remove an Export</span></span>

1. <span data-ttu-id="8b497-144">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="8b497-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8b497-145">Επιλέξτε τα κατακόρυφη αποσιωπητικά για την εξαγωγή που θέλετε να καταργήσετε.</span><span class="sxs-lookup"><span data-stu-id="8b497-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="8b497-146">Από την αναπτυσσόμενη λίστα , επιλέξτε το στοιχείο **Κατάργηση**.</span><span class="sxs-lookup"><span data-stu-id="8b497-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="8b497-147">Επιβεβαιώστε την κατάργηση επιλέγοντας **Κατάργηση** στην οθόνη επιβεβαίωσης.</span><span class="sxs-lookup"><span data-stu-id="8b497-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
