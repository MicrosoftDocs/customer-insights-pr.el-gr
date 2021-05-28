---
title: Δημιουργία και διαχείριση τμημάτων
description: Δημιουργήστε τμήματα πελατών για να τα ομαδοποιήσετε βάσει διαφόρων χαρακτηριστικών.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064937"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="fac87-103">Δημιουργία και διαχείριση τμημάτων</span><span class="sxs-lookup"><span data-stu-id="fac87-103">Create and manage segments</span></span>

<span data-ttu-id="fac87-104">Καθορίστε πολύπλοκα φίλτρα γύρω από την ενοποιημένη οντότητα πελάτη και τις σχετικές της οντότητες.</span><span class="sxs-lookup"><span data-stu-id="fac87-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="fac87-105">Κάθε τμήμα, μετά την επεξεργασία, δημιουργεί ένα σύνολο καρτελών πελατών, το οποίο μπορείτε να εξαγάγετε και αναφορικά με το οποίο να αναλάβετε δράση.</span><span class="sxs-lookup"><span data-stu-id="fac87-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="fac87-106">Τα τμήματα διαχειριζόμαστε στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="fac87-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="fac87-107">Το παρακάτω παράδειγμα παρουσιάζει τη δυνατότητα κατακερματισμού.</span><span class="sxs-lookup"><span data-stu-id="fac87-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="fac87-108">Έχουμε καθορίσει ένα τμήμα αγοράς για πελάτες που έχουν παραγγείλει προΪόντα αξίας τουλάχιστον $500 τις τελευταίες 90 ημέρες *και* οι οποίοι συμμετείχαν σε μια κλήση εξυπηρέτησης πελατών που κλιμακώθηκε.</span><span class="sxs-lookup"><span data-stu-id="fac87-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Στιγμιότυπο οθόνης του περιβάλλοντος εργασίας χρήστη του τμήματος με δύο ομάδες που καθορίζουν ένα τμήμα πελάτη.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="fac87-110">Δημιουργία νέου τμήματος</span><span class="sxs-lookup"><span data-stu-id="fac87-110">Create a new segment</span></span>

