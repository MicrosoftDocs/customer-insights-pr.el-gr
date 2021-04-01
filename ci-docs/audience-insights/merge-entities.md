---
title: Συγχώνευση οντοτήτων στην ενοποίηση δεδομένων
description: Συγχώνευση οντοτήτων για τη δημιουργία ενοποιημένων προφίλ πελατών.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597833"
---
# <a name="merge-entities"></a><span data-ttu-id="55379-103">Συγχώνευση οντοτήτων</span><span class="sxs-lookup"><span data-stu-id="55379-103">Merge entities</span></span>

<span data-ttu-id="55379-104">Η φάση συγχώνευσης είναι η τελευταία φάση στη διεργασία ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="55379-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="55379-105">Ο σκοπός της είναι ο συμψηφισμός των δεδομένων που βρίσκονται σε διένεξη.</span><span class="sxs-lookup"><span data-stu-id="55379-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="55379-106">Τα παραδείγματα αντιφατικών δεδομένων θα μπορούσαν να περιλαμβάνουν ένα όνομα πελάτη που βρίσκεται σε δύο από τα σύνολα δεδομένων σας, αλλά εμφανίζεται κάπως διαφορετικά σε κάθε ένα από αυτά ("Grant Marshall" ενώ στο άλλο είναι "Grant Marshal") ή έναν αριθμό τηλεφώνου που διαφέρει ως προς τη μορφή (617-803-091X έναντι 617803091X).</span><span class="sxs-lookup"><span data-stu-id="55379-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="55379-107">Η συγχώνευση αυτών των σημείων δεδομένων που βρίσκονται σε διένεξη γίνεται στη βάση επιμέρους χαρακτηριστικών.</span><span class="sxs-lookup"><span data-stu-id="55379-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="55379-108">Μετά την ολοκλήρωση της [φάσης αντιστοιχίας](match-entities.md), μπορείτε να ξεκινήσετε τη φάση συγχώνευσης επιλέγοντας το πλακίδιο **Συγχώνευση** στη σελίδα **Ενοποίηση**.</span><span class="sxs-lookup"><span data-stu-id="55379-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="55379-109">Επισκόπηση προτάσεων συστήματος</span><span class="sxs-lookup"><span data-stu-id="55379-109">Review system recommendations</span></span>

<span data-ttu-id="55379-110">Στη σελίδα **Συγχώνευση**, μπορείτε να επιλέξετε και να εξαιρέσετε τα χαρακτηριστικά που θα συγχωνευτούν εντός της οντότητας του ενοποιημένου προφίλ πελάτη σας (το αποτέλεσμα της διεργασίας της ρύθμισης παραμέτρων).</span><span class="sxs-lookup"><span data-stu-id="55379-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="55379-111">Ορισμένα χαρακτηριστικά συγχωνεύονται αυτόματα από το σύστημα.</span><span class="sxs-lookup"><span data-stu-id="55379-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="55379-112">Προβολή συγχωνευμένων χαρακτηριστικών</span><span class="sxs-lookup"><span data-stu-id="55379-112">View merged attributes</span></span>

<span data-ttu-id="55379-113">Για να προβάλετε τα χαρακτηριστικά που περιλαμβάνονται σε ένα από τα χαρακτηριστικά που συγχωνεύονται αυτόματα, επιλέξτε το συγχωνευμένο χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="55379-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="55379-114">Τα δύο χαρακτηριστικά που συνθέτουν αυτό το συγχωνευμένο χαρακτηριστικό θα εμφανίζονται σε δύο νέες γραμμές κάτω από το συγχωνευμένο χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="55379-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="55379-115">![Επιλέξτε το συγχωνευμένο χαρακτηριστικό](media/configure-data-merge-profile-attributes.png "Επιλέξτε το συγχωνευμένο χαρακτηριστικό")</span><span class="sxs-lookup"><span data-stu-id="55379-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="55379-116">Διαχωρισμός συγχωνευμένων χαρακτηριστικών</span><span class="sxs-lookup"><span data-stu-id="55379-116">Separate merged attributes</span></span>

