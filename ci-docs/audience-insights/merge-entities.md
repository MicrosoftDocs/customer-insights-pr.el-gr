---
title: Συγχώνευση οντοτήτων στην ενοποίηση δεδομένων
description: Συγχώνευση οντοτήτων για τη δημιουργία ενοποιημένων προφίλ πελατών.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085576"
---
# <a name="merge-entities"></a><span data-ttu-id="ae526-103">Συγχώνευση οντοτήτων</span><span class="sxs-lookup"><span data-stu-id="ae526-103">Merge entities</span></span>

<span data-ttu-id="ae526-104">Η φάση συγχώνευσης είναι η τελευταία φάση στη διεργασία ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="ae526-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="ae526-105">Ο σκοπός της είναι ο συμψηφισμός των δεδομένων που βρίσκονται σε διένεξη.</span><span class="sxs-lookup"><span data-stu-id="ae526-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="ae526-106">Τα παραδείγματα αντιφατικών δεδομένων θα μπορούσαν να περιλαμβάνουν ένα όνομα πελάτη που βρίσκεται σε δύο από τα σύνολα δεδομένων σας, αλλά εμφανίζεται κάπως διαφορετικά σε κάθε ένα από αυτά ("Grant Marshall" ενώ στο άλλο είναι "Grant Marshal") ή έναν αριθμό τηλεφώνου που διαφέρει ως προς τη μορφή (617-803-091X έναντι 617803091X).</span><span class="sxs-lookup"><span data-stu-id="ae526-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="ae526-107">Η συγχώνευση αυτών των σημείων δεδομένων που βρίσκονται σε διένεξη γίνεται στη βάση επιμέρους χαρακτηριστικών.</span><span class="sxs-lookup"><span data-stu-id="ae526-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Σελίδα συγχώνευσης στη διεργασία ενοποίησης δεδομένων που δείχνει τον πίνακα με συγχωνευμένα πεδία που καθορίζουν το ενοποιημένο προφίλ πελάτη.":::

<span data-ttu-id="ae526-109">Μετά την ολοκλήρωση της [φάσης αντιστοιχίας](match-entities.md), μπορείτε να ξεκινήσετε τη φάση συγχώνευσης επιλέγοντας το πλακίδιο **Συγχώνευση** στη σελίδα **Ενοποίηση**.</span><span class="sxs-lookup"><span data-stu-id="ae526-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="ae526-110">Επισκόπηση προτάσεων συστήματος</span><span class="sxs-lookup"><span data-stu-id="ae526-110">Review system recommendations</span></span>

<span data-ttu-id="ae526-111">Στα **Δεδομένα** > **Ενοποίηση** > **Συγχώνευση**, επιλέγετε και εξαιρείτε χαρακτηριστικά για συγχώνευση εντός της ενοποιημένης οντότητας προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="ae526-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="ae526-112">Το ενοποιημένο προφίλ πελάτη είναι το αποτέλεσμα της διεργασίας ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="ae526-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="ae526-113">Ορισμένα χαρακτηριστικά συγχωνεύονται αυτόματα από το σύστημα.</span><span class="sxs-lookup"><span data-stu-id="ae526-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="ae526-114">Για να προβάλετε τα χαρακτηριστικά που περιλαμβάνονται σε ένα από τα αυτόματα συγχωνευμένα χαρακτηριστικά σας, επιλέξτε αυτό το συγχωνευμένο χαρακτηριστικό στην καρτέλα **Πεδία πελάτη** του πίνακα.</span><span class="sxs-lookup"><span data-stu-id="ae526-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="ae526-115">Τα χαρακτηριστικά που συνθέτουν αυτό το συγχωνευμένο χαρακτηριστικό εμφανίζονται σε δύο νέες γραμμές κάτω από το συγχωνευμένο χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="ae526-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="ae526-116">Διαχωρισμός, μετονομασία, εξαίρεση και επεξεργασία συγχωνευμένων πεδίων</span><span class="sxs-lookup"><span data-stu-id="ae526-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="ae526-117">Μπορείτε να αλλάξετε τον τρόπο με τον οποίο το σύστημα επεξεργάζεται τα συγχωνευμένα χαρακτηριστικά, ώστε να δημιουργήσει το ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="ae526-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="ae526-118">Επιλέξτε **Εμφάνιση περισσότερων** και επιλέξτε τι θέλετε να αλλάξετε.</span><span class="sxs-lookup"><span data-stu-id="ae526-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Επιλογές στο αναπτυσσόμενο μενού Εμφάνιση περισσότερων για διαχείριση των συγχωνευμένων χαρακτηριστικών.":::

