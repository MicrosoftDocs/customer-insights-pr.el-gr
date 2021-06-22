---
title: Οδηγός πρόβλεψης αξίας διάρκειας ζωής προϊόντος για τον πελάτη
description: Χρησιμοποιήστε αυτό το δείγμα οδηγού για να δοκιμάσετε το μοντέλο πρόβλεψης αξίας διάρκειας ζωής προϊόντος για τον πελάτη.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129945"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="68d4e-103">Οδηγός πρόβλεψης αξίας διάρκειας ζωής προϊόντος (CLV) για τον πελάτη</span><span class="sxs-lookup"><span data-stu-id="68d4e-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="68d4e-104">Αυτός ο οδηγός σας εξηγεί ένα ολοκληρωμένο παράδειγμα για την Πρόβλεψη αξίας διάρκειας ζωής προϊόντος για τον πελάτη (CLV) στο Customer Insights χρησιμοποιώντας δείγματα δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="68d4e-105">Σενάριο</span><span class="sxs-lookup"><span data-stu-id="68d4e-105">Scenario</span></span>

<span data-ttu-id="68d4e-106">Η Contoso είναι μια εταιρεία που παράγει μηχανές για καφέ και καφέ υψηλής ποιότητας.</span><span class="sxs-lookup"><span data-stu-id="68d4e-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="68d4e-107">Πουλάνε τα προϊόντα μέσω της τοποθεσίας web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="68d4e-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="68d4e-108">Η εταιρεία θέλει να κατανοήσει την τιμή (έσοδα) που μπορούν να δημιουργήσουν οι πελάτες στους επόμενους 12 μήνες.</span><span class="sxs-lookup"><span data-stu-id="68d4e-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="68d4e-109">Η γνώση της αναμενόμενης αξίας των πελατών τους στους επόμενους 12 μήνες θα τους βοηθήσει να κατευθύνουν τις προσπάθειες μάρκετινγκ σε πελάτες υψηλής αξίας.</span><span class="sxs-lookup"><span data-stu-id="68d4e-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68d4e-110">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="68d4e-110">Prerequisites</span></span>

