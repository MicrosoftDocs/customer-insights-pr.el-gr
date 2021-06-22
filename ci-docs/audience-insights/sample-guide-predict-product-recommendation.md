---
title: Δείγμα οδηγού για πρόβλεψη προτάσεων προϊόντων
description: Χρησιμοποιήστε αυτό το δείγμα οδηγού για να δοκιμάσετε το έτοιμο μοντέλο πρόβλεψης προτάσεων προϊόντων.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129899"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="0591c-103">Δείγμα οδηγού πρόβλεψης προτάσεων προϊόντων (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="0591c-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="0591c-104">Θα σας εξηγήσουμε ένα παράδειγμα από άκρη σε άκρη της πρόβλεψης πρότασης προϊόντων χρησιμοποιώντας το δείγμα δεδομένων που παρέχεται παρακάτω.</span><span class="sxs-lookup"><span data-stu-id="0591c-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="0591c-105">Σενάριο</span><span class="sxs-lookup"><span data-stu-id="0591c-105">Scenario</span></span>

<span data-ttu-id="0591c-106">Η Contoso είναι μια εταιρεία που παράγει μηχανές καφέ και καφέ υψηλής ποιότητας, τις οποίες πουλάει μέσω της ιστοσελίδας της Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="0591c-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="0591c-107">Ο στόχος τους είναι να κατανοήσετε ποια προϊόντα θα πρέπει να συνιστούν στους περιοδικούς πελάτες τους.</span><span class="sxs-lookup"><span data-stu-id="0591c-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="0591c-108">Γνωρίζοντας τι είναι **πιθανότερο να αγοράσουν οι πελάτες**, μπορείτε να τους βοηθήσετε να κάνουν λιγότερες προσπάθειες μάρκετινγκ, εστιάζοντας σε συγκεκριμένα στοιχεία.</span><span class="sxs-lookup"><span data-stu-id="0591c-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0591c-109">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="0591c-109">Prerequisites</span></span>

