---
title: Δείγμα οδηγού πρόβλεψης απώλειας συνδρομών
description: Χρησιμοποιήστε αυτό το δείγμα οδηγού για να δοκιμάσετε το έτοιμο μοντέλο πρόβλεψης απώλειας συνδρομών.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306303"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="427d8-103">Δείγμα οδηγού πρόβλεψης απώλειας συνδρομών (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="427d8-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="427d8-104">Θα σας εξηγήσουμε ένα παράδειγμα από άκρη σε άκρη της πρόβλεψης απώλειας συνδρομών χρησιμοποιώντας τα δεδομένα δείγμα που παρέχονται παρακάτω.</span><span class="sxs-lookup"><span data-stu-id="427d8-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="427d8-105">Σενάριο</span><span class="sxs-lookup"><span data-stu-id="427d8-105">Scenario</span></span>

<span data-ttu-id="427d8-106">Η Contoso είναι μια εταιρεία που παράγει μηχανές καφέ και καφέ υψηλής ποιότητας, τις οποίες πουλάει μέσω της ιστοσελίδας της Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="427d8-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="427d8-107">Πρόσφατα, άρχισαν μια επιχειρηματική συνδρομή για τους πελάτες τους, για να παίρνουν τακτικά τον καφέ τους.</span><span class="sxs-lookup"><span data-stu-id="427d8-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="427d8-108">Σκοπός τους είναι η κατανόηση ποιοι εγγεγραμμένοι πελάτες ενδέχεται να ακυρώσουν τη συνδρομή τους στους επόμενους μήνες.</span><span class="sxs-lookup"><span data-stu-id="427d8-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="427d8-109">Η γνώση του ποιος από τους πελάτες τους είναι **πιθανό να χαθεί**, μπορεί να τους βοηθήσει να σώσουν τις προσπάθειες μάρκετινγκ εστιάζοντας στη διατήρησή τους.</span><span class="sxs-lookup"><span data-stu-id="427d8-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="427d8-110">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="427d8-110">Prerequisites</span></span>

- <span data-ttu-id="427d8-111">Τουλάχιστον [Δικαιώματα συμμετέχοντα](permissions.md) στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="427d8-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="427d8-112">Συνιστούμε να εφαρμόσετε τα παρακάτω βήματα [σε ένα νέο περιβάλλον](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="427d8-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="427d8-113">Εργασία 1 - Λήψη δεδομένων</span><span class="sxs-lookup"><span data-stu-id="427d8-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="427d8-114">Εξετάστε τα άρθρα [σχετικά με τη λήψη δεδομένων](data-sources.md) και την [εισαγωγή προελεύσεων δεδομένων χρησιμοποιώντας συγκεκριμένα συνδέσεις Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="427d8-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="427d8-115">Οι παρακάτω πληροφορίες προϋποθέτουν ότι έχετε εξοικειωθεί με τη λήψη δεδομένων γενικά.</span><span class="sxs-lookup"><span data-stu-id="427d8-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="427d8-116">Λήψη δεδομένων πελατών από την πλατφόρμα eCommerce</span><span class="sxs-lookup"><span data-stu-id="427d8-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="427d8-117">Δημιουργήστε μια προέλευση δεδομένων με όνομα **eCommerce**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="427d8-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="427d8-118">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="427d8-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="427d8-119">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="427d8-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="427d8-120">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="427d8-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="427d8-121">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="427d8-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="427d8-122">**CreatedOn**: ημερομηνία/ώρα/ζώνη</span><span class="sxs-lookup"><span data-stu-id="427d8-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Μετασχηματισμός ημερομηνίας γέννησης σε ημερομηνία.":::

