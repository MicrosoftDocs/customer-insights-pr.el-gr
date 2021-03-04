---
title: Λήψη δεδομένων μέσω σύνδεσης Power Query
description: Συνδέσεις για προελεύσεις δεδομένων βάσει Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267769"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="d1abd-103">Σύνδεση σε προέλευση δεδομένων Power Query</span><span class="sxs-lookup"><span data-stu-id="d1abd-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="d1abd-104">Το Power Query προσφέρει ένα ευρύ σύνολο συνδέσεων για λήψη δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="d1abd-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="d1abd-105">Οι περισσότερες από αυτές τις συνδέσεις υποστηρίζονται από το Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1abd-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="d1abd-106">Η προσθήκη προελεύσεων δεδομένων με βάση τις συνδέσεις Power Query γενικά ακολουθεί τα βήματα που περιγράφονται στην επόμενη ενότητα.</span><span class="sxs-lookup"><span data-stu-id="d1abd-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="d1abd-107">Ωστόσο, ανάλογα με τη σύνδεση που χρησιμοποιείτε, απαιτούνται διαφορετικές πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="d1abd-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="d1abd-108">Για περισσότερες πληροφορίες, ανατρέξτε στην τεκμηρίωση σχετικά με μεμονωμένες συνδέσεις στην [αναφορά σύνδεσης Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="d1abd-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="d1abd-109">Δημιουργήστε μια νέα προέλευση δεδομένων</span><span class="sxs-lookup"><span data-stu-id="d1abd-109">Create a new data source</span></span>