<span data-ttu-id="ae526-120">Για περισσότερες πληροφορίες, ανατρέξτε στις ακόλουθες ενότητες.</span><span class="sxs-lookup"><span data-stu-id="ae526-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="ae526-121">Διαχωρισμός συγχωνευμένων πεδίων</span><span class="sxs-lookup"><span data-stu-id="ae526-121">Separate merged fields</span></span>

<span data-ttu-id="ae526-122">Για να διαχωρίσετε συγχωνευμένα πεδία, βρείτε το χαρακτηριστικό στον πίνακα.</span><span class="sxs-lookup"><span data-stu-id="ae526-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="ae526-123">Τα διαχωρισμένα πεδία εμφανίζονται ως μεμονωμένα σημεία δεδομένων στο ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="ae526-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="ae526-124">Επιλέξτε το συγχωνευμένο πεδίο.</span><span class="sxs-lookup"><span data-stu-id="ae526-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="ae526-125">Επιλέξτε **Εμφάνιση περισσότερων** και επιλέξτε **Ξεχωριστά πεδία**.</span><span class="sxs-lookup"><span data-stu-id="ae526-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="ae526-126">Επιβεβαιώστε τον διαχωρισμό.</span><span class="sxs-lookup"><span data-stu-id="ae526-126">Confirm the separation.</span></span>

1. <span data-ttu-id="ae526-127">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να επεξεργαστείτε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="ae526-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="ae526-128">Μετονομασία συγχωνευμένων πεδίων</span><span class="sxs-lookup"><span data-stu-id="ae526-128">Rename merged fields</span></span>

<span data-ttu-id="ae526-129">Αλλαγή του εμφανιζόμενου ονόματος των συγχωνευμένων χαρακτηριστικών.</span><span class="sxs-lookup"><span data-stu-id="ae526-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="ae526-130">Δεν μπορείτε να αλλάξετε το όνομα της οντότητας εξόδου.</span><span class="sxs-lookup"><span data-stu-id="ae526-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="ae526-131">Επιλέξτε το συγχωνευμένο πεδίο.</span><span class="sxs-lookup"><span data-stu-id="ae526-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="ae526-132">Επιλέξτε **Εμφάνιση περισσότερων** και επιλέξτε **Μετονομασία**.</span><span class="sxs-lookup"><span data-stu-id="ae526-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="ae526-133">Επιβεβαιώστε την αλλαγή του εμφανιζόμενου ονόματος.</span><span class="sxs-lookup"><span data-stu-id="ae526-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="ae526-134">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να επεξεργαστείτε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="ae526-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="ae526-135">Εξαιρέστε τα συγχωνευμένα πεδία</span><span class="sxs-lookup"><span data-stu-id="ae526-135">Exclude merged fields</span></span>