- <span data-ttu-id="0591c-110">Τουλάχιστον [Δικαιώματα συμμετέχοντα](permissions.md) στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0591c-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="0591c-111">Συνιστούμε να εφαρμόσετε τα παρακάτω βήματα [σε ένα νέο περιβάλλον](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="0591c-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="0591c-112">Εργασία 1 - Λήψη δεδομένων</span><span class="sxs-lookup"><span data-stu-id="0591c-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="0591c-113">Εξετάστε τα άρθρα [σχετικά με τη λήψη δεδομένων](data-sources.md) και την [εισαγωγή προελεύσεων δεδομένων χρησιμοποιώντας συγκεκριμένα συνδέσεις Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0591c-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="0591c-114">Οι παρακάτω πληροφορίες προϋποθέτουν ότι έχετε εξοικειωθεί με τη λήψη δεδομένων γενικά.</span><span class="sxs-lookup"><span data-stu-id="0591c-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="0591c-115">Λήψη δεδομένων πελατών από την πλατφόρμα eCommerce</span><span class="sxs-lookup"><span data-stu-id="0591c-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="0591c-116">Δημιουργήστε μια προέλευση δεδομένων με όνομα **eCommerce**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0591c-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0591c-117">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="0591c-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="0591c-118">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="0591c-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0591c-119">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="0591c-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="0591c-120">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="0591c-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="0591c-121">**CreatedOn**: ημερομηνία/ώρα/ζώνη</span><span class="sxs-lookup"><span data-stu-id="0591c-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Μετασχηματισμός ημερομηνίας γέννησης σε ημερομηνία.":::

5. <span data-ttu-id="0591c-123">Στο πεδίο «Όνομα» στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="0591c-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="0591c-124">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0591c-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="0591c-125">Λήψη δεδομένων ηλεκτρονικών αγορών</span><span class="sxs-lookup"><span data-stu-id="0591c-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="0591c-126">Προσθέστε ένα άλλο σύνολο δεδομένων στην ίδια προέλευση δεδομένων **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="0591c-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="0591c-127">Επιλέξτε ξανά τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0591c-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="0591c-128">Εισαγάγετε τη διεύθυνση URL για δεδομένα **Ηλεκτρονικών αγορών** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="0591c-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="0591c-129">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="0591c-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0591c-130">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="0591c-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="0591c-131">**PurchasedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="0591c-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="0591c-132">**TotalPrice**: νομισματική μονάδα</span><span class="sxs-lookup"><span data-stu-id="0591c-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="0591c-133">Στο πεδίο **Όνομα** στο πλευρικό τμήμα παραθύρου, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="0591c-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="0591c-134">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0591c-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="0591c-135">Λήψη δεδομένων πελατών από το σχήμα πίστης</span><span class="sxs-lookup"><span data-stu-id="0591c-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="0591c-136">Δημιουργήστε μια προέλευση δεδομένων με όνομα **LoyaltyScheme**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0591c-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0591c-137">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="0591c-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="0591c-138">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="0591c-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0591c-139">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="0591c-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="0591c-140">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="0591c-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="0591c-141">**RewardsPoints**: ακέραιος αριθμός</span><span class="sxs-lookup"><span data-stu-id="0591c-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="0591c-142">**CreatedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="0591c-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="0591c-143">Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0591c-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="0591c-144">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0591c-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="0591c-145">Εργασία 2 - Ενοποίηση δεδομένων</span><span class="sxs-lookup"><span data-stu-id="0591c-145">Task 2 - Data unification</span></span>

<span data-ttu-id="0591c-146">Μετά την ενσωμάτωση των δεδομένων, αρχίζει η διαδικασία επεξεργασίας ενοποίησης δεδομένων για τη δημιουργία ενός ενοποιημένου προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="0591c-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="0591c-147">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Ενοποίηση δεδομένων](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="0591c-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="0591c-148">Αντιστ.</span><span class="sxs-lookup"><span data-stu-id="0591c-148">Map</span></span>

1. <span data-ttu-id="0591c-149">Μετά τη λήψη των δεδομένων, αντιστοιχίστε επαφές από το eCommerce και δεδομένα πίστης σε κοινούς τύπους δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0591c-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="0591c-150">Μετάβαση στα **Δεδομένα** > **Ενοποίηση** > **Αντιστοίχιση**.</span><span class="sxs-lookup"><span data-stu-id="0591c-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="0591c-151">Επιλέξτε τις οντότητες που αντιπροσωπεύουν το προφίλ πελάτη – **eCommerceContacts** και **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0591c-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ενοποίηση προελεύσεις δεδομένων ecommerce και πίστης.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="0591c-153">Επιλέξτε **ContactId** ως πρωτεύον κλειδί για **eCommerceContacts** και **LoyaltyID** ως προωτεύον κλειδί για **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0591c-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Ενοποίηση του LoyaltyId ως πρωτεύοντος κλειδιού.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="0591c-155">Αντιστοίχιση</span><span class="sxs-lookup"><span data-stu-id="0591c-155">Match</span></span>

1. <span data-ttu-id="0591c-156">Μετάβαση στην καρτέλα **Αντιστοίχιση** κι επιλέξτε **Ορισμός σειράς**.</span><span class="sxs-lookup"><span data-stu-id="0591c-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="0591c-157">Στην αναπτυσσόμενη λίστα **Κύρια**, επιλέξτε **ECommerceContacts: eCommerce** ως την κύρια προέλευση και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="0591c-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="0591c-158">Στην αναπτυσσόμενη λίστα **Οντότητα 2**, επιλέξτε **loyCustomers : LoyaltyScheme** και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="0591c-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Ενοποίηση αντιστοίχισης eCommerce και πίστης.](media/unify-match-order.png)

4. <span data-ttu-id="0591c-160">Επιλέξτε **Δημιουργία νέου κανόνα**</span><span class="sxs-lookup"><span data-stu-id="0591c-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="0591c-161">Προσθέστε την πρώτη σας συνθήκη χρησιμοποιώντας το ονοματεπώνυμο.</span><span class="sxs-lookup"><span data-stu-id="0591c-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="0591c-162">Για eCommerceContacts επιλέξτε **Ονοματεπώνυμο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="0591c-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="0591c-163">Για loyCustomers επιλέξτε **Ονοματεπώνυμο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="0591c-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="0591c-164">Επιλέξτε την αναπτυσσόμενη λίστα **Ομαλοποίηση** και επιλέξτε **Τύπος (τηλέφωνο, όνομα, διεύθυνση,...)**.</span><span class="sxs-lookup"><span data-stu-id="0591c-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="0591c-165">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="0591c-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="0591c-166">Εισαγάγετε το όνομα **Ονοματεπώνυμο, ηλεκτρονικό ταχυδρομείο** για τον νέο κανόνα.</span><span class="sxs-lookup"><span data-stu-id="0591c-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="0591c-167">Προσθέστε μια δεύτερη συνθήκη για τη διεύθυνση ηλεκτρονικού ταχυδρομείου επιλέγοντας **Προσθήκη συνθήκης**</span><span class="sxs-lookup"><span data-stu-id="0591c-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="0591c-168">Για την οντότητα eCommerceContacts, επιλέξτε **ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="0591c-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="0591c-169">Για την οντότητα loyCustomers, επιλέξτε **ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="0591c-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="0591c-170">Αφήστε την «Κανονικοποίηση» κενή.</span><span class="sxs-lookup"><span data-stu-id="0591c-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="0591c-171">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="0591c-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Ενοποίηση του κανόνα αντιστοίχισης για όνομα και μήνυμα ηλεκτρονικού ταχυδρομείου.](media/unify-match-rule.png)

7. <span data-ttu-id="0591c-173">Επιλέξτε **Αποθήκευση** και **Εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="0591c-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="0591c-174">Συγχώνευση</span><span class="sxs-lookup"><span data-stu-id="0591c-174">Merge</span></span>

1. <span data-ttu-id="0591c-175">Μεταβείτε στην καρτέλα **Συγχώνευση**.</span><span class="sxs-lookup"><span data-stu-id="0591c-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="0591c-176">Στην οντότητα **ContactId** για **loyCustomers**, αλλάξτε τα εμφανιζόμενο όνομα σε **ContactIdLOYALTY** για να το διαφοροποιήσετε από τα υπόλοιπα αναγνωριστικά που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="0591c-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![μετονομάστε το contactid από αναγνωριστικό πίστης.](media/unify-merge-contactid.png)

1. <span data-ttu-id="0591c-178">Επιλέξτε **Αποθήκευση** και **Εκτέλεση** για να αρχίσετε τη διαδικασία συγχώνευσης.</span><span class="sxs-lookup"><span data-stu-id="0591c-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="0591c-179">Εργασία 3 - Ρύθμιση παραμέτρων πρόβλεψης σύστασης προϊόντων</span><span class="sxs-lookup"><span data-stu-id="0591c-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="0591c-180">Με τα ενοποιημένα προφίλ πελατών στη θέση τους, τώρα μπορούμε να εκτελέσουμε την πρόβλεψη απώλειας συνδρομών.</span><span class="sxs-lookup"><span data-stu-id="0591c-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="0591c-181">Μεταβείτε στην επιλογή **Ευφυία** > **Πρόβλεψη** και επιλέξτε **Πρόταση προϊόντος**.</span><span class="sxs-lookup"><span data-stu-id="0591c-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="0591c-182">Επιλέξτε **Γρήγορα αποτελέσματα**.</span><span class="sxs-lookup"><span data-stu-id="0591c-182">Select **Get started**.</span></span>

1. <span data-ttu-id="0591c-183">Ονομάστε το μοντέλο **Πρόβλεψη μοντέλου συστάσεων προϊόντος OOB** και την οντότητα εξόδου **OOBProductRecommendationModelPreproduction**.</span><span class="sxs-lookup"><span data-stu-id="0591c-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="0591c-184">Καθορίστε τρεις συνθήκες για το μοντέλο:</span><span class="sxs-lookup"><span data-stu-id="0591c-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="0591c-185">**Αριθμός προϊόντων**: Ορίστε αυτήν την τιμή σε **5**.</span><span class="sxs-lookup"><span data-stu-id="0591c-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="0591c-186">Αυτή η ρύθμιση καθορίζει πόσα προϊόντα θέλετε να προτείνετε στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="0591c-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="0591c-187">**Αναμενόμενες επαναλαμβανόμενες αγορές**: Επιλέξτε **Ναι** για να δηλώσετε ότι θέλετε να συμπεριλάβετε προϊόντα στη σύσταση που έχουν αγοράσει προηγουμένως οι πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="0591c-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="0591c-188">**Παράθυρο Πίσω:** Επιλέξτε τουλάχιστον **365 ημέρες**.</span><span class="sxs-lookup"><span data-stu-id="0591c-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="0591c-189">Αυτή η ρύθμιση καθορίζει πόσο μακριά στο παρελθόν θα κοιτά το μοντέλο στη δραστηριότητα πελάτη για να χρησιμοποιηθεί ως εισροή στις προτάσεις τους.</span><span class="sxs-lookup"><span data-stu-id="0591c-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Προτιμήσεις μοντέλου για το μοντέλο πρότασης προϊόντος.":::

1. <span data-ttu-id="0591c-191">Επιλέξτε **Απαιτούμενα δεδομένα** και επιλέξτε **Προσθήκη δεδομένων** για το ιστορικό αγορών.</span><span class="sxs-lookup"><span data-stu-id="0591c-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="0591c-192">Προσθέστε την οντότητα **eCommercePurchases: eCommerce** και αντιστοιχίστε τα πεδία από το eCommerce στα αντίστοιχα πεδία που απαιτούνται από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="0591c-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="0591c-193">Συνδυάστε την οντότητα **eCommercePurchases : eCommerce** με το **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="0591c-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Συμμετοχή σε οντότητες eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="0591c-195">Επιλέξτε **Επόμενο** για να ορίσετε το χρονοδιάγραμμα μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="0591c-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="0591c-196">Το μοντέλο πρέπει να εκπαιδεύεται τακτικά για την εκμάθηση νέων μοτίβων όταν λαμβάνονται νέα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="0591c-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="0591c-197">Για αυτό το παράδειγμα, επιλέξτε **Μηνιαία**.</span><span class="sxs-lookup"><span data-stu-id="0591c-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="0591c-198">Αφού εξετάσετε όλες τις λεπτομέρειες, επιλέξτε **Αποθήκευση και εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="0591c-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="0591c-199">Εργασία 4 - Αναθεώρηση αποτελεσμάτων μοντέλου και επεξηγήσεις</span><span class="sxs-lookup"><span data-stu-id="0591c-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="0591c-200">Αφήστε το μοντέλο να ολοκληρώσει την εκπαίδευση και τη βαθμολόγηση των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0591c-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="0591c-201">Μπορείτε πλέον να αναθεωρήσετε τις επεξηγήσεις των μοντέλων προτάσεων προϊόντων.</span><span class="sxs-lookup"><span data-stu-id="0591c-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="0591c-202">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Επανεξέταση μιας κατάστασης πρόβλεψης και αποτελέσματα](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="0591c-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="0591c-203">Εργασία 5 - Δημιουργία τμήματος αγοράς με προϊόντα με πολλές αγορές</span><span class="sxs-lookup"><span data-stu-id="0591c-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="0591c-204">Η εκτέλεση του μοντέλου παραγωγής δημιουργεί μια νέα οντότητα την οποία μπορείτε να δείτε στα **Δεδομένα** > **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="0591c-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="0591c-205">Μπορείτε να δημιουργήσετε ένα νέο τμήμα με βάση την οντότητα που δημιουργήθηκε από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="0591c-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="0591c-206">Μετάβαση στα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="0591c-206">Go to **Segments**.</span></span> <span data-ttu-id="0591c-207">Επιλέξτε **Νέο** και επιλέξτε **Δημιουργία από** > **Ευφυΐα**.</span><span class="sxs-lookup"><span data-stu-id="0591c-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Δημιουργία τμήματος με την έξοδο μοντέλου.](media/segment-intelligence.png)