1. <span data-ttu-id="d1abd-110">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d1abd-111">Επιλέξτε **Προσθήκη προέλευσης δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="d1abd-112">Επιλέξτε τη μέθοδο **Εισαγωγή δεδομένων** και επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="d1abd-113">Δώστε ένα **Όνομα** για την προέλευση δεδομένων και επιλέξτε **Επόμενο** για να δημιουργήσετε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="d1abd-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="d1abd-114">Οδηγίες ονομάτων:</span><span class="sxs-lookup"><span data-stu-id="d1abd-114">Name guidelines:</span></span> 
   - <span data-ttu-id="d1abd-115">Ξεκινήστε με γράμμα.</span><span class="sxs-lookup"><span data-stu-id="d1abd-115">Start with a letter.</span></span>
   - <span data-ttu-id="d1abd-116">Χρησιμοποιήστε μόνο γράμματα και αριθμούς.</span><span class="sxs-lookup"><span data-stu-id="d1abd-116">Use letters and numbers only.</span></span> <span data-ttu-id="d1abd-117">Δεν επιτρέπονται ειδικοί χαρακτήρες και διαστήματα.</span><span class="sxs-lookup"><span data-stu-id="d1abd-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="d1abd-118">Χρησιμοποιήστε μεταξύ 3 και 64 χαρακτήρων.</span><span class="sxs-lookup"><span data-stu-id="d1abd-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="d1abd-119">Επιλέξτε έναν από τους [διαθέσιμους συνδέσμους](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d1abd-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="d1abd-120">Για αυτό το παράδειγμα, επιλέγουμε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d1abd-121">Καταγράψτε τα απαιτούμενα στοιχεία στις **Ρυθμίσεις σύνδεσης** για την επιλεγμένη σύνδεση και επιλέξτε **Επόμενο** για να δείτε μια προεπισκόπηση των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="d1abd-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="d1abd-122">Επιλέξτε **Μετασχηματισμός δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-122">Select **Transform data**.</span></span> <span data-ttu-id="d1abd-123">Σε αυτό το βήμα, θα προσθέσετε οντότητες στην προέλευση δεδομένων σας.</span><span class="sxs-lookup"><span data-stu-id="d1abd-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="d1abd-124">Οι οντότητες είναι σύνολα δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="d1abd-124">Entities are datasets.</span></span> <span data-ttu-id="d1abd-125">Εάν έχετε μια βάση δεδομένων που περιλαμβάνει πολλαπλά σύνολα δεδομένων, κάθε σύνολο δεδομένων είναι οντότητα αυτού του ιδίου.</span><span class="sxs-lookup"><span data-stu-id="d1abd-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="d1abd-126">Το παράθυρο διαλόγου **Power Query - Επεξεργασία ερωτημάτων** σάς δίνει τη δυνατότητα να αναθεωρήσετε και να βελτιώσετε τα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="d1abd-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="d1abd-127">Οι οντότητες που αναγνωρίζονται από τα συστήματα στην επιλεγμένη προέλευση δεδομένων εμφανίζονται στο αριστερό τμήμα παραθύρου.</span><span class="sxs-lookup"><span data-stu-id="d1abd-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d1abd-128">![Παράθυρο διαλόγου επεξεργασίας ερωτημάτων](media/data-manager-configure-edit-queries.png "Παράθυρο διαλόγου επεξεργασίας ερωτημάτων")</span><span class="sxs-lookup"><span data-stu-id="d1abd-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="d1abd-129">Μπορείτε επίσης να μετασχηματίσετε τα δεδομένα σας.</span><span class="sxs-lookup"><span data-stu-id="d1abd-129">You can also transform your data.</span></span> <span data-ttu-id="d1abd-130">Επιλέξτε μια οντότητα για επεξεργασία ή μετατροπή.</span><span class="sxs-lookup"><span data-stu-id="d1abd-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="d1abd-131">Χρησιμοποιήστε τις επιλογές στο παράθυρο του Power Query για να εφαρμόσετε μετασχηματισμούς.</span><span class="sxs-lookup"><span data-stu-id="d1abd-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="d1abd-132">Κάθε μετασχηματισμός εμφανίζεται στην περιοχή **Εφαρμοσμένα βήματα**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="d1abd-133">Το Power Query παρέχει πολυάριθμες προ-ενσωματωμένες επιλογές μετασχηματισμού.</span><span class="sxs-lookup"><span data-stu-id="d1abd-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="d1abd-134">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Μετασχηματισμοί Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="d1abd-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="d1abd-135">Μπορείτε να προσθέσετε επιπλέον οντότητες στο προέλευση δεδομένων σας επιλέγοντας **Λήψη δεδομένων** στο παράθυρο διαλόγου **Επεξεργασία ερωτημάτων**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="d1abd-136">Αυτοί οι μετασχηματισμοί συνιστώνται ιδιαίτερα:</span><span class="sxs-lookup"><span data-stu-id="d1abd-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="d1abd-137">Εάν λαμβάνετε δεδομένα από ένα αρχείο CSV, η πρώτη γραμμή συχνά περιέχει κεφαλίδες.</span><span class="sxs-lookup"><span data-stu-id="d1abd-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="d1abd-138">Μεταβείτε στο στοιχείο **Μετασχηματισμός πίνακα** και επιλέξτε **Χρήση κεφαλίδων ως πρώτη γραμμή**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="d1abd-139">Βεβαιωθείτε ότι ο τύπος δεδομένων έχει ρυθμιστεί κατάλληλα.</span><span class="sxs-lookup"><span data-stu-id="d1abd-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="d1abd-140">Επιλέξτε **Αποθήκευση** στην κάτω δεξιά γωνία του παραθύρου Power Query για να αποθηκεύσετε τους μετασχηματισμούς.</span><span class="sxs-lookup"><span data-stu-id="d1abd-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="d1abd-141">Μετά την αποθήκευση, θα βρείτε την προέλευση δεδομένων σας στα **Δεδομένα** > **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d1abd-142">Στη σελίδα **Προελεύσεις δεδομένων**, θα παρατηρήσετε ότι η νέα προέλευση δεδομένων βρίσκεται σε κατάσταση **Ανανέωση**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="d1abd-143">Διαθέσιμες Power Query προελεύσεις δεδομένων</span><span class="sxs-lookup"><span data-stu-id="d1abd-143">Available Power Query data sources</span></span>

<span data-ttu-id="d1abd-144">Ανατρέξτε στην [Αναφορά σύνδεσης Power Query](https://docs.microsoft.com/power-query/connectors/) για μια ενημερωμένη λίστα συνδέσεων, την οποία μπορείτε να επιλέξετε για την εισαγωγή δεδομένων στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1abd-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="d1abd-145">Οι συνδέσεις με ένα σημάδι επιλογής στη στήλη **Customer Insights (Dataflows)** είναι διαθέσιμες για τη δημιουργία νέων προελεύσεων δεδομένων βάσει του Power Query.</span><span class="sxs-lookup"><span data-stu-id="d1abd-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="d1abd-146">Εξετάστε την τεκμηρίωση μιας συγκεκριμένης σύνδεσης για να μάθετε περισσότερα σχετικά με τις προϋποθέσεις, τους περιορισμούς και άλλες λεπτομέρειες.</span><span class="sxs-lookup"><span data-stu-id="d1abd-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="d1abd-147">Επεξεργασία προελεύσεων δεδομένων Power Query</span><span class="sxs-lookup"><span data-stu-id="d1abd-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="d1abd-148">Ενδεχομένως να μην είναι δυνατό να κάνετε αλλαγές σε προελεύσεις δεδομένων που χρησιμοποιούνται τη δεδομένη στιγμή σε μία από τις διεργασίες της εφαρμογής (*κατάτμηση*, *αντιστοίχιση* ή *συγχώνευση*, για παράδειγμα).</span><span class="sxs-lookup"><span data-stu-id="d1abd-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="d1abd-149">Χρησιμοποιώντας τη σελίδα **Ρυθμίσεις** μπορείτε να παρακολουθήσετε την πρόοδο κάθε μιας από τις ενεργές διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="d1abd-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="d1abd-150">Όταν μια διεργασία ολοκληρωθεί, μπορείτε να επιστρέψετε στη σελίδα **Προελεύσεις δεδομένων** και να κάνετε τις αλλαγές σας.</span><span class="sxs-lookup"><span data-stu-id="d1abd-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="d1abd-151">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="d1abd-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d1abd-152">Επιλέξτε την κατακόρυφη έλλειψη δίπλα στην προέλευση δεδομένων που θέλετε να αλλάξετε και επιλέξτε **Επεξεργασία** από το αναπτυσσόμενο μενού.</span><span class="sxs-lookup"><span data-stu-id="d1abd-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d1abd-153">![Επιλογή επεξεργασίας](media/edit-option-data-sources.png "Επιλογή επεξεργασίας")</span><span class="sxs-lookup"><span data-stu-id="d1abd-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="d1abd-154">Εφαρμόστε τις αλλαγές και τους μετασχηματισμούς σας στο παράθυρο διαλόγου **Power Query - Επεξεργασία ερωτημάτων** όπως περιγράφεται στη [Δημιουργία νέας προέλευσης δεδομένων](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="d1abd-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="d1abd-155">Επιλέξτε **Αποθήκευση** στο Power Query μετά την ολοκλήρωση της επεξεργασίας για να αποθηκεύσετε τις αλλαγές σας.</span><span class="sxs-lookup"><span data-stu-id="d1abd-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]