1. <span data-ttu-id="427d8-124">Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="427d8-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="427d8-125">Αποθηκεύστε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="427d8-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="427d8-126">Λήψη δεδομένων πελατών από το σχήμα πίστης</span><span class="sxs-lookup"><span data-stu-id="427d8-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="427d8-127">Δημιουργήστε μια προέλευση δεδομένων με όνομα **LoyaltyScheme**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="427d8-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="427d8-128">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="427d8-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="427d8-129">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="427d8-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="427d8-130">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="427d8-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="427d8-131">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="427d8-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="427d8-132">**RewardsPoints**: ακέραιος αριθμός</span><span class="sxs-lookup"><span data-stu-id="427d8-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="427d8-133">**CreatedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="427d8-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="427d8-134">Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="427d8-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="427d8-135">Αποθηκεύστε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="427d8-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="427d8-136">Λήψη πληροφοριών συνδρομών</span><span class="sxs-lookup"><span data-stu-id="427d8-136">Ingest subscription information</span></span>

1. <span data-ttu-id="427d8-137">Δημιουργήστε μια προέλευση δεδομένων με όνομα **SubscriptionHistory**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="427d8-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="427d8-138">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="427d8-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="427d8-139">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="427d8-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="427d8-140">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="427d8-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="427d8-141">**SubscriptioID**: ακέραιος αριθμός</span><span class="sxs-lookup"><span data-stu-id="427d8-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="427d8-142">**SubscriptionAmount**: νομισματική μονάδα</span><span class="sxs-lookup"><span data-stu-id="427d8-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="427d8-143">**SubscriptionEndDate**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="427d8-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="427d8-144">**SubscriptionStartDate**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="427d8-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="427d8-145">**TransactionDate**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="427d8-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="427d8-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="427d8-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="427d8-147">**Is_auto_renew**: True/False</span><span class="sxs-lookup"><span data-stu-id="427d8-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="427d8-148">**RecurringFrequencyInMonths**: ακέριος αριθμός</span><span class="sxs-lookup"><span data-stu-id="427d8-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="427d8-149">Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="427d8-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="427d8-150">Αποθηκεύστε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="427d8-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="427d8-151">Λήψη δεδομένων πελατών από κριτικές ιστότοπων</span><span class="sxs-lookup"><span data-stu-id="427d8-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="427d8-152">Δημιουργήστε μια προέλευση δεδομένων με όνομα **Τοποθεσία web**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="427d8-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="427d8-153">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="427d8-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="427d8-154">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="427d8-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="427d8-155">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="427d8-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="427d8-156">**ReviewRating**: ακέραιος αριθμός</span><span class="sxs-lookup"><span data-stu-id="427d8-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="427d8-157">**ReviewDate**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="427d8-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="427d8-158">Στο πεδίο «Όνομα» στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="427d8-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="427d8-159">Εργασία 2 - Ενοποίηση δεδομένων</span><span class="sxs-lookup"><span data-stu-id="427d8-159">Task 2 - Data unification</span></span>

<span data-ttu-id="427d8-160">Αφού ληφθούν τα δεδομένα, ξεκινάμε τώρα τη διαδικασία **Χάρτης, Αντιστοίχιση, Συγχώνευση** για να δημιουργήσουμε ένα ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="427d8-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="427d8-161">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Ενοποίηση δεδομένων](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="427d8-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="427d8-162">Αντιστ.</span><span class="sxs-lookup"><span data-stu-id="427d8-162">Map</span></span>

1. <span data-ttu-id="427d8-163">Μετά τη λήψη των δεδομένων, αντιστοιχίστε επαφές από το eCommerce και δεδομένα πίστης σε κοινούς τύπους δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="427d8-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="427d8-164">Μετάβαση στα **Δεδομένα** > **Ενοποίηση** > **Αντιστοίχιση**.</span><span class="sxs-lookup"><span data-stu-id="427d8-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="427d8-165">Επιλέξτε τις οντότητες που αντιπροσωπεύουν το προφίλ πελάτη – **eCommerceContacts** και **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="427d8-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ενοποίηση προελεύσεις δεδομένων ecommerce και πίστης.":::

