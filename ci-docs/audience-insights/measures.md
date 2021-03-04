---
title: Δημιουργία και διαχείριση μεγεθών
description: Καθορίστε μεγέθη για να αναλύσετε και να απεικονίσετε την απόδοση της επιχείρησής σας.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269928"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="29b1e-103">Καθορισμός και διαχείριση μέτρων</span><span class="sxs-lookup"><span data-stu-id="29b1e-103">Define and manage measures</span></span>

<span data-ttu-id="29b1e-104">Τα μεγέθη σας βοηθούν να κατανοήσετε καλύτερα τις συμπεριφορές των πελατών και την επιχειρηματική απόδοση, ανακτώντας σχετικές τιμές από [ενοποιημένα προφίλ](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="29b1e-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="29b1e-105">Για παράδειγμα, μια επιχείρηση θέλει να δει τη *συνολική δαπάνη ανά πελάτη* για να κατανοήσει το ιστορικό αγορών μεμονωμένων πελατών.</span><span class="sxs-lookup"><span data-stu-id="29b1e-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="29b1e-106">Ή να μετρήσει *τις συνολικές πωλήσεις της εταιρείας* για να κατανοήσετε τα συγκεντρωτικά έσοδα σε ολόκληρη την επιχείρηση.</span><span class="sxs-lookup"><span data-stu-id="29b1e-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="29b1e-107">Τα μεγέθη δημιουργούνται χρησιμοποιώντας τη δόμηση μεγεθών, μια πλατφόρμα ερωτημάτων δεδομένων με διάφορους τελεστές και απλές επιλογές αντιστοίχισης.</span><span class="sxs-lookup"><span data-stu-id="29b1e-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="29b1e-108">Σας επιτρέπει να φιλτράρετε τα δεδομένα, να ομαδοποιείτε τα αποτελέσματα, να εντοπίζετε [διαδρομές σχέσεων οντοτήτων](relationships.md) και να κάνετε προεπισκόπηση των δεδομένων εξόδου.</span><span class="sxs-lookup"><span data-stu-id="29b1e-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="29b1e-109">Χρησιμοποιήστε τη δόμηση μεγεθών για να σχεδιάσετε επιχειρηματικές δραστηριότητες, κάνοντας ερωτήματα στα δεδομένα των πελατών και εξάγοντας πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="29b1e-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="29b1e-110">Για παράδειγμα, η δημιουργία του μεγέθους *συνολική δαπάνη ανά πελάτη* και *συνολική απόδοση ανά πελάτη* βοηθά στον εντοπισμό μιας ομάδας πελατών με υψηλές δαπάνες αλλά και υψηλή απόδοση.</span><span class="sxs-lookup"><span data-stu-id="29b1e-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="29b1e-111">Μπορείτε να [δημιουργήσετε ένα τμήμα](segments.md) για να οδηγήσετε τις επόμενες καλύτερες ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="29b1e-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="29b1e-112">Δημιουργία νέας μέτρησης</span><span class="sxs-lookup"><span data-stu-id="29b1e-112">Create a measure</span></span>

<span data-ttu-id="29b1e-113">Αυτή η ενότητα σας παρουσιάζει τη δημιουργία ενός νέου μεγέθους από το μηδέν.</span><span class="sxs-lookup"><span data-stu-id="29b1e-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="29b1e-114">Μπορείτε να δημιουργήσετε ένα μέγεθος με χαρακτηριστικά δεδομένων από οντότητες δεδομένων που έχουν ορίσει μια σχέση για σύνδεση με την οντότητα Πελάτη.</span><span class="sxs-lookup"><span data-stu-id="29b1e-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="29b1e-115">Στις πληροφορίες κοινού, μεταβείτε στις **Μετρήσεις**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="29b1e-116">Επιλέξτε **Νέα**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-116">Select **New**.</span></span>

1. <span data-ttu-id="29b1e-117">Επιλέξτε **Επεξεργασία ονόματος** και δώστε ένα **Όνομα** για το μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="29b1e-118">Εάν η νέα ρύθμιση παραμέτρων του μεγέθους έχει μόνο δύο πεδία, CustomerID και έναν υπολογισμό, για παράδειγμα, η έξοδος θα προστεθεί ως νέα στήλη στην οντότητα που δημιουργείται από το σύστημα, που ονομάζεται Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="29b1e-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="29b1e-119">Και θα μπορείτε να δείτε την τιμή του μεγέθους στο ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="29b1e-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="29b1e-120">Άλλα μεγέθη θα δημιουργήσουν τις δικές τους οντότητες.</span><span class="sxs-lookup"><span data-stu-id="29b1e-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="29b1e-121">Στην περιοχή ρύθμισης παραμέτρων, επιλέξτε τη συνάρτηση συνάθροισης από το αναπτυσσόμενο μενού **Επιλογή συνάρτησης**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="29b1e-122">Οι συναρτήσεις συνάθροισης περιλαμβάνουν:</span><span class="sxs-lookup"><span data-stu-id="29b1e-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="29b1e-123">**Άθροισμα**</span><span class="sxs-lookup"><span data-stu-id="29b1e-123">**Sum**</span></span>
   - <span data-ttu-id="29b1e-124">**Μέσος όρος**</span><span class="sxs-lookup"><span data-stu-id="29b1e-124">**Average**</span></span>
   - <span data-ttu-id="29b1e-125">**Μέτρηση**</span><span class="sxs-lookup"><span data-stu-id="29b1e-125">**Count**</span></span>
   - <span data-ttu-id="29b1e-126">**Πλήθος μοναδικού**</span><span class="sxs-lookup"><span data-stu-id="29b1e-126">**Count Unique**</span></span>
   - <span data-ttu-id="29b1e-127">**Μέγιστη**</span><span class="sxs-lookup"><span data-stu-id="29b1e-127">**Max**</span></span>
   - <span data-ttu-id="29b1e-128">**Ελάχιστο**</span><span class="sxs-lookup"><span data-stu-id="29b1e-128">**Min**</span></span>
   - <span data-ttu-id="29b1e-129">**First**: λαμβάνει την πρώτη τιμή της εγγραφής δεδομένων</span><span class="sxs-lookup"><span data-stu-id="29b1e-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="29b1e-130">**Last**: λαμβάνει την τελευταία τιμή που προστέθηκε στην καρτέλα δεδομένων</span><span class="sxs-lookup"><span data-stu-id="29b1e-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Τελεστές για υπολογισμούς μεγεθών.":::

1. <span data-ttu-id="29b1e-132">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να επιλέξετε τα δεδομένα που χρειάζεστε για να δημιουργήσετε αυτό το μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="29b1e-133">Επιλέξτε την καρτέλα **Χαρακτηριστικά**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="29b1e-134">Οντότητα δεδομένων: Επιλέξτε την οντότητα που περιλαμβάνει το χαρακτηριστικό που θέλετε να μετρήσετε.</span><span class="sxs-lookup"><span data-stu-id="29b1e-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="29b1e-135">Χαρακτηριστικό δεδομένων: Επιλέξτε το χαρακτηριστικό που θέλετε να χρησιμοποιήσετε στη συνάρτηση συνάθροισης για να υπολογίσετε το μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="29b1e-136">Μπορείτε να επιλέγετε μόνο ένα χαρακτηριστικό κάθε φορά.</span><span class="sxs-lookup"><span data-stu-id="29b1e-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="29b1e-137">Μπορείτε επίσης να επιλέξετε ένα χαρακτηριστικό δεδομένων από ένα υπάρχον μέγεθος επιλέγοντας την καρτέλα **μεγέθη**. Εναλλακτικά, μπορείτε να αναζητήσετε μια οντότητα ή ένα όνομα μεγέθους.</span><span class="sxs-lookup"><span data-stu-id="29b1e-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="29b1e-138">Επιλέξτε **Προσθήκη** για να προσθέσετε το επιλεγμένο χαρακτηριστικό στο μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Επιλέξτε ένα χαρακτηριστικό που θα χρησιμοποιηθεί στους υπολογισμούς.":::

1. <span data-ttu-id="29b1e-140">Για να δημιουργήσετε πιο σύνθετα μεγέθη, μπορείτε να προσθέσετε περισσότερα χαρακτηριστικά ή να χρησιμοποιήσετε μαθηματικούς τελεστές στη συνάρτηση μεγέθους.</span><span class="sxs-lookup"><span data-stu-id="29b1e-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Δημιουργήστε ένα σύνθετο μέγεθος με μαθηματικούς τελεστές.":::

1. <span data-ttu-id="29b1e-142">Για να προσθέσετε φίλτρα, επιλέξτε το **Φίλτρο** στην περιοχή ρύθμισης παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="29b1e-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="29b1e-143">Στην ενότητα **Προσθήκη χαρακτηριστικού** του τμήματος παραθύρου **Φίλτρα**, επιλέξτε το χαρακτηριστικό που θέλετε να χρησιμοποιήσετε για τη δημιουργία φίλτρων.</span><span class="sxs-lookup"><span data-stu-id="29b1e-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="29b1e-144">Ορίστε τους τελεστές φίλτρου για να ορίσετε το φίλτρο για κάθε επιλεγμένο χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="29b1e-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="29b1e-145">Επιλέξτε **Εφαρμογή** για να προσθέσετε τα φίλτρα στο μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="29b1e-146">Για να διαστάσεις, επιλέξτε το **Διάσταση** στην περιοχή ρύθμισης παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="29b1e-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="29b1e-147">Οι διαστάσεις θα εμφανίζονται ως στήλες στην οντότητα παραγωγής μεγέθους.</span><span class="sxs-lookup"><span data-stu-id="29b1e-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="29b1e-148">Επιλέξτε **Επεξεργασία διαστάσεων** για να προσθέσετε χαρακτηριστικά δεδομένων με τα οποία θέλετε να ομαδοποιήσετε τις τιμές του μεγέθους.</span><span class="sxs-lookup"><span data-stu-id="29b1e-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="29b1e-149">Για παράδειγμα, πόλη ή φύλο.</span><span class="sxs-lookup"><span data-stu-id="29b1e-149">For example, city or gender.</span></span> <span data-ttu-id="29b1e-150">Από προεπιλογή, η διάσταση *CustomerID* επιλέγεται για τη δημιουργία *μεγεθών σε επίπεδο πελάτη*.</span><span class="sxs-lookup"><span data-stu-id="29b1e-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="29b1e-151">Μπορείτε να καταργήσετε την προεπιλεγμένη διάσταση αν θέλετε να δημιουργήσετε *μεγέθη σε επίπεδο επιχείρησης*.</span><span class="sxs-lookup"><span data-stu-id="29b1e-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="29b1e-152">Επιλέξτε **Ολοκλήρωση** για να προσθέσετε τις διαστάσεις στο μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="29b1e-153">Εάν υπάρχουν πολλές διαδρομές μεταξύ της οντότητας δεδομένων που αντιστοιχίσατε και της οντότητας Πελάτη, πρέπει να επιλέξετε μία από τις [διαδρομές σχέσης οντότητας](relationships.md) που προσδιορίσατε.</span><span class="sxs-lookup"><span data-stu-id="29b1e-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="29b1e-154">Τα αποτελέσματα των μεγεθών μπορεί να διαφέρουν ανάλογα με την επιλεγμένη διαδρομή.</span><span class="sxs-lookup"><span data-stu-id="29b1e-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="29b1e-155">Επιλέξτε **Προτιμήσεις δεδομένων** και επιλέξτε τη διαδρομή οντότητας που θα πρέπει να χρησιμοποιηθεί για τον προσδιορισμό του μεγέθους σας.</span><span class="sxs-lookup"><span data-stu-id="29b1e-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="29b1e-156">Επιλέξτε **Ολοκλήρωση** για να εφαρμόσετε την επιλογή σας.</span><span class="sxs-lookup"><span data-stu-id="29b1e-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Επιλέξτε τη διαδρομή οντότητας για το μέγεθος.":::

1. <span data-ttu-id="29b1e-158">Για να προσθέσετε περισσότερους υπολογισμούς για το μέγεθος, επιλέξτε **Νέος υπολογισμός**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="29b1e-159">Μπορείτε να χρησιμοποιήσετε οντότητες μόνο στην ίδια διαδρομή οντότητας για νέους υπολογισμούς.</span><span class="sxs-lookup"><span data-stu-id="29b1e-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="29b1e-160">Οι επιπλέον υπολογισμοί θα εμφανίζονται ως νέες στήλες στην οντότητα παραγωγής μεγέθους.</span><span class="sxs-lookup"><span data-stu-id="29b1e-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="29b1e-161">Επιλέξτε **...** στον υπολογισμό σε **Διπλότυπο**, **Μετονομασία** ή **Κατάργηση** υπολογισμού από ένα μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="29b1e-162">Στην περιοχή **Προεπισκόπηση**, θα δείτε το σχήμα δεδομένων της οντότητας εξόδου μέτρησης, συμπεριλαμβανομένων φίλτρων και διαστάσεων.</span><span class="sxs-lookup"><span data-stu-id="29b1e-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="29b1e-163">Η προεπισκόπηση αντιδρά δυναμικά στις αλλαγές στη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="29b1e-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="29b1e-164">Επιλέξτε **Εκτέλεση** για να υπολογίσετε τα αποτελέσματα για το ρυθμισμένο μέγεθος.</span><span class="sxs-lookup"><span data-stu-id="29b1e-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="29b1e-165">Επιλέξτε **Αποθήκευση και κλείσιμο** εάν θέλετε να διατηρήσετε την τρέχουσα ρύθμιση παραμέτρων και εκτελέστε το μέγεθος αργότερα.</span><span class="sxs-lookup"><span data-stu-id="29b1e-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="29b1e-166">Μεταβείτε στην ενότητα **Μεγέθη** για να δείτε το μέγεθος που δημιουργήθηκε πρόσφατα στη λίστα.</span><span class="sxs-lookup"><span data-stu-id="29b1e-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="29b1e-167">Διαχείριση των μετρήσεών σας</span><span class="sxs-lookup"><span data-stu-id="29b1e-167">Manage your measures</span></span>

<span data-ttu-id="29b1e-168">Αφού [δημιουργήσετε ένα μέγεθος](#create-a-measure), θα δείτε μια λίστα μεγεθών στη σελίδα **Μεγέθη**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="29b1e-169">Θα βρείτε πληροφορίες σχετικά με τον τύπο μεγέθους, τον δημιουργό, την ημερομηνία δημιουργίας, τις συνθήκες και την κατάσταση.</span><span class="sxs-lookup"><span data-stu-id="29b1e-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="29b1e-170">Όταν επιλέγετε ένα μέγεθος από τη λίστα, μπορείτε να κάνετε προεπισκόπηση της εξόδου και να κάνετε λήψη ενός αρχείου .CSV.</span><span class="sxs-lookup"><span data-stu-id="29b1e-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="29b1e-171">Για να ανανεώσετε ταυτόχρονα όλες τις μετρήσεις σας, επιλέξτε **Ανανέωση όλων** χωρίς να επιλέξετε μια συγκεκριμένη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="29b1e-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="29b1e-172">![Ενέργειες για τη διαχείριση μεμονωμένων μετρήσεων](media/measure-actions.png "Ενέργειες για τη διαχείριση μεμονωμένων μετρήσεων")</span><span class="sxs-lookup"><span data-stu-id="29b1e-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="29b1e-173">Επιλέξτε ένα μέγεθος από τη λίστα για τις ακόλουθες επιλογές:</span><span class="sxs-lookup"><span data-stu-id="29b1e-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="29b1e-174">Επιλέξτε το όνομα της μέτρησης για να δείτε τις λεπτομέρειές της.</span><span class="sxs-lookup"><span data-stu-id="29b1e-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="29b1e-175">**Επεξεργαστείτε** τη ρύθμιση παραμέτρων της μέτρησης.</span><span class="sxs-lookup"><span data-stu-id="29b1e-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="29b1e-176">**Ανανέωση** του μεγέθους με βάση τα πιο πρόσφατα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="29b1e-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="29b1e-177">**Μετονομάστε** τη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="29b1e-177">**Rename** the measure.</span></span>
- <span data-ttu-id="29b1e-178">**Διαγράψτε** τη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="29b1e-178">**Delete** the measure.</span></span>
- <span data-ttu-id="29b1e-179">**Ενεργοποίηση** ή **Απενεργοποίηση**.</span><span class="sxs-lookup"><span data-stu-id="29b1e-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="29b1e-180">Τα ανενεργά μεγέθη δεν θα ανανεώνονται κατά τη διάρκεια μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="29b1e-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="29b1e-181">Υπάρχουν [έξι τύποι κατάστασης](system.md#status-types) για εργασίες/διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="29b1e-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="29b1e-182">Επιπλέον, οι περισσότερες διεργασίες [εξαρτώνται από άλλες διεργασίες κατάντη](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="29b1e-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="29b1e-183">Μπορείτε να επιλέξετε την κατάσταση μιας διεργασίας για να δείτε λεπτομέρειες σχετικά με την πρόοδο ολόκληρου του έργου.</span><span class="sxs-lookup"><span data-stu-id="29b1e-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="29b1e-184">Αφού επιλέξετε **Προβολή λεπτομερειών** για μία από τις εργασίες του έργου, μπορείτε να βρείτε πρόσθετες πληροφορίες: χρόνος επεξεργασίας, ημερομηνία τελευταίας επεξεργασίας και όλα τα σφάλματα και τις προειδοποιήσεις που σχετίζονται με την εργασία.</span><span class="sxs-lookup"><span data-stu-id="29b1e-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="29b1e-185">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="29b1e-185">Next step</span></span>

<span data-ttu-id="29b1e-186">Μπορείτε να χρησιμοποιήσετε τα υπάρχοντα μεγέθη για να δημιουργήσετε [ένα τμήμα πελάτη](segments.md).</span><span class="sxs-lookup"><span data-stu-id="29b1e-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]