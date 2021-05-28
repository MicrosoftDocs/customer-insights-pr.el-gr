---
title: Προτεινόμενα τμήματα με βάση τη δραστηριότητα.
description: Αφήστε την Εκμάθηση μηχανής να σας βοηθήσει να βρείτε νέα και ενδιαφέροντα τμήματα της αγοράς με βάση τη δραστηριότητα των πελατών.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034075"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="1daef-103">Προτεινόμενα τμήματα με βάση τα δεδομένα δραστηριότητας (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="1daef-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="1daef-104">Ανακαλύψτε ενδιαφέροντα τμήματα αγοράς των πελατών σας με βάση τα δεδομένα δραστηριότητας του πελάτη που έχουν εισαχθεί στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1daef-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="1daef-105">Παραδείγματα δεδομένων δραστηριότητας είναι οι συναλλαγές, η διάρκεια κλήσεων υποστήριξης, οι αγορές ή οι επιστροφές.</span><span class="sxs-lookup"><span data-stu-id="1daef-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="1daef-106">Για να προτείνουν τμήματα, τα δεδομένα δραστηριότητας αναλύονται για επικαιρότητα, συχνότητα και χρηματική αξία (ή διάρκεια).</span><span class="sxs-lookup"><span data-stu-id="1daef-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="1daef-107">Εναλλακτικά, μπορείτε να δημιουργήσετε [προτεινόμενα τμήματα της αγοράς για τη βελτίωση μιας μέτρησης ή για την καλύτερη κατανόηση του τι επηρεάζει ένα χαρακτηριστικό](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="1daef-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Καρτέλα προτεινόμενων τμημάτων που εμφανίζει προτάσεις τμημάτων αγοράς που βασίζονται σε δραστηριότητες και τμήματα που βασίζονται σε χαρακτηριστικά.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="1daef-109">Κατηγοριοποίηση των πελατών ανά δραστηριότητα</span><span class="sxs-lookup"><span data-stu-id="1daef-109">Categorize customers by activity</span></span>

<span data-ttu-id="1daef-110">Όταν τα [δεδομένα δραστηριότητας](activities.md) είναι διαθέσιμα στο Customer Insights, μπορούμε να δημιουργήσετε προτάσεις που αντιπροσωπεύουν τις ομάδες πελατών:</span><span class="sxs-lookup"><span data-stu-id="1daef-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="1daef-111">πιο ενεργοί πελάτες</span><span class="sxs-lookup"><span data-stu-id="1daef-111">most active customers</span></span> 
- <span data-ttu-id="1daef-112">πελάτες που έχουν κάνει τις περισσότερες αγορές</span><span class="sxs-lookup"><span data-stu-id="1daef-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="1daef-113">πελάτες που παράγουν τα περισσότερα έσοδα</span><span class="sxs-lookup"><span data-stu-id="1daef-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="1daef-114">πελάτες που δεν ήταν ενεργοί πρόσφατα</span><span class="sxs-lookup"><span data-stu-id="1daef-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="1daef-115">πελάτες που αλληλεπιδρούν συχνά με την επιχείρησή σας</span><span class="sxs-lookup"><span data-stu-id="1daef-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="1daef-116">Εάν έχετε μια επιχείρηση λιανικής, θα μπορούσατε να μάθετε ποιοι πελάτες παράγουν τα περισσότερα έσοδα και να τους ανταμείψετε με κουπόνι.</span><span class="sxs-lookup"><span data-stu-id="1daef-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="1daef-117">Εναλλακτικά, μπορείτε να αναγνωρίσετε περιστασιακούς πελάτες και να τους προσφέρετε να συμμετάσχουν σε ένα πρόγραμμα επιβραβεύσεων, ώστε να επισκέπτονται την επιχείρησή σας πιο συχνά.</span><span class="sxs-lookup"><span data-stu-id="1daef-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="1daef-118">Εάν ασχολείστε με δραστηριότητες παροχής υγειονομικής περίθαλψης και ο στόχος σας είναι η ελαχιστοποίηση των δαπανών για μεμονωμένους ασθενείς.</span><span class="sxs-lookup"><span data-stu-id="1daef-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="1daef-119">Ένας τρόπος για να το κάνετε αυτό θα μπορούσε να είναι να μειώσετε τις επαναλαμβανόμενες επισκέψεις παρέχοντας τη βέλτιστη δυνατή προσοχή σε όσο το δυνατό λιγότερες επισκέψεις.</span><span class="sxs-lookup"><span data-stu-id="1daef-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="1daef-120">Σε αυτή την περίπτωση, ο στόχος σας είναι να διατηρήσετε τη συχνότητα επισκέψεων σε χαμηλά επίπεδα και να ελαχιστοποιήσετε το επαναλαμβανόμενο κόστος για τους ασθενείς.</span><span class="sxs-lookup"><span data-stu-id="1daef-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="1daef-121">Εναλλακτικά, μπορείτε να προσδιορίσετε κατηγορίες ασθενών που έχουν συχνές συναντήσεις και μεγάλο επαναλαμβανόμενο κόστος και να αναλύσετε αυτές τις υποθέσεις με σκοπό τη βελτίωση της αποτελεσματικότητας του κάθε ατόμου.</span><span class="sxs-lookup"><span data-stu-id="1daef-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="1daef-122">Απαιτούμενα δεδομένα</span><span class="sxs-lookup"><span data-stu-id="1daef-122">Required data</span></span>

<span data-ttu-id="1daef-123">Δημιουργούνται προτάσεις με βάση τα επιλεγμένα δεδομένα εισόδου.</span><span class="sxs-lookup"><span data-stu-id="1daef-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="1daef-124">Προφίλ πελατών: Όλοι οι πελάτες ή τα μέλη ενός συγκεκριμένου τμήματος της αγοράς.</span><span class="sxs-lookup"><span data-stu-id="1daef-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="1daef-125">Χρονική περίοδος: Τελευταίος μήνας, τελευταίο έτος ή οποιοδήποτε προσαρμοσμένο χρονικό πλαίσιο.</span><span class="sxs-lookup"><span data-stu-id="1daef-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="1daef-126">Τύπος δραστηριότητας: αγορές, συναλλαγές λιανικής, ηλεκτρονικές συναλλαγές, υποθέσεις υποστήριξης πελατών, συνδρομές κ.ο.κ.</span><span class="sxs-lookup"><span data-stu-id="1daef-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="1daef-127">Οντότητα στο Customer Insights που περιέχει τα δεδομένα δραστηριότητας: Η οντότητα UnifiedActivity ή η οντότητα για μια συγκεκριμένη δραστηριότητα.</span><span class="sxs-lookup"><span data-stu-id="1daef-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="1daef-128">Τις διαστάσεις που θα περιλαμβάνονται: Επικαιρότητα, συχνότητα ή νομισματικές διαστάσεις, ανάλογα με τις επιχειρηματικές σας απαιτήσεις.</span><span class="sxs-lookup"><span data-stu-id="1daef-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="1daef-129">Δημιουργήστε τα προτεινόμενα τμήματα</span><span class="sxs-lookup"><span data-stu-id="1daef-129">Generate suggested segments</span></span>

1. <span data-ttu-id="1daef-130">Μετάβαση στα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="1daef-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="1daef-131">Επιλέξτε την καρτέλα **Προτάσεις (προεπισκόπηση)**.</span><span class="sxs-lookup"><span data-stu-id="1daef-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="1daef-132">Επιλέξτε **Εύρεση νέων προτάσεων** και επιλέξτε **Δείτε ή προβλέψτε τη συμπεριφορά των πελατών**.</span><span class="sxs-lookup"><span data-stu-id="1daef-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="1daef-133">Επιλέξτε **Έναρξη** για να εκτελέσετε την καθοδηγούμενη εμπειρία.</span><span class="sxs-lookup"><span data-stu-id="1daef-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Το πρώτο βήμα του οδηγού ρύθμισης παραμέτρων για ένα προτεινόμενο τμήμα της αγοράς βάσει της δραστηριότητας.":::

1. <span data-ttu-id="1daef-135">Δώστε τα απαιτούμενα δεδομένα εισόδου και επιλέξτε **Επόμενο βήμα**.</span><span class="sxs-lookup"><span data-stu-id="1daef-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="1daef-136">Επιλέξτε πελάτες: Συμπεριλάβετε όλους τους πελάτες ή ένα συγκεκριμένο τμήμα της αγοράς.</span><span class="sxs-lookup"><span data-stu-id="1daef-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="1daef-137">Επιλέξτε δραστηριότητα: Επιλέξτε τον τύπο δραστηριότητας και τις οντότητες που περιγράφουν τη δραστηριότητα.</span><span class="sxs-lookup"><span data-stu-id="1daef-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="1daef-138">Προτιμήσεις: Ορίστε τη χρονική περίοδο που θα εξετάσετε, τους παράγοντες για προτάσεις και αντιστοιχίστε τα χαρακτηριστικά.</span><span class="sxs-lookup"><span data-stu-id="1daef-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="1daef-139">Εξετάστε τα δεδομένα εισαγωγής σας και επιλέξτε **Εκτέλεση** για να εκτελέσετε το μοντέλο και δημιουργήσετε προτάσεις.</span><span class="sxs-lookup"><span data-stu-id="1daef-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="1daef-140">Ανάλογα με τον αριθμό των προφίλ πελατών και τις επιλεγμένες δραστηριότητες, μπορεί να διαρκέσει μερικά λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="1daef-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="1daef-141">Αφού δημιουργήσετε τις προτάσεις, μπορείτε να τις φιλτράρετε με κριτήριο το μέγεθος ή την τιμή που σας ενδιαφέρει περισσότερο.</span><span class="sxs-lookup"><span data-stu-id="1daef-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="1daef-142">Προβολή λεπτομερειών ενός προτεινόμενου τμήματος</span><span class="sxs-lookup"><span data-stu-id="1daef-142">View details of a suggested segment</span></span>

<span data-ttu-id="1daef-143">Αφού δημιουργηθούν οι προτάσεις, θα τις βρείτε στη λίστα **Τμήματα** > **Προτάσεις (προεπισκόπηση)** στην ενότητα **Προτάσεις που βασίζονται σε δραστηριότητα**.</span><span class="sxs-lookup"><span data-stu-id="1daef-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Αναπτυγμένο πλαϊνό τμήμα παραθύρου που εμφανίζει λεπτομερή δεδομένα ενός προτεινόμενου τμήματος της αγοράς.":::

<span data-ttu-id="1daef-145">Επιλέξτε **Εμφάνιση πρότασης** για ένα προτεινόμενο τμήμα της αγοράς για να προβάλετε τις λεπτομέρειες αυτού του τμήματος της αγοράς.</span><span class="sxs-lookup"><span data-stu-id="1daef-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="1daef-146">Το πλαϊνό τμήμα παραθύρου παρέχει λεπτομέρειες όπως η περιοχή κάθε διάστασης σε σύγκριση με την ομάδα προορισμού.</span><span class="sxs-lookup"><span data-stu-id="1daef-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="1daef-147">Επισημαίνει επίσης τον αριθμό των πιθανών μελών στην κατηγορία και το αντίστοιχο ποσοστό του συνόλου πελατών.</span><span class="sxs-lookup"><span data-stu-id="1daef-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="1daef-148">Εάν θέλετε να διατηρήσετε την πρόταση ως τμήμα, επιλέξτε **Δημιουργία τμήματος**.</span><span class="sxs-lookup"><span data-stu-id="1daef-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="1daef-149">Αποθήκευση μιας πρότασης ως τμήματος</span><span class="sxs-lookup"><span data-stu-id="1daef-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="1daef-150">Μεταβείτε στα **Τμήματα** > **Προτάσεις (προεπισκόπηση)**.</span><span class="sxs-lookup"><span data-stu-id="1daef-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="1daef-151">Επιλέξτε το τμήμα αγοράς που θέλετε να αποθηκεύσετε.</span><span class="sxs-lookup"><span data-stu-id="1daef-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="1daef-152">Στο πλαϊνό τμήμα παραθύρου, επιλέξτε **Δημιουργία τμήματος**.</span><span class="sxs-lookup"><span data-stu-id="1daef-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="1daef-153">Αφού αποθηκεύσετε το τμήμα, θα εμφανιστεί στη λίστα τμημάτων της καρτέλας **Όλα τα τμήματα**. Τώρα μπορεί να [ανανεωθεί ή να διαγραφεί, όπως κάθε άλλο τμήμα](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1daef-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="1daef-154">Δεν μπορείτε να επεξεργαστείτε τις λεπτομέρειες του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="1daef-154">You can't edit the segment details.</span></span> <span data-ttu-id="1daef-155">Ωστόσο, μπορείτε να αλλάξετε τα κριτήρια εισόδου για τις προτάσεις και να δημιουργήσετε διαφορετικές προτάσεις.</span><span class="sxs-lookup"><span data-stu-id="1daef-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="1daef-156">Ανανέωση ή επεξεργασία ενός συνόλου προτάσεων</span><span class="sxs-lookup"><span data-stu-id="1daef-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="1daef-157">Μεταβείτε στην επιλογή **Τμήματα** > **Προτάσεις (προεπισκόπηση)** και αναζητήστε το τμήμα στην ενότητας **Προτάσεις που βασίζονται σε δραστηριότητα**.</span><span class="sxs-lookup"><span data-stu-id="1daef-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="1daef-158">Επιλέξτε **Ανανέωση προτάσεων** για να ανανεώσετε τις προτάσεις, διατηρώντας παράλληλα τα ρυθμισμένα χαρακτηριστικά.</span><span class="sxs-lookup"><span data-stu-id="1daef-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="1daef-159">Εναλλακτικά, επιλέξτε **Επεξεργασία προτάσεων** για τροποποίηση των ρυθμισμένων χαρακτηριστικών.</span><span class="sxs-lookup"><span data-stu-id="1daef-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="1daef-160">Το σύστημα θα εκτελέσει ξανά τη διαδικασία, θα δημιουργήσει προτάσεις τμημάτων με βάση τα πιο πρόσφατα δεδομένα και θα αντικαταστήσει τις τρέχουσες προτάσεις.</span><span class="sxs-lookup"><span data-stu-id="1daef-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