<span data-ttu-id="ae526-136">Αποκλεισμός ενός χαρακτηριστικού από το ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="ae526-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="ae526-137">Εάν το πεδίο χρησιμοποιείται σε άλλες διεργασίες, για παράδειγμα σε ένα τμήμα, καταργήστε το από αυτές τις διεργασίες πριν το αποκλείσετε από το προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="ae526-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="ae526-138">Επιλέξτε το συγχωνευμένο πεδίο.</span><span class="sxs-lookup"><span data-stu-id="ae526-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="ae526-139">Επιλέξτε **Εμφάνιση περισσότερων** και επιλέξτε **Αποκλεισμός**.</span><span class="sxs-lookup"><span data-stu-id="ae526-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="ae526-140">Επιβεβαιώστε την εξαίρεση.</span><span class="sxs-lookup"><span data-stu-id="ae526-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="ae526-141">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να επεξεργαστείτε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="ae526-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="ae526-142">Στη σελίδα **Συγχώνευση**, επιλέξτε **Εξαιρούμενα πεδία** για να δείτε τη λίστα όλων των πεδίων που εξαιρούνται.</span><span class="sxs-lookup"><span data-stu-id="ae526-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="ae526-143">Αυτό το παράθυρο σάς επιτρέπει να προσθέσετε ξανά τα πεδία που έχουν αποκλειστεί.</span><span class="sxs-lookup"><span data-stu-id="ae526-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="ae526-144">Μη αυτόματος συνδυασμός πεδίων</span><span class="sxs-lookup"><span data-stu-id="ae526-144">Manually combine fields</span></span>

<span data-ttu-id="ae526-145">Καθορίστε ένα συγχωνευμένο χαρακτηριστικό μη αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="ae526-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="ae526-146">Στη σελίδα **Συγχώνευση**, επιλέξτε **Συνδυασμός πεδίων**.</span><span class="sxs-lookup"><span data-stu-id="ae526-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="ae526-147">Δώστε ένα **Όνομα** και ένα **Όνομα πεδίου εξόδου**.</span><span class="sxs-lookup"><span data-stu-id="ae526-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="ae526-148">Επιλέξτε ένα πεδίο για προσθήκη.</span><span class="sxs-lookup"><span data-stu-id="ae526-148">Choose a field to add.</span></span> <span data-ttu-id="ae526-149">Επιλέξτε **Προσθήκη πεδίων** για συνδυασμό περισσότερων πεδίων.</span><span class="sxs-lookup"><span data-stu-id="ae526-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="ae526-150">Επιβεβαιώστε την εξαίρεση.</span><span class="sxs-lookup"><span data-stu-id="ae526-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="ae526-151">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να επεξεργαστείτε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="ae526-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="ae526-152">Αλλαγή της σειράς των πεδίων</span><span class="sxs-lookup"><span data-stu-id="ae526-152">Change the order of fields</span></span>

<span data-ttu-id="ae526-153">Ορισμένες οντότητες περιέχουν περισσότερες λεπτομέρειες από άλλες.</span><span class="sxs-lookup"><span data-stu-id="ae526-153">Some entities contain more details than others.</span></span> <span data-ttu-id="ae526-154">Εάν μια οντότητα περιλαμβάνει τα πιο πρόσφατα δεδομένα σχετικά με ένα πεδίο, μπορείτε να τη χρησιμοποιήσετε κατά προτεραιότητα σε σχέση με άλλες οντότητες κατά τη συγχώνευση τιμών.</span><span class="sxs-lookup"><span data-stu-id="ae526-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="ae526-155">Επιλέξτε το συγχωνευμένο πεδίο.</span><span class="sxs-lookup"><span data-stu-id="ae526-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="ae526-156">Επιλέξτε **Εμφάνιση περισσότερων** και επιλέξτε **Επεξεργασία**.</span><span class="sxs-lookup"><span data-stu-id="ae526-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="ae526-157">Στο παράθυρο **Συνδυασμός πεδίων**, επιλέξτε **Μετακίνηση επάνω/κάτω** για να ορίσετε τη σειρά ή σύρετε και αποθέστε τα στη θέση που θέλετε.</span><span class="sxs-lookup"><span data-stu-id="ae526-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="ae526-158">Επιβεβαιώστε την αλλαγή.</span><span class="sxs-lookup"><span data-stu-id="ae526-158">Confirm the change.</span></span>

1. <span data-ttu-id="ae526-159">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να επεξεργαστείτε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="ae526-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="ae526-160">Εκτέλεση της συγχώνευσής σας</span><span class="sxs-lookup"><span data-stu-id="ae526-160">Run your merge</span></span>

