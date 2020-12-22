---
title: Δείγμα οδηγού πρόβλεψης απώλειας συναλλαγών
description: Χρησιμοποιήστε αυτό το δείγμα οδηγού για να δοκιμάσετε το έτοιμο μοντέλο πρόβλεψης απώλειας συναλλαγών.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643593"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="903ab-103">Δείγμα οδηγού πρόβλεψης απώλειας συναλλαγών (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="903ab-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="903ab-104">Αυτός ο οδηγός θα σας εξηγήσει ένα παράδειγμα από άκρη σε άκρη της πρόβλεψης απώλειας συναλλαγών στο Customer Insights χρησιμοποιώντας τα δεδομένα που παρέχονται παρακάτω.</span><span class="sxs-lookup"><span data-stu-id="903ab-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="903ab-105">Όλα τα δεδομένα που χρησιμοποιούνται σε αυτόν τον οδηγό δεν είναι πραγματικά δεδομένα πελάτη και είναι μέρος του συνόλου δεδομένων της Contoso που βρίσκονται στο περιβάλλον *Επίδειξη* εντός της συνδρομής σας στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="903ab-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="903ab-106">Σενάριο</span><span class="sxs-lookup"><span data-stu-id="903ab-106">Scenario</span></span>

<span data-ttu-id="903ab-107">Η Contoso είναι μια εταιρεία που παράγει υψηλής ποιότητας καφέ και καφετιέρες, τα οποία πωλούν μέσω της τοποθεσίας Web της Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="903ab-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="903ab-108">Ο στόχος τους είναι να γνωρίζουν ποιοι πελάτες που αγοράζουν συνήθως τα προϊόντα τους σε τακτική βάση, θα σταματήσουν να είναι ενεργοί πελάτες στις επόμενες 60 ημέρες.</span><span class="sxs-lookup"><span data-stu-id="903ab-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="903ab-109">Η γνώση του ποιος από τους πελάτες τους είναι **πιθανό να χαθεί**, μπορεί να τους βοηθήσει να σώσουν τις προσπάθειες μάρκετινγκ εστιάζοντας στη διατήρησή τους.</span><span class="sxs-lookup"><span data-stu-id="903ab-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="903ab-110">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="903ab-110">Prerequisites</span></span>

- <span data-ttu-id="903ab-111">Τουλάχιστον [Δικαιώματα συμμετέχοντα](permissions.md) στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="903ab-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="903ab-112">Συνιστούμε να εφαρμόσετε τα παρακάτω βήματα [σε ένα νέο περιβάλλον](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="903ab-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="903ab-113">Εργασία 1 - Λήψη δεδομένων</span><span class="sxs-lookup"><span data-stu-id="903ab-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="903ab-114">Εξετάστε τα άρθρα [σχετικά με τη λήψη δεδομένων](data-sources.md) και την [εισαγωγή προελεύσεων δεδομένων χρησιμοποιώντας συγκεκριμένα συνδέσεις Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="903ab-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="903ab-115">Οι παρακάτω πληροφορίες προϋποθέτουν ότι έχετε εξοικειωθεί με τη λήψη δεδομένων γενικά.</span><span class="sxs-lookup"><span data-stu-id="903ab-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="903ab-116">Λήψη δεδομένων πελατών από την πλατφόρμα eCommerce</span><span class="sxs-lookup"><span data-stu-id="903ab-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="903ab-117">Δημιουργήστε μια προέλευση δεδομένων με όνομα **eCommerce**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="903ab-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="903ab-118">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="903ab-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="903ab-119">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="903ab-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="903ab-120">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="903ab-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="903ab-121">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="903ab-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="903ab-122">**CreatedOn**: ημερομηνία/ώρα/ζώνη</span><span class="sxs-lookup"><span data-stu-id="903ab-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="903ab-123">![Μετατροπή DoB σε ημερομηνία](media/ecommerce-dob-date.PNG "μετασχηματισμός ημερομηνίας γέννησης σε ημερομηνία")</span><span class="sxs-lookup"><span data-stu-id="903ab-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="903ab-124">Στο πεδίο «Όνομα» στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="903ab-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="903ab-125">Αποθηκεύστε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="903ab-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="903ab-126">Λήψη δεδομένων ηλεκτρονικών αγορών</span><span class="sxs-lookup"><span data-stu-id="903ab-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="903ab-127">Προσθέστε ένα άλλο σύνολο δεδομένων στην ίδια προέλευση δεδομένων **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="903ab-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="903ab-128">Επιλέξτε ξανά τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="903ab-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="903ab-129">Εισαγάγετε τη διεύθυνση URL για δεδομένα **Ηλεκτρονικών αγορών** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="903ab-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="903ab-130">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="903ab-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="903ab-131">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="903ab-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="903ab-132">**PurchasedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="903ab-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="903ab-133">**TotalPrice**: νομισματική μονάδα</span><span class="sxs-lookup"><span data-stu-id="903ab-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="903ab-134">Στο πεδίο «Όνομα» στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="903ab-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="903ab-135">Αποθηκεύστε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="903ab-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="903ab-136">Λήψη δεδομένων πελατών από το σχήμα πίστης</span><span class="sxs-lookup"><span data-stu-id="903ab-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="903ab-137">Δημιουργήστε μια προέλευση δεδομένων με όνομα **LoyaltyScheme**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="903ab-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="903ab-138">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="903ab-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="903ab-139">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="903ab-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="903ab-140">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="903ab-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="903ab-141">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="903ab-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="903ab-142">**RewardsPoints**: ακέραιος αριθμός</span><span class="sxs-lookup"><span data-stu-id="903ab-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="903ab-143">**CreatedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="903ab-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="903ab-144">Στο πεδίο «Όνομα» στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="903ab-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="903ab-145">Αποθηκεύστε την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="903ab-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="903ab-146">Εργασία 2 - Ενοποίηση δεδομένων</span><span class="sxs-lookup"><span data-stu-id="903ab-146">Task 2 - Data unification</span></span>