<span data-ttu-id="55379-117">Για να διαχωρίσετε ή να καταργήσετε τη συγχώνευση σε οποιοδήποτε από τα χαρακτηριστικά που συγχωνεύονται αυτόματα, βρείτε το χαρακτηριστικό στον πίνακα **Χαρακτηριστικά προφίλ**.</span><span class="sxs-lookup"><span data-stu-id="55379-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="55379-118">Επιλέξτε το κουμπί αποσιωπητικών (...).</span><span class="sxs-lookup"><span data-stu-id="55379-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="55379-119">Στην αναπτυσσόμενη λίστα επιλέξτε **Διαχωρισμός πεδίων**.</span><span class="sxs-lookup"><span data-stu-id="55379-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="55379-120">Αφαιρέστε τα συγχωνευμένα χαρακτηριστικά</span><span class="sxs-lookup"><span data-stu-id="55379-120">Remove merged attributes</span></span>

<span data-ttu-id="55379-121">Για να αποκλείσετε ένα χαρακτηριστικό από την οντότητα τελικού προφίλ πελάτη, βρείτε το στον πίνακα **Χαρακτηριστικά προφίλ**.</span><span class="sxs-lookup"><span data-stu-id="55379-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="55379-122">Επιλέξτε το κουμπί αποσιωπητικών (...).</span><span class="sxs-lookup"><span data-stu-id="55379-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="55379-123">Στην αναπτυσσόμενη λίστα επιλέξτε **Να μην γίνει συγχώνευση**.</span><span class="sxs-lookup"><span data-stu-id="55379-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="55379-124">Το χαρακτηριστικό μεταφέρεται στην ενότητα **Αφαιρέθηκε από καρτέλα πελάτη**.</span><span class="sxs-lookup"><span data-stu-id="55379-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="55379-125">Προσθέστε με μη αυτόματο τρόπο συγχωνευμένο χαρακτηριστικό</span><span class="sxs-lookup"><span data-stu-id="55379-125">Manually add a merged attribute</span></span>

<span data-ttu-id="55379-126">Για να προσθέσετε ένα συγχωνευμένο χαρακτηριστικό, μεταβείτε στη σελίδα **Συγχώνευση**.</span><span class="sxs-lookup"><span data-stu-id="55379-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="55379-127">Επιλέξτε **Προσθήκη συγχωνευμένου χαρακτηριστικού**.</span><span class="sxs-lookup"><span data-stu-id="55379-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="55379-128">Δώστε ένα **Όνομα** για να το αναγνωρίσετε αργότερα στη σελίδα **Συγχώνευση** .</span><span class="sxs-lookup"><span data-stu-id="55379-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="55379-129">Προαιρετικά, παρέχετε μια **Εμφανιζόμενο όνομα** που θα εμφανίζεται στην οντότητα Προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="55379-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="55379-130">Ρυθμίστε τις παραμέτρους για το **Επιλέξτε διπλότυπα χαρακτηριστικά** για να επιλέξετε τα χαρακτηριστικά που θέλετε να συγχωνεύσετε από τις αντιστοιχισμένες οντότητες.</span><span class="sxs-lookup"><span data-stu-id="55379-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="55379-131">Επίσης, μπορείτε να αναζητήσετε χαρακτηριστικά.</span><span class="sxs-lookup"><span data-stu-id="55379-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="55379-132">Καθορίστε την **Κατάταξη κατά σπουδαιότητα** για να δώσετε προτεραιότητα σε ένα χαρακτηριστικό σε σχέση με τα υπόλοιπα.</span><span class="sxs-lookup"><span data-stu-id="55379-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="55379-133">Για παράδειγμα, εάν η οντότητα *WebAccountCSV* περιλαμβάνει τα πιο ακριβή δεδομένα σχετικά με το χαρακτηριστικό *Ονοματεπώνυμα*", θα μπορούσατε να δώσετε προτεραιότητα σε αυτήν την οντότητα πάνω από το *ContactCSV* επιλέγοντας *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="55379-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="55379-134">Ως εκ τούτου, το *WebAccountCSV* μετακινείται σε πρώτη προτεραιότητα, ενώ το *ContactCSV* μετακινεί στη δεύτερη προτεραιότητα όταν τραβά τιμές για το χαρακτηριστικό *Ονοματεπώνυμο*.</span><span class="sxs-lookup"><span data-stu-id="55379-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="55379-135">Εκτέλεση της συγχώνευσής σας</span><span class="sxs-lookup"><span data-stu-id="55379-135">Run your merge</span></span>

