---
title: Χρησιμοποιήστε προελεύσεις δεδομένων για λήψη δεδομένων
description: Μάθετε πώς να εισαγάγετε δεδομένα από διάφορες προελεύσεις.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085530"
---
# <a name="data-sources-overview"></a><span data-ttu-id="0c452-103">Επισκόπηση προελεύσεων δεδομένων</span><span class="sxs-lookup"><span data-stu-id="0c452-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0c452-104">Η δυνατότητα πληροφοριών κοινού στο Dynamics 365 Customer Insights συνδέεται με δεδομένα από ένα ευρύ σύνολο προελεύσεων.</span><span class="sxs-lookup"><span data-stu-id="0c452-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="0c452-105">Η σύνδεση με μια προέλευση δεδομένων αναφέρεται συχνά ως διεργασία της *πρόσληψης δεδομένων*.</span><span class="sxs-lookup"><span data-stu-id="0c452-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="0c452-106">Μετά από τη λήψη των δεδομένων, μπορείτε να [ενοποιήσετε](data-unification.md) και να προβείτε σε ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="0c452-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="0c452-107">Προσθήκη προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="0c452-107">Add a data source</span></span>

<span data-ttu-id="0c452-108">Ανατρέξτε στα αναλυτικά άρθρα σχετικά με τον τρόπο προσθήκης μιας προέλευσης δεδομένων, ανάλογα με το τι θα επιλέξετε.</span><span class="sxs-lookup"><span data-stu-id="0c452-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="0c452-109">Μπορείτε να προσθέσετε μια προέλευση δεδομένων με τρεις βασικούς τρόπους:</span><span class="sxs-lookup"><span data-stu-id="0c452-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="0c452-110">Μέσω δεκάδων συνδέσεων Power Query</span><span class="sxs-lookup"><span data-stu-id="0c452-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="0c452-111">Από έναν φάκελο Common Data Model</span><span class="sxs-lookup"><span data-stu-id="0c452-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="0c452-112">Από το δικό σας Common Data Service lake</span><span class="sxs-lookup"><span data-stu-id="0c452-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="0c452-113">Προσθήκη δεδομένων από προελεύσεις δεδομένων εσωτερικής εγκατάστασης</span><span class="sxs-lookup"><span data-stu-id="0c452-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="0c452-114">Η λήψη δεδομένων από προελεύσεις δεδομένων εσωτερικής εγκατάστασης στο Audience Insights υποστηρίζεται με βάση τις ροές δεδομένων του Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0c452-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="0c452-115">Οι ροές δεδομένων μπορούν να ενεργοποιηθούν στο Customer Insights [παρέχοντας τη διεύθυνση URL του περιβάλλοντος Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) κατά τη ρύθμιση του περιβάλλοντος.</span><span class="sxs-lookup"><span data-stu-id="0c452-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="0c452-116">Οι προελεύσεις δεδομένων που δημιουργούνται μετά τη συσχέτιση ενός περιβάλλοντος Dataverse με το Customer Insights θα χρησιμοποιήσουν [ροές δεδομένων του Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) από προεπιλογή.</span><span class="sxs-lookup"><span data-stu-id="0c452-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="0c452-117">Οι ροές δεδομένων υποστηρίζουν τη σύνδεση εσωτερικής εγκατάστασης, χρησιμοποιώντας την πύλη δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0c452-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="0c452-118">Καταργήστε και δημιουργήστε εκ νέου προελεύσεις δεδομένων που υπήρχαν πριν συσχετιστεί ένα περιβάλλον Dataverse για να [χρησιμοποιηθούν οι πύλες δεδομένων εσωτερικής εγκατάστασης](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="0c452-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="0c452-119">Οι πύλες δεδομένων από ένα υπάρχον περιβάλλον Power BI ή Power Apps θα είναι ορατές και μπορείτε να τις χρησιμοποιήσετε ξανά στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0c452-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="0c452-120">Η σελίδα προέλευσης δεδομένων εμφανίζει συνδέσεις για μετάβαση στο περιβάλλον Power Platform όπου μπορείτε να προβάλετε και να ρυθμίσετε τις πύλες δεδομένων εσωτερικής εγκατάστασης.</span><span class="sxs-lookup"><span data-stu-id="0c452-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="0c452-121">Έλεγχος δεδομένων που έχουν ληφθεί</span><span class="sxs-lookup"><span data-stu-id="0c452-121">Review ingested data</span></span>

<span data-ttu-id="0c452-122">Θα δείτε το όνομα κάθε προέλευσης δεδομένων που ελήφθη, η κατάστασή της και την τελευταία φορά που ανανεώθηκαν τα δεδομένα για αυτήν την προέλευση.</span><span class="sxs-lookup"><span data-stu-id="0c452-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="0c452-123">Μπορείτε να ταξινομήσετε τη λίστα των προελεύσεων δεδομένων με βάση κάθε στήλη.</span><span class="sxs-lookup"><span data-stu-id="0c452-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0c452-124">![Προστέθηκε μια προέλευση δεδομένων](media/configure-data-datasource-added.png "Προστέθηκε μια προέλευση δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="0c452-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="0c452-125">Κατάσταση</span><span class="sxs-lookup"><span data-stu-id="0c452-125">Status</span></span>  |<span data-ttu-id="0c452-126">Περιγραφή</span><span class="sxs-lookup"><span data-stu-id="0c452-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0c452-127">Επιτυχία</span><span class="sxs-lookup"><span data-stu-id="0c452-127">Successful</span></span>   |<span data-ttu-id="0c452-128">Η προέλευση δεδομένων λήφθηκε με επιτυχία εάν αναφέρεται η ώρα στη στήλη **Ανανεώθηκε**.</span><span class="sxs-lookup"><span data-stu-id="0c452-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="0c452-129">Δεν έχει γίνει εκκίνηση</span><span class="sxs-lookup"><span data-stu-id="0c452-129">Not started</span></span>   |<span data-ttu-id="0c452-130">Η προέλευση δεδομένων δεν έχει λάβει ακόμα δεδομένα ή είναι ακόμα σε λειτουργία προσχεδίου.</span><span class="sxs-lookup"><span data-stu-id="0c452-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="0c452-131">Ανανέωση</span><span class="sxs-lookup"><span data-stu-id="0c452-131">Refreshing</span></span>    |<span data-ttu-id="0c452-132">Η πρόσληψη δεδομένων βρίσκεται σε εξέλιξη.</span><span class="sxs-lookup"><span data-stu-id="0c452-132">Data ingestion is in progress.</span></span> <span data-ttu-id="0c452-133">Μπορείτε να ακυρώσετε αυτήν τη λειτουργία επιλέγοντας **Διακοπή ανανέωσης** στη στήλη **Ενέργειες**.</span><span class="sxs-lookup"><span data-stu-id="0c452-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="0c452-134">Η διακοπή της ανανέωσης μιας προέλευσης δεδομένων θα την επαναφέρει στην τελευταία κατάσταση ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="0c452-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="0c452-135">Απέτυχε</span><span class="sxs-lookup"><span data-stu-id="0c452-135">Failed</span></span>     |<span data-ttu-id="0c452-136">Κατά την πρόσληψη δεδομένων σημειώθηκαν σφάλματα.</span><span class="sxs-lookup"><span data-stu-id="0c452-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="0c452-137">Επιλέξτε την τιμή στη στήλη **Κατάσταση** οποιασδήποτε προέλευσης δεδομένων για να εξετάσετε περισσότερες λεπτομέρειες.</span><span class="sxs-lookup"><span data-stu-id="0c452-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="0c452-138">Στο τμήμα παραθύρου παράθυρο **Λεπτομέρειες προόδου**, αναπτύξτε το στοιχείο **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="0c452-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="0c452-139">Επιλέξτε **Δείτε λεπτομέρειες** για περισσότερες πληροφορίες σχετικά με την κατάσταση ανανέωσης, συμπεριλαμβανομένων των λεπτομερειών σφάλματος και των ενημερώσεων κατάντη διεργασίας.</span><span class="sxs-lookup"><span data-stu-id="0c452-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="0c452-140">Η φόρτωση των δεδομένων μπορεί να διαρκέσει αρκετά.</span><span class="sxs-lookup"><span data-stu-id="0c452-140">Loading data can take some time.</span></span> <span data-ttu-id="0c452-141">Μετά από μια επιτυχημένη ανανέωση, τα προσληφθέντα δεδομένα κατάποσης μπορούν να ελεγχθούν από τη σελίδα **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="0c452-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="0c452-142">Για περισσότερες πληροφορίες, δείτε [Οντότητες](entities.md).</span><span class="sxs-lookup"><span data-stu-id="0c452-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="0c452-143">Ανανέωση μιας προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="0c452-143">Refresh a data source</span></span>

<span data-ttu-id="0c452-144">Οι προελεύσεις δεδομένων μπορούν να ανανεωθούν σε ένα αυτόματο χρονοδιάγραμμα ή να ανανεωθούν με μη αυτόματο τρόπο κατ' απαίτηση.</span><span class="sxs-lookup"><span data-stu-id="0c452-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="0c452-145">Μεταβείτε στο **Διαχειριστής** > **Σύστημα** > [**Χρονοδιάγραμμα**](system.md#schedule-tab) για να ρυθμίσετε τις παραμέτρους προγραμματισμένων ανανεώσεων όλων των αρχείων προέλευσης δεδομένων που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="0c452-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="0c452-146">Για να ανανεώσετε μια προέλευση δεδομένων κατ' απαίτηση, ακολουθήστε τα παρακάτω βήματα:</span><span class="sxs-lookup"><span data-stu-id="0c452-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="0c452-147">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**</span><span class="sxs-lookup"><span data-stu-id="0c452-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="0c452-148">Επιλέξτε τα κατακόρυφα αποσιωπητικά δίπλα στην προέλευση δεδομένων που θέλετε να ανανεώσετε και επιλέξτε **Ανανέωση** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="0c452-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="0c452-149">Η προέλευση δεδομένων ενεργοποιείται πλέον με μη αυτόματο τρόπο ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="0c452-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="0c452-150">Εάν ανανεώσετε μια προέλευση δεδομένων θα ενημερωθεί τόσο το σχήμα της οντότητας όσο και τα δεδομένα για όλες τις οντότητες που καθορίζονται στην προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="0c452-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="0c452-151">Επιλέξτε **Διακοπή ανανέωσης** εάν θέλετε να ακυρώσετε μια υπάρχουσα ανανέωση και η προέλευση δεδομένων θα επανέλθει στην τελευταία της κατάσταση ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="0c452-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="0c452-152">Διαγραφή μιας προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="0c452-152">Delete a data source</span></span>

1. <span data-ttu-id="0c452-153">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="0c452-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0c452-154">Επιλέξτε την κατακόρυφη έλλειψη δίπλα στην προέλευση δεδομένων που θέλετε να διαγράψετε και επιλέξτε **Διαγραφή** από το αναπτυσσόμενο μενού.</span><span class="sxs-lookup"><span data-stu-id="0c452-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="0c452-155">Επιβεβαιώστε τη διαγραφή.</span><span class="sxs-lookup"><span data-stu-id="0c452-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