<span data-ttu-id="ae526-161">Είτε κάνετε μη αυτόματη συγχώνευση χαρακτηριστικών είτε αφήνετε το σύστημα να τα συγχωνεύσει, μπορείτε πάντα να εκτελείτε τη συγχώνευση.</span><span class="sxs-lookup"><span data-stu-id="ae526-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="ae526-162">Επιλέξτε **Εκτέλεση** στη σελίδα **Συγχώνευση** για να ξεκινήσετε τη διεργασία.</span><span class="sxs-lookup"><span data-stu-id="ae526-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ae526-163">![Αποθήκευση και εκτέλεση συγχώνευσης δεδομένων](media/configure-data-merge-save-run.png "Αποθήκευση και εκτέλεση συγχώνευσης δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="ae526-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="ae526-164">Επιλέξτε **Εκτέλεση μόνο συγχώνευσης**, εάν θέλετε να εμφανίζεται μόνο το αποτέλεσμα στην ενοποιημένη οντότητα πελάτη.</span><span class="sxs-lookup"><span data-stu-id="ae526-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="ae526-165">Οι κατάντη διεργασίες θα ανανεώνονται όπως [ορίζεται στο χρονοδιάγραμμα ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae526-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="ae526-166">Επιλέξτε **Εκτέλεση συγχώνευσης και κατάντη διεργασιών** για να ανανεώσετε το σύστημα με τις αλλαγές σας.</span><span class="sxs-lookup"><span data-stu-id="ae526-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="ae526-167">Όλες οι διεργασίες, συμπεριλαμβανομένου του εμπλουτισμού, των τμημάτων και των ενεργειών θα εκτελούνται ξανά αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="ae526-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="ae526-168">Αφού ολοκληρωθούν όλες οι κατάντη διεργασίες, τα προφίλ πελατών θα αντικατοπτρίζουν τις αλλαγές που έχετε κάνει.</span><span class="sxs-lookup"><span data-stu-id="ae526-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="ae526-169">Για να κάνετε περισσότερες αλλαγές και να εκτελέσετε ξανά το βήμα, μπορείτε να ακυρώσετε μια συγχώνευση σε εξέλιξη.</span><span class="sxs-lookup"><span data-stu-id="ae526-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="ae526-170">Επιλέξτε το κείμενο **Γίνεται ανανέωση ...** και επιλέξτε **Ακύρωση εργασίας** στο πλαϊνό παράθυρο που εμφανίζεται.</span><span class="sxs-lookup"><span data-stu-id="ae526-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="ae526-171">Υπάρχουν [έξι τύποι κατάστασης](system.md#status-types) για εργασίες/διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="ae526-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ae526-172">Επιπλέον, οι περισσότερες διεργασίες [εξαρτώνται από άλλες διεργασίες κατάντη](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ae526-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ae526-173">Μπορείτε να επιλέξετε την κατάσταση μιας διεργασίας για να δείτε λεπτομέρειες σχετικά με την πρόοδο ολόκληρου του έργου.</span><span class="sxs-lookup"><span data-stu-id="ae526-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ae526-174">Αφού επιλέξετε **Προβολή λεπτομερειών** για μία από τις εργασίες του έργου, μπορείτε να βρείτε πρόσθετες πληροφορίες: χρόνος επεξεργασίας, ημερομηνία τελευταίας επεξεργασίας και όλα τα σφάλματα και τις προειδοποιήσεις που σχετίζονται με την εργασία.</span><span class="sxs-lookup"><span data-stu-id="ae526-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae526-175">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="ae526-175">Next Step</span></span>

<span data-ttu-id="ae526-176">Ρυθμίστε τις παραμέτρους [Δραστηριότητες](activities.md) [Εμπλουτισμός,](enrichment-hub.md) ή [Σχέσεις](relationships.md) σε περισσότερες πληροφορίες σχετικά με τους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="ae526-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="ae526-177">Εάν έχετε ήδη ρυθμίσει τις παραμέτρους των δραστηριοτήτων, του εμπλουτισμού ή των τμημάτων, θα γίνει αυτόματα επεξεργασία τους ώστε να χρησιμοποιήσετε τα πιο πρόσφατα δεδομένα πελατών.</span><span class="sxs-lookup"><span data-stu-id="ae526-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
