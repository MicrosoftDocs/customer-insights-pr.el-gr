---
title: Χρησιμοποιήστε προελεύσεις δεδομένων για λήψη δεδομένων
description: Μάθετε πώς να εισαγάγετε δεδομένα από διάφορες προελεύσεις.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595947"
---
# <a name="data-sources-overview"></a><span data-ttu-id="21cbd-103">Επισκόπηση προελεύσεων δεδομένων</span><span class="sxs-lookup"><span data-stu-id="21cbd-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="21cbd-104">Η δυνατότητα πληροφοριών κοινού στο Dynamics 365 Customer Insights συνδέεται με δεδομένα από ένα ευρύ σύνολο προελεύσεων.</span><span class="sxs-lookup"><span data-stu-id="21cbd-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="21cbd-105">Η σύνδεση με μια προέλευση δεδομένων αναφέρεται συχνά ως διεργασία της *πρόσληψης δεδομένων*.</span><span class="sxs-lookup"><span data-stu-id="21cbd-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="21cbd-106">Μετά από τη λήψη των δεδομένων, μπορείτε να [ενοποιήσετε](data-unification.md) και να προβείτε σε ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="21cbd-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="21cbd-107">Προσθήκη προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="21cbd-107">Add a data source</span></span>

<span data-ttu-id="21cbd-108">Ανατρέξτε στα αναλυτικά άρθρα σχετικά με τον τρόπο προσθήκης μιας προέλευσης δεδομένων, ανάλογα με το τι θα επιλέξετε.</span><span class="sxs-lookup"><span data-stu-id="21cbd-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="21cbd-109">Μπορείτε να προσθέσετε μια προέλευση δεδομένων με τρεις βασικούς τρόπους:</span><span class="sxs-lookup"><span data-stu-id="21cbd-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="21cbd-110">Μέσω δεκάδων συνδέσεων Power Query</span><span class="sxs-lookup"><span data-stu-id="21cbd-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="21cbd-111">Από έναν φάκελο Common Data Model</span><span class="sxs-lookup"><span data-stu-id="21cbd-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="21cbd-112">Από το δικό σας Common Data Service lake</span><span class="sxs-lookup"><span data-stu-id="21cbd-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="21cbd-113">Δεν μπορείτε να προσθέσετε ακόμα δεδομένα από προελεύσεις δεδομένων εσωτερικής εγκατάστασης.</span><span class="sxs-lookup"><span data-stu-id="21cbd-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="21cbd-114">Έλεγχος δεδομένων που έχουν ληφθεί</span><span class="sxs-lookup"><span data-stu-id="21cbd-114">Review ingested data</span></span>