<span data-ttu-id="55379-136">Είτε κάνετε μη αυτόματη συγχώνευση χαρακτηριστικών είτε αφήνετε το σύστημα να τα συγχωνεύσει, μπορείτε πάντα να εκτελείτε τη συγχώνευση.</span><span class="sxs-lookup"><span data-stu-id="55379-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="55379-137">Επιλέξτε **Εκτέλεση** στη σελίδα **Συγχώνευση** για να ξεκινήσετε τη διεργασία.</span><span class="sxs-lookup"><span data-stu-id="55379-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="55379-138">![Αποθήκευση και εκτέλεση συγχώνευσης δεδομένων](media/configure-data-merge-save-run.png "Αποθήκευση και εκτέλεση συγχώνευσης δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="55379-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="55379-139">Για να κάνετε πρόσθετες αλλαγές και να εκτελέσετε ξανά το βήμα, μπορείτε να ακυρώσετε μια συγχώνευση σε εξέλιξη.</span><span class="sxs-lookup"><span data-stu-id="55379-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="55379-140">Επιλέξτε το κείμενο **Γίνεται ανανέωση ...** και επιλέξτε **Ακύρωση εργασίας** στο πλαϊνό παράθυρο που εμφανίζεται.</span><span class="sxs-lookup"><span data-stu-id="55379-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="55379-141">Αφού το κείμενο **Γίνεται ανανέωση ...** αλλάζει σε **Επιτυχής**, η συγχώνευση έχει ολοκληρωθεί και έχουν επιλυθεί αντιφάσεις στα δεδομένα σας σύμφωνα με τις πολιτικές που έχετε καθορίσει.</span><span class="sxs-lookup"><span data-stu-id="55379-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="55379-142">Τα συγχωνευμένα και τα μη συγχωνευμένα χαρακτηριστικά περιλαμβάνονται στην οντότητα ενοποιημένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="55379-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="55379-143">Τα εξαιρούμενα χαρακτηριστικά δεν περιλαμβάνονται στην οντότητα ενοποιημένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="55379-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="55379-144">Εάν δεν ήταν η πρώτη φορά που εκτελέσατε μια συγχώνευση με επιτυχία, όλες οι κατάντη διεργασίες, συμπεριλαμβανομένου του εμπλουτισμού, της κατάτμησης και των μέτρων θα εκτελούνται αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="55379-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="55379-145">Αφού ολοκληρωθεί η επανάληψη όλων των διεργασιών κατάντη, τα προφίλ πελατών απεικονίζουν τις αλλαγές που έχετε κάνει.</span><span class="sxs-lookup"><span data-stu-id="55379-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="55379-146">Υπάρχουν [έξι τύποι κατάστασης](system.md#status-types) για εργασίες/διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="55379-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="55379-147">Επιπλέον, οι περισσότερες διεργασίες [εξαρτώνται από άλλες διεργασίες κατάντη](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="55379-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="55379-148">Μπορείτε να επιλέξετε την κατάσταση μιας διεργασίας για να δείτε λεπτομέρειες σχετικά με την πρόοδο ολόκληρου του έργου.</span><span class="sxs-lookup"><span data-stu-id="55379-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="55379-149">Αφού επιλέξετε **Προβολή λεπτομερειών** για μία από τις εργασίες του έργου, μπορείτε να βρείτε πρόσθετες πληροφορίες: χρόνος επεξεργασίας, ημερομηνία τελευταίας επεξεργασίας και όλα τα σφάλματα και τις προειδοποιήσεις που σχετίζονται με την εργασία.</span><span class="sxs-lookup"><span data-stu-id="55379-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="55379-150">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="55379-150">Next Step</span></span>

<span data-ttu-id="55379-151">Ρυθμίστε τις παραμέτρους [Δραστηριότητες](activities.md) [Εμπλουτισμός,](enrichment-microsoft-graph.md) ή [Σχέσεις](relationships.md) σε περισσότερες πληροφορίες σχετικά με τους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="55379-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="55379-152">Εάν έχετε ήδη ρυθμίσει τις παραμέτρους των δραστηριοτήτων, του εμπλουτισμού ή των σχέσεων ή εάν έχετε καθορίσει τμήματα αγοράς, θα γίνεται αυτόματα η επεξεργασία τους ώστε να χρησιμοποιούν τα πιο πρόσφατα δεδομένα πελατών.</span><span class="sxs-lookup"><span data-stu-id="55379-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]