<span data-ttu-id="903ab-147">Αφού ληφθούν τα δεδομένα, ξεκινάμε τώρα τη διαδικασία **Χάρτης, Αντιστοίχιση, Συγχώνευση** για να δημιουργήσουμε ένα ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="903ab-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="903ab-148">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Ενοποίηση δεδομένων](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="903ab-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="903ab-149">Αντιστ.</span><span class="sxs-lookup"><span data-stu-id="903ab-149">Map</span></span>

1. <span data-ttu-id="903ab-150">Μετά τη λήψη των δεδομένων, αντιστοιχίστε επαφές από το eCommerce και δεδομένα πίστης σε κοινούς τύπους δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="903ab-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="903ab-151">Μετάβαση στα **Δεδομένα** > **Ενοποίηση** > **Αντιστοίχιση**.</span><span class="sxs-lookup"><span data-stu-id="903ab-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="903ab-152">Επιλέξτε τις οντότητες που αντιπροσωπεύουν το προφίλ πελάτη – **eCommerceContacts** και **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="903ab-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ενοποίηση προελεύσεις δεδομένων ecommerce και πίστης.":::

1. <span data-ttu-id="903ab-154">Επιλέξτε **ContactId** ως πρωτεύον κλειδί για **eCommerceContacts** και **LoyaltyID** ως προωτεύον κλειδί για **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="903ab-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Ενοποίηση του LoyaltyId ως πρωτεύοντος κλειδιού.":::

### <a name="match"></a><span data-ttu-id="903ab-156">Αντιστοίχιση</span><span class="sxs-lookup"><span data-stu-id="903ab-156">Match</span></span>

1. <span data-ttu-id="903ab-157">Μετάβαση στην καρτέλα **Αντιστοίχιση** κι επιλέξτε **Ορισμός σειράς**.</span><span class="sxs-lookup"><span data-stu-id="903ab-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="903ab-158">Στην αναπτυσσόμενη λίστα **Κύρια**, επιλέξτε **ECommerceContacts: eCommerce** ως την κύρια προέλευση και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="903ab-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="903ab-159">Στην αναπτυσσόμενη λίστα **Οντότητα 2**, επιλέξτε **loyCustomers : LoyaltyScheme** και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="903ab-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Ενοποίηση αντιστοίχισης eCommerce και πίστης.":::