<span data-ttu-id="21cbd-115">Θα δείτε το όνομα κάθε προέλευσης δεδομένων που ελήφθη, η κατάστασή της και την τελευταία φορά που ανανεώθηκαν τα δεδομένα για αυτήν την προέλευση.</span><span class="sxs-lookup"><span data-stu-id="21cbd-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="21cbd-116">Μπορείτε να ταξινομήσετε τη λίστα των προελεύσεων δεδομένων με βάση κάθε στήλη.</span><span class="sxs-lookup"><span data-stu-id="21cbd-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="21cbd-117">![Προστέθηκε μια προέλευση δεδομένων](media/configure-data-datasource-added.png "Προστέθηκε μια προέλευση δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="21cbd-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="21cbd-118">Κατάσταση</span><span class="sxs-lookup"><span data-stu-id="21cbd-118">Status</span></span>  |<span data-ttu-id="21cbd-119">Περιγραφή</span><span class="sxs-lookup"><span data-stu-id="21cbd-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="21cbd-120">Επιτυχία</span><span class="sxs-lookup"><span data-stu-id="21cbd-120">Successful</span></span>   |<span data-ttu-id="21cbd-121">Η προέλευση δεδομένων λήφθηκε με επιτυχία εάν αναφέρεται η ώρα στη στήλη **Ανανεώθηκε**.</span><span class="sxs-lookup"><span data-stu-id="21cbd-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="21cbd-122">Δεν έχει γίνει εκκίνηση</span><span class="sxs-lookup"><span data-stu-id="21cbd-122">Not started</span></span>   |<span data-ttu-id="21cbd-123">Η προέλευση δεδομένων δεν έχει λάβει ακόμα δεδομένα ή είναι ακόμα σε λειτουργία προσχεδίου.</span><span class="sxs-lookup"><span data-stu-id="21cbd-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="21cbd-124">Ανανέωση</span><span class="sxs-lookup"><span data-stu-id="21cbd-124">Refreshing</span></span>    |<span data-ttu-id="21cbd-125">Η πρόσληψη δεδομένων βρίσκεται σε εξέλιξη.</span><span class="sxs-lookup"><span data-stu-id="21cbd-125">Data ingestion is in progress.</span></span> <span data-ttu-id="21cbd-126">Μπορείτε να ακυρώσετε αυτήν τη λειτουργία επιλέγοντας **Διακοπή ανανέωσης** στη στήλη **Ενέργειες**.</span><span class="sxs-lookup"><span data-stu-id="21cbd-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="21cbd-127">Η διακοπή της ανανέωσης μιας προέλευσης δεδομένων θα την επαναφέρει στην τελευταία κατάσταση ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="21cbd-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="21cbd-128">Απέτυχε</span><span class="sxs-lookup"><span data-stu-id="21cbd-128">Failed</span></span>     |<span data-ttu-id="21cbd-129">Κατά την πρόσληψη δεδομένων σημειώθηκαν σφάλματα.</span><span class="sxs-lookup"><span data-stu-id="21cbd-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="21cbd-130">Επιλέξτε την τιμή στη στήλη **Κατάσταση** οποιασδήποτε προέλευσης δεδομένων για να εξετάσετε περισσότερες λεπτομέρειες.</span><span class="sxs-lookup"><span data-stu-id="21cbd-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="21cbd-131">Στο τμήμα παραθύρου παράθυρο **Λεπτομέρειες προόδου**, αναπτύξτε το στοιχείο **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="21cbd-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="21cbd-132">Επιλέξτε **Δείτε λεπτομέρειες** για περισσότερες πληροφορίες σχετικά με την κατάσταση ανανέωσης, συμπεριλαμβανομένων των λεπτομερειών σφάλματος και των ενημερώσεων κατάντη διεργασίας.</span><span class="sxs-lookup"><span data-stu-id="21cbd-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="21cbd-133">Η φόρτωση των δεδομένων μπορεί να διαρκέσει αρκετά.</span><span class="sxs-lookup"><span data-stu-id="21cbd-133">Loading data can take some time.</span></span> <span data-ttu-id="21cbd-134">Μετά από μια επιτυχημένη ανανέωση, τα προσληφθέντα δεδομένα κατάποσης μπορούν να ελεγχθούν από τη σελίδα **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="21cbd-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="21cbd-135">Για περισσότερες πληροφορίες, δείτε [Οντότητες](entities.md).</span><span class="sxs-lookup"><span data-stu-id="21cbd-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="21cbd-136">Ανανέωση μιας προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="21cbd-136">Refresh a data source</span></span>

<span data-ttu-id="21cbd-137">Οι προελεύσεις δεδομένων μπορούν να ανανεωθούν σε ένα αυτόματο χρονοδιάγραμμα ή να ανανεωθούν με μη αυτόματο τρόπο κατ' απαίτηση.</span><span class="sxs-lookup"><span data-stu-id="21cbd-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="21cbd-138">Μεταβείτε στο **Διαχειριστής** > **Σύστημα** > [**Χρονοδιάγραμμα**](system.md#schedule-tab) για να ρυθμίσετε τις παραμέτρους προγραμματισμένων ανανεώσεων όλων των αρχείων προέλευσης δεδομένων που έχουν ληφθεί.</span><span class="sxs-lookup"><span data-stu-id="21cbd-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="21cbd-139">Για να ανανεώσετε μια προέλευση δεδομένων κατ' απαίτηση, ακολουθήστε τα παρακάτω βήματα:</span><span class="sxs-lookup"><span data-stu-id="21cbd-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="21cbd-140">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**</span><span class="sxs-lookup"><span data-stu-id="21cbd-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="21cbd-141">Επιλέξτε τα κατακόρυφα αποσιωπητικά δίπλα στην προέλευση δεδομένων που θέλετε να ανανεώσετε και επιλέξτε **Ανανέωση** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="21cbd-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="21cbd-142">Η προέλευση δεδομένων ενεργοποιείται πλέον με μη αυτόματο τρόπο ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="21cbd-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="21cbd-143">Η ανανέωση μιας προέλευση δεδομένων θα ενημερώσει το σχήμα οντότητας, καθώς και δεδομένα για όλες τις οντότητες που καθορίζονται στην προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="21cbd-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="21cbd-144">Επιλέξτε **Διακοπή ανανέωσης** εάν θέλετε να ακυρώσετε μια υπάρχουσα ανανέωση και η προέλευση δεδομένων θα επανέλθει στην τελευταία της κατάσταση ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="21cbd-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="21cbd-145">Διαγραφή μιας προέλευσης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="21cbd-145">Delete a data source</span></span>

1. <span data-ttu-id="21cbd-146">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="21cbd-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="21cbd-147">Επιλέξτε την κατακόρυφη έλλειψη δίπλα στην προέλευση δεδομένων που θέλετε να διαγράψετε και επιλέξτε **Διαγραφή** από το αναπτυσσόμενο μενού.</span><span class="sxs-lookup"><span data-stu-id="21cbd-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="21cbd-148">Επιβεβαιώστε τη διαγραφή.</span><span class="sxs-lookup"><span data-stu-id="21cbd-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]