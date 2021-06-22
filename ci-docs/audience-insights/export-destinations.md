---
title: Εξαγωγή δεδομένων από το Customer Insights
description: 'Διαχειριστείτε εξαγωγές για κοινή χρήση δεδομένων. '
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253040"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="b1137-103">Επισκόπηση εξαγωγών (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="b1137-103">Exports (preview) overview</span></span>

<span data-ttu-id="b1137-104">Η σελίδα **Εξαγωγές** εμφανίζει όλες τις ρυθμισμένες εξαγωγές.</span><span class="sxs-lookup"><span data-stu-id="b1137-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="b1137-105">Οι εξαγωγές μοιράζονται συγκεκριμένα δεδομένα με διάφορες εφαρμογές.</span><span class="sxs-lookup"><span data-stu-id="b1137-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="b1137-106">Μπορούν να περιλαμβάνουν προφίλ πελατών ή οντότητες, σχήματα και λεπτομέρειες αντιστοίχισης.</span><span class="sxs-lookup"><span data-stu-id="b1137-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="b1137-107">Κάθε εξαγωγή απαιτεί μια [σύνδεση, που έχει ρυθμιστεί από έναν διαχειριστή, για τη διαχείριση του ελέγχου ταυτότητας και την πρόσβαση](connections.md).</span><span class="sxs-lookup"><span data-stu-id="b1137-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="b1137-108">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές** για να δείτε τη σελίδα εξαγωγών.</span><span class="sxs-lookup"><span data-stu-id="b1137-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="b1137-109">Όλοι οι ρόλοι χρηστών έχουν πρόσβαση για προβολή ρυθμισμένες εξαγωγές.</span><span class="sxs-lookup"><span data-stu-id="b1137-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="b1137-110">Χρήση του πεδίου αναζήτησης στη γραμμή εντολών για την εύρεση εξαγωγών σύμφωνα με το όνομα, το όνομα σύνδεσης ή τον τύπο σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="b1137-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="b1137-111">Ρύθμιση νέας εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="b1137-111">Set up a new export</span></span>

<span data-ttu-id="b1137-112">Για να ρυθμίσετε ή να επεξεργαστείτε μια εξαγωγή, θα πρέπει να έχετε διαθέσιμες συνδέσεις.</span><span class="sxs-lookup"><span data-stu-id="b1137-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="b1137-113">Οι συνδέσεις εξαρτώνται από τον [ρόλο του χρήστη](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="b1137-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="b1137-114">Οι διαχειριστές έχουν πρόσβαση σε όλες τις συνδέσεις.</span><span class="sxs-lookup"><span data-stu-id="b1137-114">Administrators have access to all connections.</span></span> <span data-ttu-id="b1137-115">Επίσης, μπορούν να δημιουργήσουν νέες συνδέσεις κατά τη ρύθμιση μιας εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="b1137-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="b1137-116">Οι συμβάλλοντες μπορούν να έχουν πρόσβαση σε συγκεκριμένες συνδέσεις.</span><span class="sxs-lookup"><span data-stu-id="b1137-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="b1137-117">Εξαρτώνται από τους διαχειριστές για τη ρύθμιση παραμέτρων και την κοινή χρήση συνδέσεων.</span><span class="sxs-lookup"><span data-stu-id="b1137-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="b1137-118">Η λίστα "εξαγωγές" εμφανίζει στους συμβάλλοντες αν μπορούν να επεξεργαστούν ή να προβάλουν μόνο μια εξαγωγή στη στήλη **Τα δικαιώματά σας**.</span><span class="sxs-lookup"><span data-stu-id="b1137-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="b1137-119">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b1137-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="b1137-120">Οι χρήστες μπορούν μόνο να προβάλλουν τις υπάρχουσες εξαγωγές, αλλά όχι να τις δημιουργήσουν.</span><span class="sxs-lookup"><span data-stu-id="b1137-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="b1137-121">Ορίστε μια νέα εξαγωγή</span><span class="sxs-lookup"><span data-stu-id="b1137-121">Define a new export</span></span>