1. <span data-ttu-id="903ab-161">Επιλέξτε **Δημιουργία νέου κανόνα**</span><span class="sxs-lookup"><span data-stu-id="903ab-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="903ab-162">Προσθέστε την πρώτη σας συνθήκη χρησιμοποιώντας το ονοματεπώνυμο.</span><span class="sxs-lookup"><span data-stu-id="903ab-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="903ab-163">Για eCommerceContacts επιλέξτε **Ονοματεπώνυμο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="903ab-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="903ab-164">Για loyCustomers επιλέξτε **Ονοματεπώνυμο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="903ab-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="903ab-165">Επιλέξτε την αναπτυσσόμενη λίστα **Ομαλοποίηση** και επιλέξτε **Τύπος (τηλέφωνο, όνομα, διεύθυνση,...)**.</span><span class="sxs-lookup"><span data-stu-id="903ab-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="903ab-166">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="903ab-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="903ab-167">Εισαγάγετε το όνομα **Ονοματεπώνυμο, ηλεκτρονικό ταχυδρομείο** για τον νέο κανόνα.</span><span class="sxs-lookup"><span data-stu-id="903ab-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="903ab-168">Προσθέστε μια δεύτερη συνθήκη για τη διεύθυνση ηλεκτρονικού ταχυδρομείου επιλέγοντας **Προσθήκη συνθήκης**</span><span class="sxs-lookup"><span data-stu-id="903ab-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="903ab-169">Για την οντότητα eCommerceContacts, επιλέξτε **ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="903ab-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="903ab-170">Για την οντότητα loyCustomers, επιλέξτε **ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="903ab-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="903ab-171">Αφήστε την «Κανονικοποίηση» κενή.</span><span class="sxs-lookup"><span data-stu-id="903ab-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="903ab-172">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="903ab-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Ενοποίηση του κανόνα αντιστοίχισης για όνομα και μήνυμα ηλεκτρονικού ταχυδρομείου.":::

7. <span data-ttu-id="903ab-174">Επιλέξτε **Αποθήκευση** και **Εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="903ab-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="903ab-175">Συγχώνευση</span><span class="sxs-lookup"><span data-stu-id="903ab-175">Merge</span></span>

1. <span data-ttu-id="903ab-176">Μεταβείτε στην καρτέλα **Συγχώνευση**.</span><span class="sxs-lookup"><span data-stu-id="903ab-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="903ab-177">Στην οντότητα **ContactId** για **loyCustomers**, αλλάξτε τα εμφανιζόμενο όνομα σε **ContactIdLOYALTY** για να το διαφοροποιήσετε από τα υπόλοιπα αναγνωριστικά που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="903ab-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="μετονομάστε το contactid από αναγνωριστικό πίστης.":::

1. <span data-ttu-id="903ab-179">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να αρχίσετε τη διαδικασία συγχώνευσης.</span><span class="sxs-lookup"><span data-stu-id="903ab-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="903ab-180">Εργασία 3 - Ρύθμιση παραμέτρων πρόβλεψης απώλειας συναλλαγών</span><span class="sxs-lookup"><span data-stu-id="903ab-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="903ab-181">Με τα ενοποιημένα προφίλ πελατών στη θέση τους, τώρα μπορούμε να εκτελέσουμε την πρόβλεψη απώλειας συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="903ab-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="903ab-182">Για αναλυτικά βήματα, ανατρέξτε στο άρθρο [Πρόβλεψη απώλειας συνδρομών (προεπισκόπηση)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="903ab-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="903ab-183">Μεταβείτε στο **Ευφυΐα** > **Ανακάλυψη** και επιλέξτε για χρήση του **Μοντέλου απώλειας πελατών**.</span><span class="sxs-lookup"><span data-stu-id="903ab-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="903ab-184">Επιλέξτε την επιλογή **Συναλλαγών** και επιλέξτε **Έναρξη**.</span><span class="sxs-lookup"><span data-stu-id="903ab-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="903ab-185">Ονομάστε το μοντέλο **Πρόβλεψη απώλειας συναλλαγών OOB eCommerce** και την οντότητα εξόδου **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="903ab-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="903ab-186">Καθορίστε δύο συνθήκες για το μοντέλο απώλειας:</span><span class="sxs-lookup"><span data-stu-id="903ab-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="903ab-187">**Παράθυρο πρόβλεψης**: **τουλάχιστον 60** ημέρες.</span><span class="sxs-lookup"><span data-stu-id="903ab-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="903ab-188">Αυτή η ρύθμιση καθορίζει το βάθος στο μέλλον για το οποίο θέλουμε να προβλέπουμε την απώλεια πελατών.</span><span class="sxs-lookup"><span data-stu-id="903ab-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="903ab-189">**Ορισμός απώλειας**: **τουλάχιστον 60** ημέρες.</span><span class="sxs-lookup"><span data-stu-id="903ab-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="903ab-190">Η διάρκεια χωρίς την αγορά μετά από την οποία ένας πελάτης θεωρείται ότι χάθηκε.</span><span class="sxs-lookup"><span data-stu-id="903ab-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Επιλέξτε τους μοχλούς μοντέλου Παράθυρο πρόβλεψης και Ορισμός απώλειας.":::

