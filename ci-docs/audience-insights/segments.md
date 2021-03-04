---
title: Δημιουργία και διαχείριση τμημάτων
description: Δημιουργήστε τμήματα πελατών για να τα ομαδοποιήσετε βάσει διαφόρων χαρακτηριστικών.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270356"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="befdb-103">Δημιουργία και διαχείριση τμημάτων</span><span class="sxs-lookup"><span data-stu-id="befdb-103">Create and manage segments</span></span>

<span data-ttu-id="befdb-104">Τα τμήματα σάς επιτρέπουν να ομαδοποιήσετε τους πελάτες σας με βάση τα δημογραφικά, συναλλακτικά ή συμπεριφορικά χαρακτηριστικά.</span><span class="sxs-lookup"><span data-stu-id="befdb-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="befdb-105">Μπορείτε να χρησιμοποιήσετε τμήματα αγοράς για να στοχεύσετε σε εκστρατείες προώθησης, δραστηριότητες πωλήσεων και ενέργειες υποστήριξης πελατών για να επιτύχετε τους επιχειρηματικούς σας στόχους.</span><span class="sxs-lookup"><span data-stu-id="befdb-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="befdb-106">Μπορείτε να ορίσετε σύνθετα φίλτρα γύρω από την οντότητα Προφίλ πελάτη και τις σχετικές με αυτήν οντότητες.</span><span class="sxs-lookup"><span data-stu-id="befdb-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="befdb-107">Κάθε τμήμα, μετά την επεξεργασία, δημιουργεί ένα σύνολο καρτελών πελατών, το οποίο μπορείτε να εξαγάγετε και αναφορικά με το οποίο να αναλάβετε δράση.</span><span class="sxs-lookup"><span data-stu-id="befdb-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="befdb-108">Ισχύουν ορισμένα [όρια εξυπηρέτησης](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="befdb-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="befdb-109">Εκτός εάν δηλώνεται διαφορετικά, όλα τα τμήματα είναι **δυναμικά τμήματα**, τα οποία ανανεώνονται σε ένα επαναλαμβανόμενο χρονοδιάγραμμα.</span><span class="sxs-lookup"><span data-stu-id="befdb-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="befdb-110">Το παρακάτω παράδειγμα παρουσιάζει τη δυνατότητα κατακερματισμού.</span><span class="sxs-lookup"><span data-stu-id="befdb-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="befdb-111">Έχουμε καθορίσει ένα τμήμα αγοράς για πελάτες που έχουν παραγγείλει προΪόντα αξίας τουλάχιστον $500 τις τελευταίες 90 ημέρες *και* οι οποίοι συμμετείχαν σε μια κλήση εξυπηρέτησης πελατών που κλιμακώθηκε.</span><span class="sxs-lookup"><span data-stu-id="befdb-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="befdb-112">![Πολλές ομάδες](media/segmentation-group1-2.png "Πολλές ομάδες")</span><span class="sxs-lookup"><span data-stu-id="befdb-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="befdb-113">Δημιουργία νέου τμήματος</span><span class="sxs-lookup"><span data-stu-id="befdb-113">Create a new segment</span></span>

<span data-ttu-id="befdb-114">Τα τμήματα διαχειριζόμαστε στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="befdb-115">Στις πληροφορίες κοινού, μεταβείτε στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="befdb-116">Επιλέξτε **Νέο** > **Κενό τμήμα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="befdb-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="befdb-117">Στο τμήμα παραθύρου **Νέο τμήμα** επιλέξτε έναν τύπο τμήματος αγοράς δώστε ένα **Όνομα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="befdb-118">Προαιρετικά, δώστε ένα εμφανιζόμενο όνομα και μια περιγραφή που θα σας βοηθήσει να προσδιορίσετε το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="befdb-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="befdb-119">Επιλέξτε **Επόμενο** για να μεταβείτε στη σελίδα **Δόμηση τμήματος** όπου καθορίζετε μια ομάδα.</span><span class="sxs-lookup"><span data-stu-id="befdb-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="befdb-120">Μια ομάδα είναι ένα σύνολο πελατών.</span><span class="sxs-lookup"><span data-stu-id="befdb-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="befdb-121">Επιλέξτε την οντότητα που περιλαμβάνει το χαρακτηριστικό με βάση το οποίο θέλετε να κάνετε κατάτμηση.</span><span class="sxs-lookup"><span data-stu-id="befdb-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="befdb-122">Επιλέξτε το χαρακτηριστικό με βάση το οποίο θα δημιουργηθεί το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="befdb-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="befdb-123">Αυτό το χαρακτηριστικό μπορεί να έχει έναν από τους τέσσερις τύπους τιμών: αριθμητική, συμβολοσειρά, ημερομηνία ή δυαδική τιμή.</span><span class="sxs-lookup"><span data-stu-id="befdb-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="befdb-124">Επιλέξτε έναν τελεστή και μια τιμή για το επιλεγμένο χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="befdb-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="befdb-125">![Φίλτρο προσαρμοσμένης ομάδας](media/customer-group-numbers.png "Φίλτρο ομάδας πελατών")</span><span class="sxs-lookup"><span data-stu-id="befdb-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="befdb-126">Αριθμός</span><span class="sxs-lookup"><span data-stu-id="befdb-126">Number</span></span> |<span data-ttu-id="befdb-127">Ορισμός</span><span class="sxs-lookup"><span data-stu-id="befdb-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="befdb-128">1</span><span class="sxs-lookup"><span data-stu-id="befdb-128">1</span></span>     |<span data-ttu-id="befdb-129">Entity</span><span class="sxs-lookup"><span data-stu-id="befdb-129">Entity</span></span>          |
   |<span data-ttu-id="befdb-130">2</span><span class="sxs-lookup"><span data-stu-id="befdb-130">2</span></span>     |<span data-ttu-id="befdb-131">Χαρακτηριστικό</span><span class="sxs-lookup"><span data-stu-id="befdb-131">Attribute</span></span>          |
   |<span data-ttu-id="befdb-132">3</span><span class="sxs-lookup"><span data-stu-id="befdb-132">3</span></span>    |<span data-ttu-id="befdb-133">Τελεστής</span><span class="sxs-lookup"><span data-stu-id="befdb-133">Operator</span></span>         |
   |<span data-ttu-id="befdb-134">4</span><span class="sxs-lookup"><span data-stu-id="befdb-134">4</span></span>    |<span data-ttu-id="befdb-135">Τιμή</span><span class="sxs-lookup"><span data-stu-id="befdb-135">Value</span></span>         |

8. <span data-ttu-id="befdb-136">Εάν η οντότητα είναι συνδεδεμένη με την οντότητα του ενοποιημένου πελάτη μέσω των [σχέσεων](relationships.md), θα πρέπει να καθορίσετε τη διαδρομή σχέσης για να δημιουργήσετε ένα έγκυρο τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="befdb-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="befdb-137">Προσθέστε τις οντότητες από τη διαδρομή σχέσης, μέχρι να επιλέξετε την οντότητα **Πελάτης: CustomerInsights** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="befdb-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="befdb-138">Στη συνέχεια, επιλέξτε **Όλες οι καρτέλες** για κάθε συνθήκη.</span><span class="sxs-lookup"><span data-stu-id="befdb-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="befdb-139">![Διαδρομή σχέσης κατά τη δημιουργία τμήματος](media/segments-multiple-relationships.png "Διαδρομή σχέσης κατά τη δημιουργία τμήματος")</span><span class="sxs-lookup"><span data-stu-id="befdb-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="befdb-140">Επιλέξτε **Αποθήκευση** για να αποθηκευτεί το τμήμα σας.</span><span class="sxs-lookup"><span data-stu-id="befdb-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="befdb-141">Εάν επικυρωθούν όλες οι απαιτήσεις, το τμήμα αγοράς σας θα αποθηκευτεί και θα υποβληθεί σε επεξεργασία.</span><span class="sxs-lookup"><span data-stu-id="befdb-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="befdb-142">Διαφορετικά, θα αποθηκευτεί ως προσχέδιο.</span><span class="sxs-lookup"><span data-stu-id="befdb-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="befdb-143">Επιλέξτε **Επιστροφή στα τμήματα αγοράς** για να επιστρέψετε στη σελίδα **Τμήματα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="befdb-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="befdb-144">Διαχείριση υπαρχόντων τμημάτων αγοράς</span><span class="sxs-lookup"><span data-stu-id="befdb-144">Manage existing segments</span></span>

<span data-ttu-id="befdb-145">Στη σελίδα **Τμήματα αγοράς**, μπορείτε να δείτε όλα τα αποθηκευμένα τμήματα αγοράς και να τα διαχειριστείτε.</span><span class="sxs-lookup"><span data-stu-id="befdb-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="befdb-146">Κάθε τμήμα αντιπροσωπεύεται από μια γραμμή που περιλαμβάνει πρόσθετες πληροφορίες σχετικά με το τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="befdb-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="befdb-147">Μπορείτε να ταξινομήσετε τα τμήματα αγοράς σε μια στήλη επιλέγοντας την επικεφαλίδα της στήλης.</span><span class="sxs-lookup"><span data-stu-id="befdb-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="befdb-148">Χρησιμοποιήστε το πλαίσιο **Αναζήτηση** στην επάνω δεξιά γωνία για να φιλτράρετε τα τμήματα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="befdb-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="befdb-149">![Επιλογές για τη διαχείριση ενός υπάρχοντος τμήματος](media/segments-selected-segment.png "Επιλογές για τη διαχείριση ενός υπάρχοντος τμήματος")</span><span class="sxs-lookup"><span data-stu-id="befdb-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="befdb-150">Οι παρακάτω ενέργειες είναι διαθέσιμες όταν επιλέγετε ένα τμήμα:</span><span class="sxs-lookup"><span data-stu-id="befdb-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="befdb-151">**Προβάλετε** τις λεπτομέρειες του τμήματος αγοράς, συμπεριλαμβανομένης της τάσης πλήθους μελών για μια προεπισκόπηση των μελών τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="befdb-152">**Επεξεργαστείτε** το τμήμα αγοράς για να αλλάξετε τις ιδιότητές του.</span><span class="sxs-lookup"><span data-stu-id="befdb-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="befdb-153">**Ανανεώστε** το τμήμα αγοράς ώστε να συμπεριλάβει τα πιο πρόσφατα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="befdb-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="befdb-154">Προβείτε σε **Ενεργοποίηση** ή **Απενεργοποίηση** του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="befdb-155">Τα τμήματα έχουν δύο πιθανές καταστάσεις - ενεργή ή ανενεργή.</span><span class="sxs-lookup"><span data-stu-id="befdb-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="befdb-156">Αυτές οι καταστάσεις σας χρησιμεύουν όταν επεξεργάζεστε ένα τμήμα.</span><span class="sxs-lookup"><span data-stu-id="befdb-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="befdb-157">Για ανενεργή τμήματα, ο ορισμός του τμήματος υπάρχει, αλλά δεν περιέχει ακόμα κανέναν πελάτη.</span><span class="sxs-lookup"><span data-stu-id="befdb-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="befdb-158">Όταν ενεργοποιείτε ένα τμήμα, η κατάστασή του αλλάζει από "Ανενεργή" σε "Ενεργή" και αρχίζει να αναζητά πελάτες που συμφωνούν με τον ορισμό του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="befdb-159">Εάν έχει ρυθμιστεί μια [προγραμματισμένη ανανέωση](system.md#schedule-tab), τα ανενεργά τμήματα έχουν την **Κατάσταση** ως **Παραλείφθηκε**, υποδηλώνοντας ότι δεν επιχειρήθηκε καν η ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="befdb-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="befdb-160">Όταν ένα ανενεργό τμήμα έχει ενεργοποιηθεί, θα ανανεωθεί και θα συμπεριληφθεί στις προγραμματισμένες ανανεώσεις.</span><span class="sxs-lookup"><span data-stu-id="befdb-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="befdb-161">Εναλλακτικά, μπορείτε να χρησιμοποιήσετε τη λειτουργία **Προγραμματισμός αργότερα** στην αναπτυσσόμενη λίστα **Ενεργοποίηση/απενεργοποίηση** για να καθορίσετε μια μελλοντική ημερομηνία και ώρα για την ενεργοποίηση και την απενεργοποίηση ενός συγκεκριμένου τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="befdb-162">Κάντε **Μετονομασία** του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-162">**Rename** the segment.</span></span>
- <span data-ttu-id="befdb-163">**Πραγματοποιήστε λήψη** της λίστας μελών ως αρχείο .CSV.</span><span class="sxs-lookup"><span data-stu-id="befdb-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="befdb-164">Η επιλογή **Προσθήκη σε** αποστέλλει τη λίστα των αναγνωριστικών πελατών στο τμήμα για επεξεργασία σε άλλη εφαρμογή.</span><span class="sxs-lookup"><span data-stu-id="befdb-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="befdb-165">Κάντε **Διαγραφή** του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="befdb-166">Ανανέωση τμημάτων</span><span class="sxs-lookup"><span data-stu-id="befdb-166">Refresh segments</span></span>

<span data-ttu-id="befdb-167">Μπορείτε να ανανεώσετε όλα τα τμήματα ταυτόχρονα επιλέγοντας **Ανανέωση όλων** στη σελίδα **Τμήματα** ή μπορείτε να ανανεώσετε ένα ή περισσότερα τμήματα όταν τα επιλέγετε και να επιλέξετε **Ανανέωση** από τις επιλογές.</span><span class="sxs-lookup"><span data-stu-id="befdb-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="befdb-168">Εναλλακτικά, μπορείτε να ρυθμίσετε τις παραμέτρους μιας επαναλαμβανόμενης ανανέωσης στα στοιχεία **Διαχείριση** > **Σύστημα** > **Χρονοδιάγραμμα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="befdb-169">Υπάρχουν [έξι τύποι κατάστασης](system.md#status-types) για εργασίες/διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="befdb-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="befdb-170">Επιπλέον, οι περισσότερες διεργασίες [εξαρτώνται από άλλες διεργασίες κατάντη](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="befdb-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="befdb-171">Μπορείτε να επιλέξετε την κατάσταση μιας διεργασίας για να δείτε λεπτομέρειες σχετικά με την πρόοδο ολόκληρου του έργου.</span><span class="sxs-lookup"><span data-stu-id="befdb-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="befdb-172">Αφού επιλέξετε **Προβολή λεπτομερειών** για μία από τις εργασίες του έργου, μπορείτε να βρείτε πρόσθετες πληροφορίες: χρόνος επεξεργασίας, ημερομηνία τελευταίας επεξεργασίας και όλα τα σφάλματα και τις προειδοποιήσεις που σχετίζονται με την εργασία.</span><span class="sxs-lookup"><span data-stu-id="befdb-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="befdb-173">Λήψη και εξαγωγή τμημάτων</span><span class="sxs-lookup"><span data-stu-id="befdb-173">Download and export segments</span></span>

<span data-ttu-id="befdb-174">Μπορείτε να λάβετε τα τμήματα σε ένα αρχείο CSV ή να τα εξαγάγετε στο Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="befdb-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="befdb-175">Λήψη τμημάτων σε ένα αρχείο CSV</span><span class="sxs-lookup"><span data-stu-id="befdb-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="befdb-176">Στις πληροφορίες κοινού, μεταβείτε στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="befdb-177">Επιλέξτε την έλλειψη στο πλακίδιο ενός συγκεκριμένου τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="befdb-178">Επιλέξτε **Λήψη ως CSV** από την αναπτυσσόμενη λίστα "ενέργειες".</span><span class="sxs-lookup"><span data-stu-id="befdb-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="befdb-179">Εξαγωγή τμημάτων στο Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="befdb-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="befdb-180">Πριν από την εξαγωγή τμημάτων στο Dynamics 365 Sales, ένας διαχειριστής πρέπει να [δημιουργήσει τον προορισμό εξαγωγής](export-destinations.md) για το Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="befdb-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="befdb-181">Στις πληροφορίες κοινού, μεταβείτε στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="befdb-182">Επιλέξτε την έλλειψη στο πλακίδιο ενός συγκεκριμένου τμήματος.</span><span class="sxs-lookup"><span data-stu-id="befdb-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="befdb-183">Επιλέξτε **Προσθήκη στο** από την αναπτυσσόμενη λίστα "ενέργειες" και επιλέξτε τον προορισμό εξαγωγής στον οποίο θέλετε να στείλετε τα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="befdb-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="befdb-184">Λειτουργία προσχεδίου για τμήματα αγοράς</span><span class="sxs-lookup"><span data-stu-id="befdb-184">Draft mode for segments</span></span>

<span data-ttu-id="befdb-185">Εάν δεν πληρούνται όλες οι απαιτήσεις για την επεξεργασία ενός τμήματος αγοράς, μπορείτε να αποθηκεύσετε το τμήμα αγοράς ως προσχέδιο και να αποκτήσετε πρόσβαση σε αυτό από τη σελίδα **Τμήματα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="befdb-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="befdb-186">Θα αποθηκευτεί ως ανενεργό τμήμα αγοράς και δεν θα είναι δυνατή η ενεργοποίησή του μέχρι να είναι έγκυρο.</span><span class="sxs-lookup"><span data-stu-id="befdb-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="befdb-187">Προσθήκη περισσότερων συνθηκών σε μια ομάδα</span><span class="sxs-lookup"><span data-stu-id="befdb-187">Add more conditions to a group</span></span>

<span data-ttu-id="befdb-188">Για να προσθέσετε περισσότερες συνθήκες σε μια ομάδα, μπορείτε να χρησιμοποιήσετε δύο λογικούς τελεστές:</span><span class="sxs-lookup"><span data-stu-id="befdb-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="befdb-189">Τελεστής **AND**: Και οι δύο συνθήκες πρέπει να πληρούνται ως μέρος της διεργασίας κατάτμησης.</span><span class="sxs-lookup"><span data-stu-id="befdb-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="befdb-190">Η επιλογή αυτή είναι ιδιαίτερα χρήσιμη όταν καθορίζετε συνθήκες σε διαφορετικές οντότητες.</span><span class="sxs-lookup"><span data-stu-id="befdb-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="befdb-191">Τελεστής **OR**: Κάθε μία από τις συνθήκες πρέπει να πληρούται ως μέρος της διεργασίας κατάτμησης.</span><span class="sxs-lookup"><span data-stu-id="befdb-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="befdb-192">Η επιλογή αυτή είναι ιδιαίτερα χρήσιμη όταν καθορίζετε πολλαπλές συνθήκες για την ίδια οντότητα.</span><span class="sxs-lookup"><span data-stu-id="befdb-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="befdb-193">![Τελεστής OR όπου είτε η μία είτε η άλλη συνθήκη πρέπει να πληρούται](media/segmentation-either-condition.png "Τελεστής OR όπου είτε η μία είτε η άλλη συνθήκη πρέπει να πληρούται")</span><span class="sxs-lookup"><span data-stu-id="befdb-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="befdb-194">Προς το παρόν, είναι δυνατή η ένθεση ενός τελεστή **OR** σε έναν τελεστή **AND** αλλά όχι το αντίστροφο.</span><span class="sxs-lookup"><span data-stu-id="befdb-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="befdb-195">Συνδυασμός πολλών ομάδων</span><span class="sxs-lookup"><span data-stu-id="befdb-195">Combine multiple groups</span></span>

<span data-ttu-id="befdb-196">Κάθε ομάδα παράγει ένα συγκεκριμένο σύνολο πελατών.</span><span class="sxs-lookup"><span data-stu-id="befdb-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="befdb-197">Μπορείτε να συνδυάσετε αυτές τις ομάδες για να συμπεριλάβετε τους πελάτες που απαιτούνται για την επιχειρηματική σας υπόθεση.</span><span class="sxs-lookup"><span data-stu-id="befdb-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="befdb-198">Στις πληροφορίες κοινού, μεταβείτε στη σελίδα **Τμήματα** και επιλέξτε ένα τμήμα.</span><span class="sxs-lookup"><span data-stu-id="befdb-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="befdb-199">Επιλέξτε **Προσθήκη Ομάδας**.</span><span class="sxs-lookup"><span data-stu-id="befdb-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="befdb-200">![Ομάδα πελατών προσθήκη ομάδας](media/customer-group-add-group.png "Ομάδα πελατών προσθήκη ομάδας")</span><span class="sxs-lookup"><span data-stu-id="befdb-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="befdb-201">Επιλέξτε έναν από τους ακόλουθους καθορισμένους τελεστές: **Ένωση**, **Επικαλυπτόμενη** ή **Εξαίρεση**.</span><span class="sxs-lookup"><span data-stu-id="befdb-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="befdb-202">![Προσθήκη ένωσης ομάδας πελατών](media/customer-group-union.png "Προσθήκη ένωσης ομάδας πελατών")</span><span class="sxs-lookup"><span data-stu-id="befdb-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="befdb-203">Επιλέξτε έναν τελεστή συνόλου για να ορίσετε μια νέα ομάδα.</span><span class="sxs-lookup"><span data-stu-id="befdb-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="befdb-204">Αποθηκεύστε διάφορες ομάδες για να καθορίσετε ποια δεδομένα θα διατηρούνται:</span><span class="sxs-lookup"><span data-stu-id="befdb-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="befdb-205">Η **Ένωση** ενώνει τις δύο ομάδες.</span><span class="sxs-lookup"><span data-stu-id="befdb-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="befdb-206">Η **Τομή** επικαλύπτει τις δύο ομάδες.</span><span class="sxs-lookup"><span data-stu-id="befdb-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="befdb-207">Μόνο τα δεδομένα που *είναι κοινά* και για τις δύο ομάδες διατηρούνται στην ενοποιημένη ομάδα.</span><span class="sxs-lookup"><span data-stu-id="befdb-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="befdb-208">Με την **Εξαίρεση** συνδυάζονται οι δύο ομάδες.</span><span class="sxs-lookup"><span data-stu-id="befdb-208">**Except** combines the two groups.</span></span> <span data-ttu-id="befdb-209">Μόνο τα δεδομένα στην ομάδα Α που *δεν είναι κοινά* με τα δεδομένα στην ομάδα Β διατηρούνται.</span><span class="sxs-lookup"><span data-stu-id="befdb-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="befdb-210">Προβολή ιστορικού επεξεργασίας και μελών τμήματος αγοράς</span><span class="sxs-lookup"><span data-stu-id="befdb-210">View processing history and segment members</span></span>

<span data-ttu-id="befdb-211">Μπορείτε να δείτε τα ενοποιημένα δεδομένα σχετικά με ένα τμήμα αγοράς, εξετάζοντας τις λεπτομέρειές του.</span><span class="sxs-lookup"><span data-stu-id="befdb-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="befdb-212">Στη σελίδα **Τμήματα**, επιλέξτε το τμήμα αγοράς το οποίο θέλετε να ελέγξετε.</span><span class="sxs-lookup"><span data-stu-id="befdb-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="befdb-213">Το επάνω μέρος της σελίδας περιλαμβάνει ένα γράφημα τάσεων που απεικονίζει τις αλλαγές στο πλήθος μελών.</span><span class="sxs-lookup"><span data-stu-id="befdb-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="befdb-214">Τοποθετήστε το δείκτη του ποντικιού πάνω από τα σημεία δεδομένων για να δείτε το πλήθος μελών σε μια συγκεκριμένη ημερομηνία.</span><span class="sxs-lookup"><span data-stu-id="befdb-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="befdb-215">Μπορείτε να ενημερώσετε το χρονικό πλαίσιο της απεικόνισης.</span><span class="sxs-lookup"><span data-stu-id="befdb-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="befdb-216">![Εύρος χρόνου τμήματος αγοράς](media/segment-time-range.png "Εύρος χρόνου τμήματος αγοράς")</span><span class="sxs-lookup"><span data-stu-id="befdb-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="befdb-217">Το κάτω μέρος περιέχει μια λίστα με τα μέλη του τμήματος αγοράς.</span><span class="sxs-lookup"><span data-stu-id="befdb-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="befdb-218">Τα πεδία που εμφανίζονται σε αυτήν τη λίστα βασίζονται στα χαρακτηριστικά των οντοτήτων του τμήματος αγοράς σας.</span><span class="sxs-lookup"><span data-stu-id="befdb-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="befdb-219">Η λίστα είναι μια προεπισκόπηση των μελών του αντίστοιχου τμήματος και εμφανίζει τις πρώτες 100 καρτέλες του τμήματος αγοράς σας, ώστε να μπορείτε να τις αξιολογήσετε γρήγορα και να ελέγξετε τους ορισμούς της, εάν είναι απαραίτητο.</span><span class="sxs-lookup"><span data-stu-id="befdb-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="befdb-220">Για να δείτε όλες τις καρτέλες που διαθέτουν αντιστοιχία, θα πρέπει να κάνετε [εξαγωγή του τμήματος αγοράς](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="befdb-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="befdb-221">Γρήγορα τμήματα</span><span class="sxs-lookup"><span data-stu-id="befdb-221">Quick segments</span></span>

<span data-ttu-id="befdb-222">Εκτός από το τμήμα δόμησης, υπάρχει μια άλλη διαδρομή για τη δημιουργία τμημάτων.</span><span class="sxs-lookup"><span data-stu-id="befdb-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="befdb-223">Τα γρήγορα τμήματα σάς επιτρέπουν να δημιουργείτε απλά τμήματα (με έναν μόνο τελεστή) γρήγορα και με άμεσες πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="befdb-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="befdb-224">Στη σελίδα **Τμήματα**, επιλέξτε **Νέο** > **Γρήγορη δημιουργία από**.</span><span class="sxs-lookup"><span data-stu-id="befdb-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="befdb-225">Επιλέξτε την επιλογή **Προφίλ** για να δημιουργήσετε ένα τμήμα αγοράς που βασίζεται στην ενοποιημένη οντότητα Πελάτη.</span><span class="sxs-lookup"><span data-stu-id="befdb-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="befdb-226">Επιλέξτε την επιλογή **Μέτρα** για να δημιουργήσετε ένα τμήμα γύρω από κάθε τύπο Χαρακτηριστικού Πελάτη για τις μετρήσεις που έχετε ήδη δημιουργήσει στη σελίδα **Μετρήσεις**.</span><span class="sxs-lookup"><span data-stu-id="befdb-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="befdb-227">Επιλέξτε την επιλογή **Ευφυΐα** για να δημιουργήσετε ένα τμήμα γύρω από μια από τις οντότητες εξόδου που δημιουργήσατε χρησιμοποιώντας είτε τις **Προβλέψεις** είτε **Προσαρμοσμένα μοντέλα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="befdb-228">Στο παράθυρο διαλόγου **Νέο γρήγορο τμήμα**, επιλέξτε ένα χαρακτηριστικό από την αναπτυσσόμενη λίστα **Πεδίο**.</span><span class="sxs-lookup"><span data-stu-id="befdb-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="befdb-229">Το σύστημα θα σας παράσχει μερικές επιπλέον πληροφορίες που θα σας βοηθήσουν να δημιουργήσετε καλύτερα τμήματα αγοράς των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="befdb-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="befdb-230">Για κατηγορικά πεδία, θα παρουσιάσουμε 10 κορυφαίες αριθμήσεις πελατών.</span><span class="sxs-lookup"><span data-stu-id="befdb-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="befdb-231">επιλέξτε μια **Τιμή** και επιλέξτε **Αναθεώρηση**.</span><span class="sxs-lookup"><span data-stu-id="befdb-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="befdb-232">Για ένα αριθμητικό χαρακτηριστικό, το σύστημα θα εμφανίσει ποια τιμή χαρακτηριστικού εμπίπτει στο εκατοστημόριο του κάθε πελάτη.</span><span class="sxs-lookup"><span data-stu-id="befdb-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="befdb-233">Επιλέξτε έναν **Τελεστή** και μια **Τιμή** και, στη συνέχεια επιλέξτε **Αναθεώρηση**.</span><span class="sxs-lookup"><span data-stu-id="befdb-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="befdb-234">Το σύστημα θα σας παράσχει με ένα **Εκτιμώμενο μέγεθος τμήματος αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="befdb-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="befdb-235">Μπορείτε να επιλέξετε αν θα δημιουργήσετε το τμήμα αγοράς που έχετε ορίσει ή θα το επισκεφτείτε εκ νέου για να αποκτήσετε διαφορετικό μέγεθος τμήματος αγοράς.</span><span class="sxs-lookup"><span data-stu-id="befdb-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="befdb-236">![Όνομα και εκτίμηση για ένα γρήγορο τμήμα αγοράς](media/quick-segment-name.png "Όνομα και εκτίμηση για ένα γρήγορο τμήμα αγοράς")</span><span class="sxs-lookup"><span data-stu-id="befdb-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="befdb-237">Πληκτρολογήστε ένα **Όνομα** για το τμήμα αγοράς σας.</span><span class="sxs-lookup"><span data-stu-id="befdb-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="befdb-238">Προαιρετικά πληκτρολογήστε ένα **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="befdb-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="befdb-239">Πατήστε **Αποθήκευση** για να δημιουργηθεί το τμήμα σας.</span><span class="sxs-lookup"><span data-stu-id="befdb-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="befdb-240">Αφού ολοκληρωθεί η επεξεργασία του τμήματος αγοράς, μπορείτε να το προβάλετε όπως οποιοδήποτε άλλο τμήμα που δημιουργήσατε.</span><span class="sxs-lookup"><span data-stu-id="befdb-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="befdb-241">Για τα παρακάτω σενάρια, συνιστούμε τη χρήση του εργαλείου δόμησης τμημάτων και όχι της δυνατότητας συνιστώμενων τμημάτων:</span><span class="sxs-lookup"><span data-stu-id="befdb-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="befdb-242">Δημιουργία τμημάτων με φίλτρα σε πεδία κατηγοριών όπου ο τελεστής είναι διαφορετικός από τον τελεστή **Is**</span><span class="sxs-lookup"><span data-stu-id="befdb-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="befdb-243">Δημιουργία τμημάτων αγοράς με φίλτρα σε αριθμητικά πεδία, όπου ο τελεστής είναι διαφορετικός από τους τελεστές **Μεταξύ**, **Μεγαλύτερο από** και **Μικρότερο από**</span><span class="sxs-lookup"><span data-stu-id="befdb-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="befdb-244">Δημιουργία τμημάτων με φίλτρα σε πεδία τύπου ημερομηνίας</span><span class="sxs-lookup"><span data-stu-id="befdb-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="befdb-245">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="befdb-245">Next steps</span></span>

<span data-ttu-id="befdb-246">[Εξαγάγετε ένα τμήμα αγοράς](export-destinations.md) και εξερευνήστε την [Καρτέλα πελάτη](customer-card-add-in.md) και τους [Συνδέσμους](export-power-bi.md) για να λάβετε πληροφορίες σχετικά με το επίπεδο του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="befdb-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]