1. <span data-ttu-id="0591c-209">Επιλέξτε το τελικό σημείο **OOBProductRecommendationModelPrediction** και καθορίστε το τμήμα:</span><span class="sxs-lookup"><span data-stu-id="0591c-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="0591c-210">Πεδίο: ProductID</span><span class="sxs-lookup"><span data-stu-id="0591c-210">Field: ProductID</span></span>
   - <span data-ttu-id="0591c-211">Τελεστής: Τιμή</span><span class="sxs-lookup"><span data-stu-id="0591c-211">Operator: Value</span></span>
   - <span data-ttu-id="0591c-212">Αξία: Επιλογή των τριών κορυφαίων αναγνωριστικών προϊόντων</span><span class="sxs-lookup"><span data-stu-id="0591c-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Δημιουργία τμήματος από τα αποτελέσματα του μοντέλου.":::

<span data-ttu-id="0591c-214">Έχετε τώρα ένα τμήμα της αγοράς που ενημερώνεται δυναμικά και το οποίο προσδιορίζει τους πελάτες που είναι περισσότερο πρόθυμοι να αγοράσουν τα τρία πιο συνιστώμενα προϊόντα</span><span class="sxs-lookup"><span data-stu-id="0591c-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="0591c-215">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και διαχείριση τμημάτων](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0591c-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