1. <span data-ttu-id="427d8-167">Επιλέξτε **ContactId** ως πρωτεύον κλειδί για **eCommerceContacts** και **LoyaltyID** ως προωτεύον κλειδί για **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="427d8-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Ενοποίηση του LoyaltyId ως πρωτεύοντος κλειδιού.":::

### <a name="match"></a><span data-ttu-id="427d8-169">Αντιστοίχιση</span><span class="sxs-lookup"><span data-stu-id="427d8-169">Match</span></span>

1. <span data-ttu-id="427d8-170">Μετάβαση στην καρτέλα **Αντιστοίχιση** κι επιλέξτε **Ορισμός σειράς**.</span><span class="sxs-lookup"><span data-stu-id="427d8-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="427d8-171">Στην αναπτυσσόμενη λίστα **Κύρια**, επιλέξτε **eCommerceContacts : eCommerce** ως κύρια προέλευσης και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="427d8-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="427d8-172">Στην αναπτυσσόμενη λίστα **Οντότητα 2**, επιλέξτε **loyCustomers : LoyaltyScheme** και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="427d8-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Ενοποίηση αντιστοίχισης eCommerce και πίστης.":::

1. <span data-ttu-id="427d8-174">Επιλέξτε **Δημιουργία νέου κανόνα**</span><span class="sxs-lookup"><span data-stu-id="427d8-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="427d8-175">Προσθέστε την πρώτη σας συνθήκη χρησιμοποιώντας το ονοματεπώνυμο.</span><span class="sxs-lookup"><span data-stu-id="427d8-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="427d8-176">Για το eCommerceContacts, επιλέξτε **FullName** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="427d8-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="427d8-177">Για το loyCustomers, επιλέξτε **FullName** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="427d8-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="427d8-178">Επιλέξτε την αναπτυσσόμενη λίστα **Ομαλοποίηση** και επιλέξτε **Τύπος (τηλέφωνο, όνομα, διεύθυνση,...)**.</span><span class="sxs-lookup"><span data-stu-id="427d8-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="427d8-179">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="427d8-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="427d8-180">Εισαγάγετε το όνομα **Ονοματεπώνυμο, ηλεκτρονικό ταχυδρομείο** για τον νέο κανόνα.</span><span class="sxs-lookup"><span data-stu-id="427d8-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="427d8-181">Προσθέστε μια δεύτερη συνθήκη για τη διεύθυνση ηλεκτρονικού ταχυδρομείου επιλέγοντας **Προσθήκη συνθήκης**</span><span class="sxs-lookup"><span data-stu-id="427d8-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="427d8-182">Για το eCommerceContacts της οντότητας, επιλέξτε **Ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="427d8-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="427d8-183">Για το loyCustomers της οντότητας, επιλέξτε **Ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="427d8-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="427d8-184">Αφήστε την «Κανονικοποίηση» κενή.</span><span class="sxs-lookup"><span data-stu-id="427d8-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="427d8-185">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="427d8-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Ενοποίηση του κανόνα αντιστοίχισης για όνομα και μήνυμα ηλεκτρονικού ταχυδρομείου.":::

7. <span data-ttu-id="427d8-187">Επιλέξτε **Αποθήκευση** και **Εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="427d8-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="427d8-188">Συγχώνευση</span><span class="sxs-lookup"><span data-stu-id="427d8-188">Merge</span></span>

1. <span data-ttu-id="427d8-189">Μεταβείτε στην καρτέλα **Συγχώνευση**.</span><span class="sxs-lookup"><span data-stu-id="427d8-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="427d8-190">Στην οντότητα **ContactId** για **loyCustomers**, αλλάξτε τα εμφανιζόμενο όνομα σε **ContactIdLOYALTY** για να το διαφοροποιήσετε από τα υπόλοιπα αναγνωριστικά που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="427d8-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="μετονομάστε το contactid από αναγνωριστικό πίστης.":::