1. <span data-ttu-id="b1137-122">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1137-123">Επιλέξτε **Προσθήκη εξαγωγής** για να δημιουργήσετε μια νέα εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b1137-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="b1137-124">Στο τμήμα παραθύρου **Ρύθμιση εξαγωγής**, επιλέξτε τη σύνδεση που θα χρησιμοποιήσετε.</span><span class="sxs-lookup"><span data-stu-id="b1137-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="b1137-125">Η διαχείριση των [συνδεων](connections.md) γίνεται από τους διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="b1137-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="b1137-126">Δώστε τις απαιτούμενες λεπτομέρειες και επιλέξτε **Αποθήκευση** για να δημιουργήσετε την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b1137-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="b1137-127">Καθορισμός νέας εξαγωγής με βάση μια υπάρχουσα εξαγωγή</span><span class="sxs-lookup"><span data-stu-id="b1137-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="b1137-128">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1137-129">Στη λίστα εξαγωγών, επιλέξτε την εξαγωγή που θέλετε να αναπαράξετε.</span><span class="sxs-lookup"><span data-stu-id="b1137-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="b1137-130">Επιλέξτε **Δημιουργία διπλότυπου** στη γραμμή εντολών για να ανοίξετε το τμήμα παραθύρου **Ρύθμιση εξαγωγής** με τις λεπτομέρειες της επιλεγμένης εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="b1137-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="b1137-131">Αναθεωρήστε και προσαρμόστε την εξαγωγή και επιλέξτε **Αποθήκευση** για να δημιουργήσετε μια νέα εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b1137-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="b1137-132">Επεξεργασία μιας εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="b1137-132">Edit an export</span></span>

1. <span data-ttu-id="b1137-133">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1137-134">Στη λίστα εξαγωγών, επιλέξτε την εξαγωγή που θέλετε να επεξεργαστείτε.</span><span class="sxs-lookup"><span data-stu-id="b1137-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="b1137-135">Επιλέξτε **Επεξεργασία** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b1137-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="b1137-136">Αλλάξτε τις τιμές που θέλετε να ενημερώσετε κι επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="b1137-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="b1137-137">Προβολή εξαγωγών και λεπτομερειών εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="b1137-137">View exports and export details</span></span>

<span data-ttu-id="b1137-138">Μετά τη δημιουργία προορισμών εξαγωγής, αυτοί εμφανίζονται στην περιοχή **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="b1137-139">Όλοι οι χρήστες μπορούν να δουν ποια δεδομένα κοινοποιούνται και την πιο πρόσφατη κατάστασή τους.</span><span class="sxs-lookup"><span data-stu-id="b1137-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="b1137-140">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1137-141">Οι χρήστες χωρίς δικαιώματα επεξεργασίας επιλέγουν **Προβολή** αντί για **Επεξεργασία**, δείτε τις λεπτομέρειες της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="b1137-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="b1137-142">Το πλαϊνό τμήμα παραθύρου εμφανίζει τη ρύθμιση παραμέτρων μιας εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="b1137-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="b1137-143">Χωρίς δικαιώματα επεξεργασίας, δεν μπορείτε να αλλάξετε τις τιμές.</span><span class="sxs-lookup"><span data-stu-id="b1137-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="b1137-144">Επιλέξτε **Κλείσιμο** για να επιστρέψετε στη σελίδα "Εξαγωγές".</span><span class="sxs-lookup"><span data-stu-id="b1137-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="b1137-145">Προγραμματισμός και εκτέλεση εξαγωγών</span><span class="sxs-lookup"><span data-stu-id="b1137-145">Schedule and run exports</span></span>