1. <span data-ttu-id="903ab-192">Επιλέξτε **Ιστορικό αγορών (απαιτείται)** και επιλέξτε **Προσθήκη δεδομένων** για το ιστορικό συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="903ab-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="903ab-193">Προσθέστε την οντότητα **eCommercePurchases: eCommerce** και αντιστοιχίστε τα πεδία από το eCommerce στα αντίστοιχα πεδία που απαιτούνται από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="903ab-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="903ab-194">Συνδυάστε την οντότητα **eCommercePurchases : eCommerce** με το **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="903ab-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Συμμετοχή σε οντότητες eCommerce.":::

1. <span data-ttu-id="903ab-196">Επιλέξτε **Επόμενο** για να ορίσετε το χρονοδιάγραμμα μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="903ab-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="903ab-197">Το μοντέλο πρέπει να εκπαιδεύεται τακτικά για την εκμάθηση νέων μοτίβων όταν λαμβάνονται νέα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="903ab-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="903ab-198">Για αυτό το παράδειγμα, επιλέξτε **Μηνιαία**.</span><span class="sxs-lookup"><span data-stu-id="903ab-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="903ab-199">Αφού εξετάσετε όλες τις λεπτομέρειες, επιλέξτε **Αποθήκευση και εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="903ab-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="903ab-200">Εργασία 4 - Αναθεώρηση αποτελεσμάτων μοντέλου και επεξηγήσεις</span><span class="sxs-lookup"><span data-stu-id="903ab-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="903ab-201">Αφήστε το μοντέλο να ολοκληρώσει την εκπαίδευση και τη βαθμολόγηση των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="903ab-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="903ab-202">Μπορείτε πλέον να αναθεωρήσετε τις επεξηγήσεις των μοντέλων απώλειας συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="903ab-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="903ab-203">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Επανεξέταση μιας κατάστασης πρόβλεψης και αποτελέσματα](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="903ab-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="903ab-204">Εργασία 5 - Δημιουργία τμήματος πελατών με υψηλό κίνδυνο απώλειας</span><span class="sxs-lookup"><span data-stu-id="903ab-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="903ab-205">Η εκτέλεση του μοντέλου παραγωγής δημιουργεί μια νέα οντότητα την οποία μπορείτε να δείτε στα **Δεδομένα** > **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="903ab-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="903ab-206">Μπορείτε να δημιουργήσετε ένα νέο τμήμα με βάση την οντότητα που δημιουργήθηκε από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="903ab-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="903ab-207">Μετάβαση στα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="903ab-207">Go to **Segments**.</span></span> <span data-ttu-id="903ab-208">Επιλέξτε **Νέο** και επιλέξτε **Δημιουργία από** > **Ευφυΐα**.</span><span class="sxs-lookup"><span data-stu-id="903ab-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Δημιουργία τμήματος με την έξοδο μοντέλου.":::

1. <span data-ttu-id="903ab-210">Επιλέξτε το τελικό σημείο **OOBSubscriptionChurnPrediction** και καθορίστε το τμήμα:</span><span class="sxs-lookup"><span data-stu-id="903ab-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="903ab-211">Πεδίο: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="903ab-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="903ab-212">Τελεστής: μεγαλύτερο από</span><span class="sxs-lookup"><span data-stu-id="903ab-212">Operator: greater than</span></span>
   - <span data-ttu-id="903ab-213">Τιμή: 0,6</span><span class="sxs-lookup"><span data-stu-id="903ab-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Ρυθμίστε το τμήμα απώλειας συνδρομών.":::

<span data-ttu-id="903ab-215">Τώρα διαθέτετε ένα τμήμα που ενημερώνεται δυναμικά και προσδιορίζει τους πελάτες υψηλού κινδύνου απώλειας για αυτήν την επιχειρηματική συνδρομή.</span><span class="sxs-lookup"><span data-stu-id="903ab-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="903ab-216">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και διαχείριση τμημάτων](segments.md).</span><span class="sxs-lookup"><span data-stu-id="903ab-216">For more information, see [Create and manage segments](segments.md).</span></span>
