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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887894"
---
# <a name="data-sources-overview"></a><span data-ttu-id="eac59-103">Επισκόπηση προελεύσεων δεδομένων</span><span class="sxs-lookup"><span data-stu-id="eac59-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="eac59-104">Η δυνατότητα πληροφοριών κοινού στο Dynamics 365 Customer Insights συνδέεται με δεδομένα από ένα ευρύ σύνολο προελεύσεων.</span><span class="sxs-lookup"><span data-stu-id="eac59-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="eac59-105">Η σύνδεση με μια προέλευση δεδομένων αναφέρεται συχνά ως διεργασία της *πρόσληψης δεδομένων*.</span><span class="sxs-lookup"><span data-stu-id="eac59-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="eac59-106">Μετά από τη λήψη των δεδομένων, μπορείτε να [ενοποιήσετε](data-unification.md) και να προβείτε σε ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="eac59-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="eac59-107">Προσθήκη προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="eac59-107">Add a data source</span></span>

<span data-ttu-id="eac59-108">Ανατρέξτε στα αναλυτικά άρθρα σχετικά με τον τρόπο προσθήκης μιας προέλευσης δεδομένων, ανάλογα με το τι θα επιλέξετε.</span><span class="sxs-lookup"><span data-stu-id="eac59-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="eac59-109">Μπορείτε να προσθέσετε μια προέλευση δεδομένων με τρεις βασικούς τρόπους:</span><span class="sxs-lookup"><span data-stu-id="eac59-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="eac59-110">Μέσω δεκάδων συνδέσεων Power Query</span><span class="sxs-lookup"><span data-stu-id="eac59-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="eac59-111">Από έναν φάκελο Common Data Model</span><span class="sxs-lookup"><span data-stu-id="eac59-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="eac59-112">Από το δικό σας Common Data Service lake</span><span class="sxs-lookup"><span data-stu-id="eac59-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="eac59-113">Προσθήκη δεδομένων από προελεύσεις δεδομένων εσωτερικής εγκατάστασης</span><span class="sxs-lookup"><span data-stu-id="eac59-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="eac59-114">Η λήψη δεδομένων από προελεύσεις δεδομένων εσωτερικής εγκατάστασης στο Audience Insights υποστηρίζεται με βάση τις ροές δεδομένων του Power Platform.</span><span class="sxs-lookup"><span data-stu-id="eac59-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="eac59-115">Οι ροές δεδομένων μπορούν να ενεργοποιηθούν στο Customer Insights [παρέχοντας τη διεύθυνση URL του περιβάλλοντος Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) κατά τη ρύθμιση του περιβάλλοντος.</span><span class="sxs-lookup"><span data-stu-id="eac59-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="eac59-116">Οι προελεύσεις δεδομένων που δημιουργούνται μετά τη συσχέτιση ενός περιβάλλοντος Dataverse με το Customer Insights θα χρησιμοποιήσουν [ροές δεδομένων του Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) από προεπιλογή.</span><span class="sxs-lookup"><span data-stu-id="eac59-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="eac59-117">Οι ροές δεδομένων υποστηρίζουν τη σύνδεση εσωτερικής εγκατάστασης, χρησιμοποιώντας τις πύλες δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="eac59-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="eac59-118">Καταργήστε και δημιουργήστε εκ νέου προελεύσεις δεδομένων που υπήρχαν πριν συσχετιστεί ένα περιβάλλον Dataverse για να χρησιμοποιηθούν οι πύλες δεδομένων εσωτερικής εγκατάστασης.</span><span class="sxs-lookup"><span data-stu-id="eac59-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="eac59-119">Οι πύλες δεδομένων από ένα υπάρχον περιβάλλον Power BI ή Power Apps θα είναι ορατές και μπορείτε να τις χρησιμοποιήσετε ξανά στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eac59-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="eac59-120">Η σελίδα προέλευσης δεδομένων εμφανίζει συνδέσεις για μετάβαση στο περιβάλλον Power Platform όπου μπορείτε να προβάλετε και να ρυθμίσετε τις πύλες δεδομένων εσωτερικής εγκατάστασης.</span><span class="sxs-lookup"><span data-stu-id="eac59-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Στιγμιότυπο οθόνης της σελίδας προελεύσεων δεδομένων που δείχνει συνδέσεις που δείχνουν προς το περιβάλον του Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="eac59-122">Έλεγχος δεδομένων που έχουν ληφθεί</span><span class="sxs-lookup"><span data-stu-id="eac59-122">Review ingested data</span></span>