<span data-ttu-id="fac87-111">Υπάρχουν πολλοί τρόποι για τη δημιουργία ενός νέου τμήματος.</span><span class="sxs-lookup"><span data-stu-id="fac87-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="fac87-112">Αυτή η ενότητα περιγράφει τον τρόπο δημιουργίας ενός *κενού τμήματος* από την αρχή.</span><span class="sxs-lookup"><span data-stu-id="fac87-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="fac87-113">Μπορείτε επίσης να δημιουργήσετε ένα *γρήγορο τμήμα* με βάση υπάρχουσες οντότητες ή να χρησιμοποιήσετε τα μοντέλα εκμάθησης μηχανής για να λάβετε *προτεινόμενα τμήματα*.</span><span class="sxs-lookup"><span data-stu-id="fac87-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="fac87-114">Περισσότερες πληροφορίες: [Επισκόπηση τμημάτων](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fac87-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="fac87-115">Κατά τη δημιουργία ενός τμήματος, μπορείτε να αποθηκεύσετε ένα προσχέδιο.</span><span class="sxs-lookup"><span data-stu-id="fac87-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="fac87-116">Θα αποθηκευτεί ως ανενεργό τμήμα και δεν είναι δυνατή η ενεργοποίησή του μέχρι να ολοκληρωθεί με έγκυρη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="fac87-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="fac87-117">Μετάβαση στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="fac87-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="fac87-118">Επιλέξτε **Νέο** > **Κενό τμήμα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="fac87-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="fac87-119">Στο τμήμα παραθύρου **Νέο τμήμα**, επιλέξτε έναν τύπο τμήματος:</span><span class="sxs-lookup"><span data-stu-id="fac87-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="fac87-120">Τα **δυναμικά τμήματα** [ανανεώνονται](segments.md#refresh-segments) με επαναλαμβανόμενο χρονοδιάγραμμα.</span><span class="sxs-lookup"><span data-stu-id="fac87-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="fac87-121">Τα **στατικά τμήματα** εκτελούνται μία φορά όταν τα δημιουργείτε.</span><span class="sxs-lookup"><span data-stu-id="fac87-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="fac87-122">Δώστε ένα **όνομα οντότητας εξόδου** για το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="fac87-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="fac87-123">Προαιρετικά, δώστε ένα εμφανιζόμενο όνομα και μια περιγραφή που θα σας βοηθήσει να προσδιορίσετε το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="fac87-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="fac87-124">Επιλέξτε **Επόμενο** για να μεταβείτε στη σελίδα **Δόμηση τμήματος** όπου καθορίζετε μια ομάδα.</span><span class="sxs-lookup"><span data-stu-id="fac87-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="fac87-125">Μια ομάδα είναι ένα σύνολο πελατών.</span><span class="sxs-lookup"><span data-stu-id="fac87-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="fac87-126">Επιλέξτε την οντότητα που περιλαμβάνει το χαρακτηριστικό με βάση το οποίο θέλετε να κάνετε κατάτμηση.</span><span class="sxs-lookup"><span data-stu-id="fac87-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="fac87-127">Επιλέξτε το χαρακτηριστικό με βάση το οποίο θα δημιουργηθεί το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="fac87-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="fac87-128">Αυτό το χαρακτηριστικό μπορεί να έχει έναν από τους τέσσερις τύπους τιμών: αριθμητική, συμβολοσειρά, ημερομηνία ή δυαδική τιμή.</span><span class="sxs-lookup"><span data-stu-id="fac87-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="fac87-129">Επιλέξτε έναν τελεστή και μια τιμή για το επιλεγμένο χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="fac87-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fac87-130">![Φίλτρο προσαρμοσμένης ομάδας](media/customer-group-numbers.png "Φίλτρο ομάδας πελατών")</span><span class="sxs-lookup"><span data-stu-id="fac87-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="fac87-131">Αριθμός</span><span class="sxs-lookup"><span data-stu-id="fac87-131">Number</span></span> |<span data-ttu-id="fac87-132">Ορισμός</span><span class="sxs-lookup"><span data-stu-id="fac87-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="fac87-133">1</span><span class="sxs-lookup"><span data-stu-id="fac87-133">1</span></span>     |<span data-ttu-id="fac87-134">Entity</span><span class="sxs-lookup"><span data-stu-id="fac87-134">Entity</span></span>          |
   |<span data-ttu-id="fac87-135">2</span><span class="sxs-lookup"><span data-stu-id="fac87-135">2</span></span>     |<span data-ttu-id="fac87-136">Χαρακτηριστικό</span><span class="sxs-lookup"><span data-stu-id="fac87-136">Attribute</span></span>          |
   |<span data-ttu-id="fac87-137">3</span><span class="sxs-lookup"><span data-stu-id="fac87-137">3</span></span>    |<span data-ttu-id="fac87-138">Τελεστής</span><span class="sxs-lookup"><span data-stu-id="fac87-138">Operator</span></span>         |
   |<span data-ttu-id="fac87-139">4</span><span class="sxs-lookup"><span data-stu-id="fac87-139">4</span></span>    |<span data-ttu-id="fac87-140">Τιμή</span><span class="sxs-lookup"><span data-stu-id="fac87-140">Value</span></span>         |

   1. <span data-ttu-id="fac87-141">Για να προσθέσετε περισσότερες συνθήκες σε μια ομάδα, μπορείτε να χρησιμοποιήσετε δύο λογικούς τελεστές:</span><span class="sxs-lookup"><span data-stu-id="fac87-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="fac87-142">Τελεστής **AND**: Και οι δύο συνθήκες πρέπει να πληρούνται ως μέρος της διεργασίας κατάτμησης.</span><span class="sxs-lookup"><span data-stu-id="fac87-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="fac87-143">Η επιλογή αυτή είναι ιδιαίτερα χρήσιμη όταν καθορίζετε συνθήκες σε διαφορετικές οντότητες.</span><span class="sxs-lookup"><span data-stu-id="fac87-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="fac87-144">Τελεστής **OR**: Κάθε μία από τις συνθήκες πρέπει να πληρούται ως μέρος της διεργασίας κατάτμησης.</span><span class="sxs-lookup"><span data-stu-id="fac87-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="fac87-145">Η επιλογή αυτή είναι ιδιαίτερα χρήσιμη όταν καθορίζετε πολλαπλές συνθήκες για την ίδια οντότητα.</span><span class="sxs-lookup"><span data-stu-id="fac87-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="fac87-146">![Τελεστής OR όπου είτε η μία είτε η άλλη συνθήκη πρέπει να πληρούται](media/segmentation-either-condition.png "Τελεστής OR όπου είτε η μία είτε η άλλη συνθήκη πρέπει να πληρούται")</span><span class="sxs-lookup"><span data-stu-id="fac87-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="fac87-147">Προς το παρόν, είναι δυνατή η ένθεση ενός τελεστή **OR** σε έναν τελεστή **AND** αλλά όχι το αντίστροφο.</span><span class="sxs-lookup"><span data-stu-id="fac87-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="fac87-148">Κάθε ομάδα ταιριάζει με ένα σύνολο πελατών.</span><span class="sxs-lookup"><span data-stu-id="fac87-148">Each group matches set of customers.</span></span> <span data-ttu-id="fac87-149">Μπορείτε να συνδυάσετε ομάδες για να συμπεριλάβετε τους πελάτες που απαιτούνται για την επιχειρηματική σας υπόθεση.</span><span class="sxs-lookup"><span data-stu-id="fac87-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="fac87-150">Επιλέξτε **Προσθήκη Ομάδας**.</span><span class="sxs-lookup"><span data-stu-id="fac87-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="fac87-151">![Ομάδα πελατών προσθήκη ομάδας](media/customer-group-add-group.png "Ομάδα πελατών προσθήκη ομάδας")</span><span class="sxs-lookup"><span data-stu-id="fac87-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="fac87-152">Επιλέξτε έναν από τους τελεστές ορισμού: **Ένωση**, **Τομή** ή **Εξαίρεση**.</span><span class="sxs-lookup"><span data-stu-id="fac87-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fac87-153">![Προσθήκη ένωσης ομάδας πελατών](media/customer-group-union.png "Προσθήκη ένωσης ομάδας πελατών")</span><span class="sxs-lookup"><span data-stu-id="fac87-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="fac87-154">Η **Ένωση** ενώνει τις δύο ομάδες.</span><span class="sxs-lookup"><span data-stu-id="fac87-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="fac87-155">Η **Τομή** επικαλύπτει τις δύο ομάδες.</span><span class="sxs-lookup"><span data-stu-id="fac87-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="fac87-156">Μόνο τα δεδομένα που *είναι κοινά* και για τις δύο ομάδες διατηρούνται στην ενοποιημένη ομάδα.</span><span class="sxs-lookup"><span data-stu-id="fac87-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="fac87-157">Με την **Εξαίρεση** συνδυάζονται οι δύο ομάδες.</span><span class="sxs-lookup"><span data-stu-id="fac87-157">**Except** combines the two groups.</span></span> <span data-ttu-id="fac87-158">Μόνο τα δεδομένα στην ομάδα Α που *δεν είναι κοινά* με τα δεδομένα στην ομάδα Β διατηρούνται.</span><span class="sxs-lookup"><span data-stu-id="fac87-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="fac87-159">Εάν η οντότητα είναι συνδεδεμένη με την οντότητα του ενοποιημένου πελάτη μέσω των [σχέσεων](relationships.md), θα πρέπει να καθορίσετε τη διαδρομή σχέσης για να δημιουργήσετε ένα έγκυρο τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="fac87-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="fac87-160">Προσθέστε τις οντότητες από τη διαδρομή σχέσης, μέχρι να επιλέξετε την οντότητα **Πελάτης: CustomerInsights** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="fac87-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="fac87-161">Στη συνέχεια, επιλέξτε **Όλες οι καρτέλες** για κάθε βήμα.</span><span class="sxs-lookup"><span data-stu-id="fac87-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fac87-162">![Διαδρομή σχέσης κατά τη δημιουργία τμήματος](media/segments-multiple-relationships.png "Διαδρομή σχέσης κατά τη δημιουργία τμήματος")</span><span class="sxs-lookup"><span data-stu-id="fac87-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="fac87-163">Από προεπιλογή, τα τμήματα δημιουργούν μια οντότητα εξόδου που περιέχει όλα τα χαρακτηριστικά των προφίλ πελατών τα οποία συμφωνούν με τα καθορισμένα φίλτρα.</span><span class="sxs-lookup"><span data-stu-id="fac87-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="fac87-164">Εάν ένα τμήμα βασίζεται σε άλλες οντότητες από την οντότητα *Πελάτης*, μπορείτε να προσθέσετε περισσότερα χαρακτηριστικά από αυτές τις οντότητες στην οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="fac87-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="fac87-165">Επιλέξτε **χαρακτηριστικά έργου** για να επιλέξετε τα χαρακτηριστικά που θα προσαρτηθούν στην οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="fac87-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="fac87-166">Παράδειγμα: ένα τμήμα βασίζεται σε μια οντότητα που περιέχει δεδομένα δραστηριότητας πελάτη που σχετίζονται με την οντότητα *Πελάτης*.</span><span class="sxs-lookup"><span data-stu-id="fac87-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="fac87-167">Το τμήμα αναζητά όλους τους πελάτες που ονομάζονται στο γραφείο βοήθειας τις τελευταίες 60 ημέρες.</span><span class="sxs-lookup"><span data-stu-id="fac87-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="fac87-168">Μπορείτε να επιλέξετε να προσαρτήσετε τη διάρκεια της κλήσης και τον αριθμό των κλήσεων σε όλες τις καρτέλες πελατών που συμφωνούν στην οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="fac87-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="fac87-169">Αυτές οι πληροφορίες μπορεί να είναι χρήσιμες για να στείλετε ένα μήνυμα ηλεκτρονικού ταχυδρομείου με χρήσιμες συνδέσεις σε άρθρα ηλεκτρονικής βοήθειας και σε συνήθεις ερωτήσεις σε πελάτες που καλούνται συχνά.</span><span class="sxs-lookup"><span data-stu-id="fac87-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="fac87-170">Τα προβλεπόμενα χαρακτηριστικά λειτουργούν μόνο για οντότητες με σχέση "ένα προς πολλά" με την οντότητα πελάτη.</span><span class="sxs-lookup"><span data-stu-id="fac87-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="fac87-171">Για παράδειγμα, ένας πελάτης μπορεί να έχει πολλές συνδρομές.</span><span class="sxs-lookup"><span data-stu-id="fac87-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="fac87-172">Μπορείτε να προβάλλετε χαρακτηριστικά μόνο από μια οντότητα που χρησιμοποιείται σε κάθε ομάδα ερωτημάτων τμημάτων που δομείτε.</span><span class="sxs-lookup"><span data-stu-id="fac87-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="fac87-173">Τα προβλεπόμενα χαρακτηριστικά συνυπολογίζονται κατά τη χρήση τελεστών ορισμού.</span><span class="sxs-lookup"><span data-stu-id="fac87-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="fac87-174">Επιλέξτε **Αποθήκευση** για να αποθηκευτεί το τμήμα σας.</span><span class="sxs-lookup"><span data-stu-id="fac87-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="fac87-175">Εάν επικυρωθούν όλες οι απαιτήσεις, το τμήμα αγοράς σας θα αποθηκευτεί και θα υποβληθεί σε επεξεργασία.</span><span class="sxs-lookup"><span data-stu-id="fac87-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="fac87-176">Διαφορετικά, θα αποθηκευτεί ως προσχέδιο.</span><span class="sxs-lookup"><span data-stu-id="fac87-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="fac87-177">Επιλέξτε **Επιστροφή στα τμήματα αγοράς** για να επιστρέψετε στη σελίδα **Τμήματα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="fac87-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="fac87-178">Γρήγορα τμήματα</span><span class="sxs-lookup"><span data-stu-id="fac87-178">Quick segments</span></span>

<span data-ttu-id="fac87-179">Τα γρήγορα τμήματα σας επιτρέπουν να δημιουργείτε απλά τμήματα, με έναν μόνο τελεστή γρήγορα, για πιο γρήγορη πληροφόρηση.</span><span class="sxs-lookup"><span data-stu-id="fac87-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="fac87-180">Στη σελίδα **Τμήματα**, επιλέξτε **Νέο** > **Δημιουργία από**.</span><span class="sxs-lookup"><span data-stu-id="fac87-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="fac87-181">Επιλέξτε την επιλογή **Προφίλ** για να δημιουργήσετε ένα τμήμα αγοράς που βασίζεται στην οντότητα *ενοποιημένου πελάτη*.</span><span class="sxs-lookup"><span data-stu-id="fac87-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="fac87-182">Ενεργοποιήστε την επιλογή **Μέτρα** για να δημιουργήσετε ένα τμήμα της αγοράς γύρω από τα μέτρα που έχετε δημιουργήσει προηγουμένως.</span><span class="sxs-lookup"><span data-stu-id="fac87-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="fac87-183">Επιλέξτε την επιλογή **Ευφυΐα** για να δημιουργήσετε ένα τμήμα γύρω από μια από τις οντότητες εξόδου που δημιουργήσατε χρησιμοποιώντας είτε τις **Προβλέψεις** είτε **Προσαρμοσμένα μοντέλα**.</span><span class="sxs-lookup"><span data-stu-id="fac87-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="fac87-184">Στο παράθυρο διαλόγου **Νέο γρήγορο τμήμα**, επιλέξτε ένα χαρακτηριστικό από την αναπτυσσόμενη λίστα **Πεδίο**.</span><span class="sxs-lookup"><span data-stu-id="fac87-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="fac87-185">Το σύστημα θα σας παράσχει μερικές επιπλέον πληροφορίες που θα σας βοηθήσουν να δημιουργήσετε καλύτερα τμήματα αγοράς των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="fac87-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="fac87-186">Για κατηγορικά πεδία, θα παρουσιάσουμε 10 κορυφαίες αριθμήσεις πελατών.</span><span class="sxs-lookup"><span data-stu-id="fac87-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="fac87-187">επιλέξτε μια **Τιμή** και επιλέξτε **Αναθεώρηση**.</span><span class="sxs-lookup"><span data-stu-id="fac87-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="fac87-188">Για ένα αριθμητικό χαρακτηριστικό, το σύστημα θα εμφανίσει ποια τιμή χαρακτηριστικού εμπίπτει στο εκατοστημόριο του κάθε πελάτη.</span><span class="sxs-lookup"><span data-stu-id="fac87-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="fac87-189">Επιλέξτε έναν **Τελεστή** και μια **Τιμή** και, στη συνέχεια επιλέξτε **Αναθεώρηση**.</span><span class="sxs-lookup"><span data-stu-id="fac87-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="fac87-190">Το σύστημα θα σας παράσχει με ένα **Εκτιμώμενο μέγεθος τμήματος αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="fac87-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="fac87-191">Μπορείτε να επιλέξετε αν θα δημιουργήσετε το τμήμα αγοράς που έχετε ορίσει ή θα το επισκεφτείτε εκ νέου για να αποκτήσετε διαφορετικό μέγεθος τμήματος αγοράς.</span><span class="sxs-lookup"><span data-stu-id="fac87-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fac87-192">![Όνομα και εκτίμηση για ένα γρήγορο τμήμα αγοράς](media/quick-segment-name.png "Όνομα και εκτίμηση για ένα γρήγορο τμήμα αγοράς")</span><span class="sxs-lookup"><span data-stu-id="fac87-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="fac87-193">Πληκτρολογήστε ένα **Όνομα** για το τμήμα αγοράς σας.</span><span class="sxs-lookup"><span data-stu-id="fac87-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="fac87-194">Προαιρετικά πληκτρολογήστε ένα **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="fac87-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="fac87-195">Πατήστε **Αποθήκευση** για να δημιουργηθεί το τμήμα σας.</span><span class="sxs-lookup"><span data-stu-id="fac87-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="fac87-196">Αφού ολοκληρωθεί η επεξεργασία του τμήματος αγοράς, μπορείτε να το προβάλετε όπως οποιοδήποτε άλλο τμήμα που δημιουργήσατε.</span><span class="sxs-lookup"><span data-stu-id="fac87-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fac87-197">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="fac87-197">Next steps</span></span>

<span data-ttu-id="fac87-198">[Εξαγάγετε ένα τμήμα αγοράς](export-destinations.md) και εξερευνήστε την [Καρτέλα πελάτη](customer-card-add-in.md) και τους [Συνδέσμους](export-power-bi.md) για να λάβετε πληροφορίες σχετικά με το επίπεδο του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="fac87-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