1. <span data-ttu-id="427d8-192">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να αρχίσετε τη διαδικασία συγχώνευσης.</span><span class="sxs-lookup"><span data-stu-id="427d8-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="427d8-193">Εργασία 3 - Ρύθμιση παραμέτρων της πρόβλεψης απώλειας συνδρομών</span><span class="sxs-lookup"><span data-stu-id="427d8-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="427d8-194">Με τα ενοποιημένα προφίλ πελατών στη θέση τους, τώρα μπορούμε να εκτελέσουμε την πρόβλεψη απώλειας συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="427d8-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="427d8-195">Για αναλυτικά βήματα, ανατρέξτε στο άρθρο [Πρόβλεψη απώλειας συνδρομών (προεπισκόπηση)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="427d8-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="427d8-196">Μεταβείτε στο **Ευφυΐα** > **Ανακάλυψη** και επιλέξτε για χρήση του **Μοντέλου απώλειας πελατών**.</span><span class="sxs-lookup"><span data-stu-id="427d8-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="427d8-197">Επιλέξτε την επιλογή **Συνδρομή** και επιλέξτε **Έναρξη**.</span><span class="sxs-lookup"><span data-stu-id="427d8-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="427d8-198">Ονομάστε το μοντέλο **Πρόβλεψη απώλειας συνδρομών OOB** και την οντότητα εξόδου **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="427d8-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="427d8-199">Καθορίστε δύο συνθήκες για το μοντέλο απώλειας:</span><span class="sxs-lookup"><span data-stu-id="427d8-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="427d8-200">**Ημέρες από τη λήξη της συνδρομής**: **τουλάχιστον 60** ημέρες.</span><span class="sxs-lookup"><span data-stu-id="427d8-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="427d8-201">Εάν ένας πελάτης δεν ανανεώσει τη συνδρομή του σε αυτό το χρονικό διάστημα μετά τη λήξη της συνδρομής του, τότε θεωρείται χαμένος.</span><span class="sxs-lookup"><span data-stu-id="427d8-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="427d8-202">**Ορισμός απώλειας**: **τουλάχιστον 93** ημέρες.</span><span class="sxs-lookup"><span data-stu-id="427d8-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="427d8-203">Η διάρκεια που το μοντέλο προβλέπει ποιοι πελάτες ενδέχεται να χαθούν.</span><span class="sxs-lookup"><span data-stu-id="427d8-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="427d8-204">Όσο πιο μακριά στο μέλλον κοιτάξετε, τόσο λιγότερο ακριβή είναι τα αποτελέσματα.</span><span class="sxs-lookup"><span data-stu-id="427d8-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Επιλέξτε τους μοχλούς μοντέλου Παράθυρο πρόβλεψης και Ορισμός απώλειας.":::

1. <span data-ttu-id="427d8-206">Επιλέξτε **Προσθήκη απαιτούμενων δεδομένων** και επιλέξτε **Προσθήκη δεδομένων** για το ιστορικό συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="427d8-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="427d8-207">Προσθέστε την οντότητα **Συνδρομή: SubscriptionHistory** και αντιστοιχίστε τα πεδία από το eCommerce στα αντίστοιχα πεδία που απαιτούνται από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="427d8-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="427d8-208">Συμμετάσχετε στην οντότητα **Συνδρομή: SubscriptionHistory** με **eCommerceContacts : eCommerce**, ονομάστε τη σχέση **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="427d8-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Συμμετοχή σε οντότητες eCommerce.":::