<span data-ttu-id="eac59-123">Θα δείτε το όνομα κάθε προέλευσης δεδομένων που ελήφθη, η κατάστασή της και την τελευταία φορά που ανανεώθηκαν τα δεδομένα για αυτήν την προέλευση.</span><span class="sxs-lookup"><span data-stu-id="eac59-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="eac59-124">Μπορείτε να ταξινομήσετε τη λίστα των προελεύσεων δεδομένων με βάση κάθε στήλη.</span><span class="sxs-lookup"><span data-stu-id="eac59-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eac59-125">![Προστέθηκε μια προέλευση δεδομένων](media/configure-data-datasource-added.png "Προστέθηκε μια προέλευση δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="eac59-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="eac59-126">Κατάσταση</span><span class="sxs-lookup"><span data-stu-id="eac59-126">Status</span></span>  |<span data-ttu-id="eac59-127">Περιγραφή</span><span class="sxs-lookup"><span data-stu-id="eac59-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="eac59-128">Επιτυχία</span><span class="sxs-lookup"><span data-stu-id="eac59-128">Successful</span></span>   |<span data-ttu-id="eac59-129">Η προέλευση δεδομένων λήφθηκε με επιτυχία εάν αναφέρεται η ώρα στη στήλη **Ανανεώθηκε**.</span><span class="sxs-lookup"><span data-stu-id="eac59-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="eac59-130">Δεν έχει γίνει εκκίνηση</span><span class="sxs-lookup"><span data-stu-id="eac59-130">Not started</span></span>   |<span data-ttu-id="eac59-131">Η προέλευση δεδομένων δεν έχει λάβει ακόμα δεδομένα ή είναι ακόμα σε λειτουργία προσχεδίου.</span><span class="sxs-lookup"><span data-stu-id="eac59-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="eac59-132">Ανανέωση</span><span class="sxs-lookup"><span data-stu-id="eac59-132">Refreshing</span></span>    |<span data-ttu-id="eac59-133">Η πρόσληψη δεδομένων βρίσκεται σε εξέλιξη.</span><span class="sxs-lookup"><span data-stu-id="eac59-133">Data ingestion is in progress.</span></span> <span data-ttu-id="eac59-134">Μπορείτε να ακυρώσετε αυτήν τη λειτουργία επιλέγοντας **Διακοπή ανανέωσης** στη στήλη **Ενέργειες**.</span><span class="sxs-lookup"><span data-stu-id="eac59-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="eac59-135">Η διακοπή της ανανέωσης μιας προέλευσης δεδομένων θα την επαναφέρει στην τελευταία κατάσταση ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="eac59-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="eac59-136">Απέτυχε</span><span class="sxs-lookup"><span data-stu-id="eac59-136">Failed</span></span>     |<span data-ttu-id="eac59-137">Κατά την πρόσληψη δεδομένων σημειώθηκαν σφάλματα.</span><span class="sxs-lookup"><span data-stu-id="eac59-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="eac59-138">Επιλέξτε την τιμή στη στήλη **Κατάσταση** οποιασδήποτε προέλευσης δεδομένων για να εξετάσετε περισσότερες λεπτομέρειες.</span><span class="sxs-lookup"><span data-stu-id="eac59-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="eac59-139">Στο τμήμα παραθύρου παράθυρο **Λεπτομέρειες προόδου**, αναπτύξτε το στοιχείο **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="eac59-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="eac59-140">Επιλέξτε **Δείτε λεπτομέρειες** για περισσότερες πληροφορίες σχετικά με την κατάσταση ανανέωσης, συμπεριλαμβανομένων των λεπτομερειών σφάλματος και των ενημερώσεων κατάντη διεργασίας.</span><span class="sxs-lookup"><span data-stu-id="eac59-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="eac59-141">Η φόρτωση των δεδομένων μπορεί να διαρκέσει αρκετά.</span><span class="sxs-lookup"><span data-stu-id="eac59-141">Loading data can take some time.</span></span> <span data-ttu-id="eac59-142">Μετά από μια επιτυχημένη ανανέωση, τα προσληφθέντα δεδομένα κατάποσης μπορούν να ελεγχθούν από τη σελίδα **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="eac59-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="eac59-143">Για περισσότερες πληροφορίες, δείτε [Οντότητες](entities.md).</span><span class="sxs-lookup"><span data-stu-id="eac59-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="eac59-144">Ανανέωση μιας προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="eac59-144">Refresh a data source</span></span>

<span data-ttu-id="eac59-145">Οι προελεύσεις δεδομένων μπορούν να ανανεωθούν σε ένα αυτόματο χρονοδιάγραμμα ή να ανανεωθούν με μη αυτόματο τρόπο κατ' απαίτηση.</span><span class="sxs-lookup"><span data-stu-id="eac59-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="eac59-146">Μεταβείτε στο **Διαχειριστής** > **Σύστημα** > [**Χρονοδιάγραμμα**](system.md#schedule-tab) για να ρυθμίσετε τις παραμέτρους προγραμματισμένων ανανεώσεων όλων των αρχείων προέλευσης δεδομένων που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="eac59-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="eac59-147">Για να ανανεώσετε μια προέλευση δεδομένων κατ' απαίτηση, ακολουθήστε τα παρακάτω βήματα:</span><span class="sxs-lookup"><span data-stu-id="eac59-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="eac59-148">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**</span><span class="sxs-lookup"><span data-stu-id="eac59-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="eac59-149">Επιλέξτε τα κατακόρυφα αποσιωπητικά δίπλα στην προέλευση δεδομένων που θέλετε να ανανεώσετε και επιλέξτε **Ανανέωση** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="eac59-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="eac59-150">Η προέλευση δεδομένων ενεργοποιείται πλέον με μη αυτόματο τρόπο ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="eac59-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="eac59-151">Εάν ανανεώσετε μια προέλευση δεδομένων θα ενημερωθεί τόσο το σχήμα της οντότητας όσο και τα δεδομένα για όλες τις οντότητες που καθορίζονται στην προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="eac59-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="eac59-152">Επιλέξτε **Διακοπή ανανέωσης** εάν θέλετε να ακυρώσετε μια υπάρχουσα ανανέωση και η προέλευση δεδομένων θα επανέλθει στην τελευταία της κατάσταση ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="eac59-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="eac59-153">Διαγραφή μιας προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="eac59-153">Delete a data source</span></span>

1. <span data-ttu-id="eac59-154">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="eac59-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="eac59-155">Επιλέξτε την κατακόρυφη έλλειψη δίπλα στην προέλευση δεδομένων που θέλετε να διαγράψετε και επιλέξτε **Διαγραφή** από το αναπτυσσόμενο μενού.</span><span class="sxs-lookup"><span data-stu-id="eac59-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="eac59-156">Επιβεβαιώστε τη διαγραφή.</span><span class="sxs-lookup"><span data-stu-id="eac59-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