- <span data-ttu-id="68d4e-111">Τουλάχιστον [Δικαιώματα συμμετέχοντος](permissions.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="68d4e-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="68d4e-112">Συνιστούμε να εφαρμόσετε τα παρακάτω βήματα [σε ένα νέο περιβάλλον](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="68d4e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="68d4e-113">Εργασία 1 - Λήψη δεδομένων</span><span class="sxs-lookup"><span data-stu-id="68d4e-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="68d4e-114">Εξετάστε τα άρθρα [σχετικά με την ενσωμάτωση δεδομένων](data-sources.md) και [εισαγωγή προέλευσης δεδομένων χρησιμοποιώντας συνδέσεις Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="68d4e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="68d4e-115">Οι παρακάτω πληροφορίες προϋποθέτουν ότι έχετε εξοικειωθεί με τη λήψη δεδομένων γενικά.</span><span class="sxs-lookup"><span data-stu-id="68d4e-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="68d4e-116">Λήψη δεδομένων πελατών από την πλατφόρμα eCommerce</span><span class="sxs-lookup"><span data-stu-id="68d4e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="68d4e-117">Δημιουργήστε μια προέλευση δεδομένων με το όνομα **eCommerce**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="68d4e-118">Καταχωρίστε τη διεύθυνση URL για τις επαφές [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="68d4e-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="68d4e-119">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρήση της πρώτης γραμμής ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="68d4e-120">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="68d4e-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="68d4e-121">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="68d4e-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="68d4e-122">**CreatedOn**: ημερομηνία/ώρα/ζώνη</span><span class="sxs-lookup"><span data-stu-id="68d4e-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Μετασχηματισμός ημερομηνίας γέννησης σε ημερομηνία.":::

1. <span data-ttu-id="68d4e-124">Στο πεδίο «Όνομα» στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="68d4e-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="68d4e-125">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="68d4e-126">Λήψη δεδομένων ηλεκτρονικών αγορών</span><span class="sxs-lookup"><span data-stu-id="68d4e-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="68d4e-127">Προσθέστε ένα άλλο σύνολο δεδομένων στην ίδια προέλευση δεδομένων **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="68d4e-128">Επιλέξτε ξανά τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="68d4e-129">Εισαγάγετε τη διεύθυνση URL για δεδομένα **Ηλεκτρονικών αγορών** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="68d4e-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="68d4e-130">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="68d4e-131">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="68d4e-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="68d4e-132">**PurchasedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="68d4e-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="68d4e-133">**TotalPrice**: νομισματική μονάδα</span><span class="sxs-lookup"><span data-stu-id="68d4e-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="68d4e-134">Στο πεδίο **Όνομα** στο πλευρικό τμήμα παραθύρου, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="68d4e-135">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="68d4e-136">Λήψη δεδομένων πελατών από το σχήμα πίστης</span><span class="sxs-lookup"><span data-stu-id="68d4e-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="68d4e-137">Δημιουργήστε μια προέλευση δεδομένων με όνομα **LoyaltyScheme**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="68d4e-138">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="68d4e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="68d4e-139">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="68d4e-140">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="68d4e-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="68d4e-141">**DateOfBirth**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="68d4e-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="68d4e-142">**RewardsPoints**: ακέραιος αριθμός</span><span class="sxs-lookup"><span data-stu-id="68d4e-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="68d4e-143">**CreatedOn**: ημερομηνία/ώρα</span><span class="sxs-lookup"><span data-stu-id="68d4e-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="68d4e-144">Στο πεδίο **Όνομα** στο δεξιό παράθυρο, μετονομάστε την προέλευση δεδομένων σας από **Ερώτημα** σε **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="68d4e-145">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="68d4e-146">Λήψη δεδομένων πελατών από κριτικές ιστότοπων</span><span class="sxs-lookup"><span data-stu-id="68d4e-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="68d4e-147">Δημιουργήστε μια προέλευση δεδομένων με όνομα **Τοποθεσία web**, κάντε την επιλογή εισαγωγής και επιλέξτε τη σύνδεση **Κείμενο/CSV**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="68d4e-148">Καταγράψτε τη διεύθυνση URL για τις επαφές eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="68d4e-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="68d4e-149">Κατά την επεξεργασία των δεδομένων, επιλέξτε **Μετασχηματισμός** και, στη συνέχεια, **Χρησιμοποιήστε την πρώτη γραμμή ως κεφαλίδες**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="68d4e-150">Ενημερώστε τον τύπο δεδομένων για τις στήλες που παρατίθενται παρακάτω:</span><span class="sxs-lookup"><span data-stu-id="68d4e-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="68d4e-151">**ReviewRating**: Δεκαδικός αριθμός</span><span class="sxs-lookup"><span data-stu-id="68d4e-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="68d4e-152">**ReviewDate**: ημερομηνία</span><span class="sxs-lookup"><span data-stu-id="68d4e-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="68d4e-153">Στο πεδίο "Όνομα" στο δεξιό τμήμα παραθύρου, μετονομάστε την προέλευση δεδομένων από **Ερώτημα** σε **Κριτικές**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="68d4e-154">**Αποθηκεύστε** την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="68d4e-155">Εργασία 2 - Ενοποίηση δεδομένων</span><span class="sxs-lookup"><span data-stu-id="68d4e-155">Task 2 - Data unification</span></span>

<span data-ttu-id="68d4e-156">Μετά την ενσωμάτωση των δεδομένων, αρχίζει η διαδικασία επεξεργασίας ενοποίησης δεδομένων για τη δημιουργία ενός ενοποιημένου προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="68d4e-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="68d4e-157">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Ενοποίηση δεδομένων](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="68d4e-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="68d4e-158">Αντιστ.</span><span class="sxs-lookup"><span data-stu-id="68d4e-158">Map</span></span>

1. <span data-ttu-id="68d4e-159">Μετά τη λήψη των δεδομένων, αντιστοιχίστε επαφές από το eCommerce και δεδομένα πίστης σε κοινούς τύπους δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="68d4e-160">Μετάβαση στα **Δεδομένα** > **Ενοποίηση** > **Αντιστοίχιση**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="68d4e-161">Επιλέξτε τις οντότητες που αντιπροσωπεύουν το προφίλ πελάτη – **eCommerceContacts** και **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="68d4e-162">Στη συνέχεια, επιλέξτε **Εφαρμογή**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-162">Then, select **Apply**.</span></span>

   ![ενοποίηση προελεύσεις δεδομένων ecommerce και πίστης.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="68d4e-164">Επιλέξτε **ContactId** ως πρωτεύον κλειδί για **eCommerceContacts** και **LoyaltyID** ως προωτεύον κλειδί για **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Ενοποίηση του LoyaltyId ως πρωτεύοντος κλειδιού.](media/unify-loyaltyid.png)

1. <span data-ttu-id="68d4e-166">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="68d4e-167">Αντιστοίχιση</span><span class="sxs-lookup"><span data-stu-id="68d4e-167">Match</span></span>

1. <span data-ttu-id="68d4e-168">Μετάβαση στην καρτέλα **Αντιστοίχιση** κι επιλέξτε **Ορισμός σειράς**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="68d4e-169">Στην αναπτυσσόμενη λίστα **Κύρια**, επιλέξτε **ECommerceContacts: eCommerce** ως την κύρια προέλευση και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="68d4e-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="68d4e-170">Στην αναπτυσσόμενη λίστα **Οντότητα 2**, επιλέξτε **loyCustomers : LoyaltyScheme** και συμπεριλάβετε όλες τις καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="68d4e-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Ενοποίηση αντιστοίχισης eCommerce και πίστης.](media/unify-match-order.png)

1. <span data-ttu-id="68d4e-172">Επιλέξτε **Προσθήκη κανόνα**</span><span class="sxs-lookup"><span data-stu-id="68d4e-172">Select **Add rule**</span></span>

1. <span data-ttu-id="68d4e-173">Προσθέστε την πρώτη σας συνθήκη χρησιμοποιώντας το ονοματεπώνυμο.</span><span class="sxs-lookup"><span data-stu-id="68d4e-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="68d4e-174">Για eCommerceContacts επιλέξτε **Ονοματεπώνυμο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="68d4e-175">Για loyCustomers επιλέξτε **Ονοματεπώνυμο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="68d4e-176">Επιλέξτε την αναπτυσσόμενη λίστα **Ομαλοποίηση** και επιλέξτε **Τύπος (τηλέφωνο, όνομα, διεύθυνση,...)**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="68d4e-177">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="68d4e-178">Εισαγάγετε το όνομα **Ονοματεπώνυμο, ηλεκτρονικό ταχυδρομείο** για τον νέο κανόνα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="68d4e-179">Προσθέστε μια δεύτερη συνθήκη για τη διεύθυνση ηλεκτρονικού ταχυδρομείου επιλέγοντας **Προσθήκη συνθήκης**</span><span class="sxs-lookup"><span data-stu-id="68d4e-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="68d4e-180">Για την οντότητα eCommerceContacts, επιλέξτε **ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="68d4e-181">Για την οντότητα loyCustomers, επιλέξτε **ηλεκτρονικό ταχυδρομείο** στην αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="68d4e-182">Αφήστε την «Κανονικοποίηση» κενή.</span><span class="sxs-lookup"><span data-stu-id="68d4e-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="68d4e-183">Ορίστε **Επίπεδο ακριβείας**: **Βασικό** και **Αξία**: **Υψηλή**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Ενοποίηση του κανόνα αντιστοίχισης για όνομα και μήνυμα ηλεκτρονικού ταχυδρομείου.](media/unify-match-rule.png)

1. <span data-ttu-id="68d4e-185">Επιλέξτε **Τέλος**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-185">Select **Done**.</span></span>

1. <span data-ttu-id="68d4e-186">Επιλέξτε **Αποθήκευση** και **Εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="68d4e-187">Συγχώνευση</span><span class="sxs-lookup"><span data-stu-id="68d4e-187">Merge</span></span>

1. <span data-ttu-id="68d4e-188">Μεταβείτε στην καρτέλα **Συγχώνευση**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="68d4e-189">Στην οντότητα **ContactId** για **loyCustomers**, αλλάξτε τα εμφανιζόμενο όνομα σε **ContactIdLOYALTY** για να το διαφοροποιήσετε από τα υπόλοιπα αναγνωριστικά που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="68d4e-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![μετονομάστε το contactid από αναγνωριστικό πίστης.](media/unify-merge-contactid.png)

1. <span data-ttu-id="68d4e-191">Επιλέξτε **Αποθήκευση** και **Εκτελέση συγχώνευσης και κατάντη διεργασιών**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="68d4e-192">Εργασία 3 - Ρύθμιση παραμέτρων της πρόβλεψης αξίας διάρκειας ζωής προϊόντος πελάτη</span><span class="sxs-lookup"><span data-stu-id="68d4e-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="68d4e-193">Με τα ενοποιημένα προφίλ πελατών στη θέση τους, μπορούμε τώρα να εκτελέσουμε την πρόβλεψη αξίας διάρκειας ζωής προϊόντος πελάτη.</span><span class="sxs-lookup"><span data-stu-id="68d4e-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="68d4e-194">Για αναλυτικά βήματα, ανατρέξτε στο θέμα [Πρόβλεψη αξίας διάρκειας ζωής προϊόντος πελάτη (έκδοση προεπισκόπησης)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="68d4e-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="68d4e-195">Μεταβείτε στην επιλογή **Πληροφορίες**  > **Προβλέψεις** και επιλέξτε το **Μοντέλο αξίας διάρκειας ζωής πελάτη**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="68d4e-196">Μεταβείτε στις πληροφορίες στο πλαϊνό τμήμα παραθύρου και επιλέξτε **Έναρξη**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="68d4e-197">Ονομάστε το μοντέλο **OOB eCommerce CLV Prediction** και την οντότητα εξόδου **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="68d4e-198">Καθορίστε τις προτιμήσεις μοντέλου για το μοντέλο CLV:</span><span class="sxs-lookup"><span data-stu-id="68d4e-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="68d4e-199">**Χρονική περίοδος πρόβλεψης**: **12 μήνες ή 1 έτος**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="68d4e-200">Αυτή η ρύθμιση καθορίζει πόσο μακριά στο μέλλον θα προβλεφθεί η αξία διάρκειας ζωής του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="68d4e-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="68d4e-201">**Ενεργοί πελάτες**: Καθορίστε ποιοι είναι ενεργοί πελάτες για την επιχείρησή σας.</span><span class="sxs-lookup"><span data-stu-id="68d4e-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="68d4e-202">Ορίστε το ιστορικό χρονικό πλαίσιο στο οποίο ο πελάτης πρέπει να έχει τουλάχιστον μία συναλλαγή για να θεωρηθεί ενεργός.</span><span class="sxs-lookup"><span data-stu-id="68d4e-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="68d4e-203">Το μοντέλο θα προβλέπει CLV μόνο για ενεργούς πελάτες.</span><span class="sxs-lookup"><span data-stu-id="68d4e-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="68d4e-204">Επιλέξτε μεταξύ του να αφήσετε το μοντέλο να υπολογίσει τη χρονική περίοδο με βάση ιστορικά δεδομένα συναλλαγής ή να καταχωρίσετε ένα συγκεκριμένο χρονικό πλαίσιο.</span><span class="sxs-lookup"><span data-stu-id="68d4e-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="68d4e-205">Σε αυτό το δείγμα οδηγού, **αφήνουμε το μοντέλο να υπολογίσει το χρονικό διάστημα αγορών**, που είναι η προεπιλεγμένη επιλογή.</span><span class="sxs-lookup"><span data-stu-id="68d4e-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="68d4e-206">**Πελάτες υψηλής αξίας**: Καθορίστε τους πελάτες υψηλής αξίας ως ποσοστό των πελατών με τις κορυφαίες πληρωμές.</span><span class="sxs-lookup"><span data-stu-id="68d4e-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="68d4e-207">Το μοντέλο χρησιμοποιεί αυτές τις πληροφορίες για να παράσχει αποτελέσματα που ταιριάζουν με τον επιχειρηματικό ορισμό των πελατών υψηλής αξίας.</span><span class="sxs-lookup"><span data-stu-id="68d4e-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="68d4e-208">Μπορείτε να επιλέξετε το μοντέλο να ορίσει τους πελάτες υψηλής αξίας.</span><span class="sxs-lookup"><span data-stu-id="68d4e-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="68d4e-209">Χρησιμοποιεί έναν ευρετικό κανόνα που εξαγάγει εκατοστημόριο.</span><span class="sxs-lookup"><span data-stu-id="68d4e-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="68d4e-210">Μπορείτε επίσης να καθορίσετε πελάτες υψηλής αξίας ως ποσοστό των πελατών με τις μελλοντικές κορυφαίες πληρωμές.</span><span class="sxs-lookup"><span data-stu-id="68d4e-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="68d4e-211">Σε αυτό το δείγμα οδηγού, ορίζουμε με μη αυτόματο τρόπο τους πελάτες υψηλής αξίας **ως το κορυφαίο 30% των ενεργών πελατών που καταβάλλουν πληρωμές** και επιλέγουμε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Βήμα προτιμήσεων στην καθοδηγούμενη εμπειρία για το μοντέλο CLV.":::

1. <span data-ttu-id="68d4e-213">Στο βήμα **Απαιτούμενα δεδομένα**, επιλέξτε **Προσθήκη δεδομένων** για την παροχή των δεδομένων ιστορικού συναλλαγών.</span><span class="sxs-lookup"><span data-stu-id="68d4e-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="68d4e-214">Προσθέστε την οντότητα **eCommercePurchases : eCommerce** και αντιστοιχίστε τα χαρακτηριστικά που απαιτούνται από το μοντέλο:</span><span class="sxs-lookup"><span data-stu-id="68d4e-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="68d4e-215">Αναγνωριστικό συναλλαγής: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="68d4e-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="68d4e-216">Ημερομηνία συναλλαγής: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="68d4e-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="68d4e-217">Ποσό συναλλαγής: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="68d4e-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="68d4e-218">Αναγνωριστικό προϊόντος: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="68d4e-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="68d4e-219">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-219">Select **Next**.</span></span>

1. <span data-ttu-id="68d4e-220">Ρυθμίστε τη σχέση μεταξύ της οντότητας **eCommercePurchases : eCommerce** και **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="68d4e-221">Το βήμα **Πρόσθετα δεδομένα (προαιρετικό)** σάς επιτρέπει να προσθέσετε περισσότερα δεδομένα δραστηριότητας πελατών.</span><span class="sxs-lookup"><span data-stu-id="68d4e-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="68d4e-222">Αυτά τα δεδομένα μπορούν να σας βοηθήσουν να έχετε περισσότερες πληροφορίες για τις αλληλεπιδράσεις των πελατών με την επιχείρησή σας, οι οποίες μπορούν να συνεισφέρουν στο CLV.</span><span class="sxs-lookup"><span data-stu-id="68d4e-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="68d4e-223">Η προσθήκη βασικών αλληλεπιδράσεων με πελάτες, όπως αρχεία καταγραφής web, αρχεία καταγραφής εξυπηρέτησης πελατών ή ιστορικό προγράμματος επιβραβεύσεις μπορεί να βελτιώσει την ακρίβεια των προγνώσεων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="68d4e-224">Επιλέξτε **Προσθήκη δεδομένων** για να συμπεριλάβετε περισσότερα δεδομένα δραστηριότητας πελατών.</span><span class="sxs-lookup"><span data-stu-id="68d4e-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="68d4e-225">Προσθέστε την οντότητα δραστηριότητας πελάτη και αντιστοιχστε τα ονόματα πεδίων στα αντίστοιχα πεδία που απαιτούνται από το μοντέλο:</span><span class="sxs-lookup"><span data-stu-id="68d4e-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="68d4e-226">Οντότητα δραστηριότητας πελάτη: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="68d4e-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="68d4e-227">Κύριο κλειδί: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="68d4e-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="68d4e-228">Χρονική σήμανση: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="68d4e-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="68d4e-229">Συμβάν (όνομα δραστηριότητας): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="68d4e-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="68d4e-230">Λεπτομέρειες (ποσό ή αξία): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="68d4e-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="68d4e-231">Επιλέξτε **Επόμενο** και ρυθμίστε τη δραστηριότητα και τη σχέση μεταξύ των δεδομένων συναλλαγής και των δεδομένων του πελάτη:</span><span class="sxs-lookup"><span data-stu-id="68d4e-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="68d4e-232">Τύπος δραστηριότητας: Επιλογή υπάρχουσας</span><span class="sxs-lookup"><span data-stu-id="68d4e-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="68d4e-233">Ετικέτα δραστηριότητας: Κριτική</span><span class="sxs-lookup"><span data-stu-id="68d4e-233">Activity label: Review</span></span>
   - <span data-ttu-id="68d4e-234">Αντίστοιχη ετικέτα: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="68d4e-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="68d4e-235">Οντότητα πελάτη: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="68d4e-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="68d4e-236">Σχέση: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="68d4e-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="68d4e-237">Επιλέξτε **Επόμενο** για να ορίσετε το χρονοδιάγραμμα μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="68d4e-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="68d4e-238">Το μοντέλο πρέπει να εκπαιδεύεται σε τακτά χρονικά διαστήματα για να μαθαίνει νέα μοτίβα όταν συγχωνεύονται νέα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="68d4e-239">Για αυτό το παράδειγμα, επιλέξτε **Μηνιαία**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="68d4e-240">Αφού εξετάσετε όλες τις λεπτομέρειες, επιλέξτε **Αποθήκευση και εκτέλεση**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="68d4e-241">Εργασία 4 - Αναθεώρηση αποτελεσμάτων μοντέλου και επεξηγήσεις</span><span class="sxs-lookup"><span data-stu-id="68d4e-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="68d4e-242">Αφήστε το μοντέλο να ολοκληρώσει την εκπαίδευση και τη βαθμολόγηση των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="68d4e-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="68d4e-243">Στη συνέχεια, μπορείτε να εξετάσετε τα αποτελέσματα και τις επεξηγήσεις του μοντέλου CLV.</span><span class="sxs-lookup"><span data-stu-id="68d4e-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="68d4e-244">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Επανεξέταση μιας κατάστασης πρόβλεψης και αποτελέσματα](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="68d4e-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="68d4e-245">Εργασία 5 - Δημιουργία τμήματος αγοράς πελατών υψηλής αξίας</span><span class="sxs-lookup"><span data-stu-id="68d4e-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="68d4e-246">Η εκτέλεση του μοντέλου δημιουργεί μια νέα οντότητα, η οποία παρατίθενται στα **Δεδομένα** > **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="68d4e-247">Μπορείτε να δημιουργήσετε ένα νέο τμήμα αγοράς με βάση την οντότητα που δημιουργήθηκε από το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="68d4e-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="68d4e-248">Μετάβαση στα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="68d4e-249">Επιλέξτε **Νέο** και επιλέξτε **Δημιουργία από** > **Πληροφορίες**.</span><span class="sxs-lookup"><span data-stu-id="68d4e-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Δημιουργία τμήματος με την έξοδο μοντέλου.](media/segment-intelligence.png)

1. <span data-ttu-id="68d4e-251">Επιλέξτε την οντότητα **OOBeCommerceCLVPrediction** και καθορίστε το τμήμα:</span><span class="sxs-lookup"><span data-stu-id="68d4e-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="68d4e-252">Πεδίο: CLVScore</span><span class="sxs-lookup"><span data-stu-id="68d4e-252">Field: CLVScore</span></span>
  - <span data-ttu-id="68d4e-253">Τελεστής: μεγαλύτερο από</span><span class="sxs-lookup"><span data-stu-id="68d4e-253">Operator: greater than</span></span>
  - <span data-ttu-id="68d4e-254">Τιμή: 1500</span><span class="sxs-lookup"><span data-stu-id="68d4e-254">Value: 1500</span></span>

1. <span data-ttu-id="68d4e-255">Επιλέξτε **Κριτική** και **Αποθήκευση** για το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="68d4e-256">Τώρα έχετε ένα τμήμα της αγοράς που προσδιορίζει τους πελάτες για τους οποίους υπάρχει πρόβλεψη να δημιουργήσουν περισσότερα από $1500 έσοδα στους επόμενους 12 μήνες.</span><span class="sxs-lookup"><span data-stu-id="68d4e-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="68d4e-257">Αυτό το τμήμα ενημερώνεται δυναμικά, εάν συγχωνευτουν περισσότερα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="68d4e-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="68d4e-258">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και διαχείριση τμημάτων](segments.md).</span><span class="sxs-lookup"><span data-stu-id="68d4e-258">For more information, see [Create and manage segments](segments.md).</span></span>