<span data-ttu-id="b1137-146">Κάθε εξαγωγή που ρυθμίζετε έχει ένα χρονοδιάγραμμα ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="b1137-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="b1137-147">Κατά τη διάρκεια μιας ανανέωσης, το σύστημα αναζητά νέα ή ενημερωμένα δεδομένα για να τα συμπεριλάβει σε μια εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b1137-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="b1137-148">Ως προεπιλογή, οι εξαγωγές εκτελούνται ως μέρος κάθε [προγραμματισμένης ανανέωσης συστήματος](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1137-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b1137-149">Μπορείτε να προσαρμόσετε το χρονοδιάγραμμα ανανέωσης ή να το απενεργοποιήσετε για μη αυτόματη εκτέλεση των εξαγωγών.</span><span class="sxs-lookup"><span data-stu-id="b1137-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="b1137-150">Τα χρονοδιαγράμματα εξαγωγής εξαρτώνται από την κατάσταση του περιβάλλοντός σας.</span><span class="sxs-lookup"><span data-stu-id="b1137-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="b1137-151">Εάν υπάρχουν ενημερώσεις για τις [εξαρτήσεις](system.md#refresh-policies) που βρίσκονται σε εξέλιξη κατά την έναρξη μιας προγραμματισμένης εξαγωγής, το σύστημα θα ολοκληρώσει πρώτα τις εξαρτήσεις και μετά θα εκτελέσει την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="b1137-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="b1137-152">Μπορείτε να δείτε την τελευταία ανανέωση μιας εξαγωγής στη στήλη **Ανανέωση**.</span><span class="sxs-lookup"><span data-stu-id="b1137-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="b1137-153">Χρονοδιάγραμμα εξαγωγών</span><span class="sxs-lookup"><span data-stu-id="b1137-153">Schedule exports</span></span>

<span data-ttu-id="b1137-154">Μπορείτε να καθορίσετε προσαρμοσμένα χρονοδιαγράμματα ανανέωσης για μεμονωμένες εξαγωγές ή πολλές εξαγωγές ταυτόχρονα.</span><span class="sxs-lookup"><span data-stu-id="b1137-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="b1137-155">Το τρέχον χρονοδιάγραμμα που ορίζεται παρατίθενται στη στήλη **Χρονοδιάγραμμα** της λίστας εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="b1137-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="b1137-156">Το δικαίωμα αλλαγής του χρονοδιαγράμματος είναι ίδιο με το δικαίωμα [επεξεργασίας και ορισμού εξαγωγών](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b1137-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="b1137-157">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1137-158">Επιλέξτε την εξαγωγή που θέλετε να προγραμματίσετε.</span><span class="sxs-lookup"><span data-stu-id="b1137-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="b1137-159">Επιλέξτε **Χρονοδιάγραμμα** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b1137-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="b1137-160">Στο τμήμα παραθύρου **Χρονοδιάγραμμα εξαγωγής** ορίστε την **Εκτέλεση χρονοδιαγράμματος** σε **Ενεργή** για αυτόματη εκτέλεση της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="b1137-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="b1137-161">Ρυθμίστε την επιλογή σε **Ανενεργή** για μη αυτόματη ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="b1137-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="b1137-162">Για εξαγωγές που ανανεώνονται αυτόματα, επιλέξτε μια τιμή **Περιοδικότητας** και καθορίστε τις λεπτομέρειες για αυτήν.</span><span class="sxs-lookup"><span data-stu-id="b1137-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="b1137-163">Ο χρόνος που ορίζεται εφαρμόζεται σε όλες τις παρουσίες περιοδικότητας.</span><span class="sxs-lookup"><span data-stu-id="b1137-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="b1137-164">Είναι η ώρα κατά την οποία μια εξαγωγή θα πρέπει να ξεκινήσει να ανανεώνεται.</span><span class="sxs-lookup"><span data-stu-id="b1137-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="b1137-165">Εφαρμόστε και ενεργοποιήστε τις αλλαγές σας επιλέγοντας **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="b1137-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="b1137-166">Κατά την επεξεργασία του χρονοδιαγράμματος για πολλές εξαγωγές, θα πρέπει να κάνετε μια επιλογή στην περιοχή **Διατήρηση ή παράκαμψη χρονοδιαγράμματων**:</span><span class="sxs-lookup"><span data-stu-id="b1137-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="b1137-167">**Διατήρηση μεμονωμένων χρονοδιαγραμμάτων**: Διατηρήστε το χρονοδιάγραμμα που ορίσατε προηγουμένως για τις επιλεγμένες εξαγωγές και απενεργοποιήστε ή ενεργοποιήστε μόνο.</span><span class="sxs-lookup"><span data-stu-id="b1137-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="b1137-168">**Καθορισμός νέου χρονοδιαγράμματος για όλες τις επιλεγμένες εξαγωγές**: Αντικαταστήστε τα υπάρχοντα χρονοδιαγράμματα των επιλεγμένων εξαγωγών.</span><span class="sxs-lookup"><span data-stu-id="b1137-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="b1137-169">Εκτέλεση εξαγωγών κατ' απαίτηση</span><span class="sxs-lookup"><span data-stu-id="b1137-169">Run exports on demand</span></span>

<span data-ttu-id="b1137-170">Για να εξαγάγετε δεδομένα χωρίς να περιμένετε την προγραμματισμένη ανανέωση, μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="b1137-171">Για να εκτελέσετε όλες τις εξαγωγές, επιλέξτε **Εκτέλεση όλων** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b1137-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="b1137-172">Αυτή η ενέργεια θα εκτελεί μόνο εξαγωγές που έχουν ενεργό χρονοδιάγραμμα.</span><span class="sxs-lookup"><span data-stu-id="b1137-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="b1137-173">Για να εκτελέσετε μία μεμονωμένη εξαγωγή, επιλέξτε την από τη λίστα και επιλέξτε **Εκτέλεση** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b1137-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="b1137-174">Με αυτόν τον τρόπο εκτελείτε εξαγωγές χωρίς ενεργό χρονοδιάγραμμα.</span><span class="sxs-lookup"><span data-stu-id="b1137-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="b1137-175">Κατάργηση εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="b1137-175">Remove an Export</span></span>

1. <span data-ttu-id="b1137-176">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="b1137-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1137-177">Επιλέξτε την εξαγωγή που θέλετε να καταργήσετε.</span><span class="sxs-lookup"><span data-stu-id="b1137-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="b1137-178">Επιλέξτε **Κατάργηση** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b1137-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="b1137-179">Επιβεβαιώστε την κατάργηση επιλέγοντας **Κατάργηση** στην οθόνη επιβεβαίωσης.</span><span class="sxs-lookup"><span data-stu-id="b1137-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