1. <span data-ttu-id="427d8-210">Στις Δραστηριότηες πελατών, προσθέσετε την οντότητα **webReviews : Τοποθεσία Web** και αντιστοιχίστε τα πεδία από το webReviews στα αντίστοιχα πεδία που απαιτούνται από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="427d8-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="427d8-211">Πρωτεύον κλειδί: ReviewId</span><span class="sxs-lookup"><span data-stu-id="427d8-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="427d8-212">Χρονική σήμανση: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="427d8-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="427d8-213">Συμβάν: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="427d8-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="427d8-214">Ρύθμιση παραμέτρων μιας δραστηριότητας για κριτικές τοποθεσίας Web.</span><span class="sxs-lookup"><span data-stu-id="427d8-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="427d8-215">Επιλέξτε τη δραστηριότητα **Κριτική** και συμμετάσχετε στην οντότητα **webReviews** με **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="427d8-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="427d8-216">Επιλέξτε **Επόμενο** για να ορίσετε το χρονοδιάγραμμα μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="427d8-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="427d8-217">Το μοντέλο πρέπει να εκπαιδεύεται τακτικά για την εκμάθηση νέων μοτίβων όταν λαμβάνονται νέα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="427d8-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="427d8-218">Για αυτό το παράδειγμα, επιλέξτε **Μηνιαία**.</span><span class="sxs-lookup"><span data-stu-id="427d8-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="427d8-219">Αφού εξετάσετε όλες τις λεπτομέρειες, επιλέξτε **Αποθήκευση και εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="427d8-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="427d8-220">Εργασία 4 - Αναθεώρηση αποτελεσμάτων μοντέλου και επεξηγήσεις</span><span class="sxs-lookup"><span data-stu-id="427d8-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="427d8-221">Αφήστε το μοντέλο να ολοκληρώσει την εκπαίδευση και τη βαθμολόγηση των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="427d8-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="427d8-222">Μπορείτε πλέον να αναθεωρήσετε τις επεξηγήσεις των μοντέλων απώλειας συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="427d8-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="427d8-223">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Επανεξέταση μιας κατάστασης πρόβλεψης και αποτελέσματα](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="427d8-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="427d8-224">Εργασία 5 - Δημιουργία τμήματος πελατών με υψηλό κίνδυνο απώλειας</span><span class="sxs-lookup"><span data-stu-id="427d8-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="427d8-225">Η εκτέλεση του μοντέλου παραγωγής δημιουργεί μια νέα οντότητα την οποία μπορείτε να δείτε στα **Δεδομένα** > **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="427d8-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="427d8-226">Μπορείτε να δημιουργήσετε ένα νέο τμήμα με βάση την οντότητα που δημιουργήθηκε από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="427d8-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="427d8-227">Μετάβαση στα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="427d8-227">Go to **Segments**.</span></span> <span data-ttu-id="427d8-228">Επιλέξτε **Νέο** και επιλέξτε **Δημιουργία από** > **Ευφυΐα**.</span><span class="sxs-lookup"><span data-stu-id="427d8-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Δημιουργία τμήματος με την έξοδο μοντέλου.":::

1. <span data-ttu-id="427d8-230">Επιλέξτε το τελικό σημείο **OOBSubscriptionChurnPrediction** και καθορίστε το τμήμα:</span><span class="sxs-lookup"><span data-stu-id="427d8-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="427d8-231">Πεδίο: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="427d8-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="427d8-232">Τελεστής: μεγαλύτερο από</span><span class="sxs-lookup"><span data-stu-id="427d8-232">Operator: greater than</span></span>
   - <span data-ttu-id="427d8-233">Τιμή: 0,6</span><span class="sxs-lookup"><span data-stu-id="427d8-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Ρυθμίστε το τμήμα απώλειας συνδρομών.":::

<span data-ttu-id="427d8-235">Τώρα διαθέτετε ένα τμήμα που ενημερώνεται δυναμικά και προσδιορίζει τους πελάτες υψηλού κινδύνου απώλειας για αυτήν την επιχειρηματική συνδρομή.</span><span class="sxs-lookup"><span data-stu-id="427d8-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="427d8-236">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και διαχείριση τμημάτων](segments.md).</span><span class="sxs-lookup"><span data-stu-id="427d8-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]