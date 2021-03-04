---
title: Σύνδεσμος Power Apps
description: Συνδεθείτε με το Power Apps και το Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268916"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="a2ddc-103">Σύνδεση Microsoft Power Apps (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="a2ddc-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="a2ddc-104">Φέρτε τα ενοποιημένα προφίλ πελατών στις προσωπικές σας εφαρμογές με το Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="a2ddc-105">Σύνδεση Power Apps και Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a2ddc-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="a2ddc-106">Το Customer Insights είναι μία από τις πολλές [διαθέσιμες προελεύσεις για δεδομένα στο Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="a2ddc-107">Ανατρέξτε στην Power Apps τεκμηρίωση για να μάθετε πώς μπορείτε να [προσθέσετε μια σύνδεση δεδομένων σε μια εφαρμογή](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="a2ddc-108">Συνιστάται επίσης να εξετάσετε τον [τρόπο με τον οποίο το Power Apps χρησιμοποιεί την ανάθεση για τη διαχείριση μεγάλων συνόλων δεδομένων σε Εφαρμογές καμβά](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="a2ddc-109">Διαθέσιμες οντότητες</span><span class="sxs-lookup"><span data-stu-id="a2ddc-109">Available entities</span></span>

<span data-ttu-id="a2ddc-110">Αφού προσθέσετε το Customer Insights ως σύνδεση δεδομένων, μπορείτε να επιλέξετε τις ακόλουθες οντότητες στο Power Apps:</span><span class="sxs-lookup"><span data-stu-id="a2ddc-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="a2ddc-111">Πελάτης: για να χρησιμοποιήσετε δεδομένα από το [ενοποιημένο προφίλ πελάτη](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="a2ddc-112">UnifiedActivity: για την εμφάνιση της [λωρίδας χρόνου δραστηριότητας](activities.md) στην εφαρμογή.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="a2ddc-113">Περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="a2ddc-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="a2ddc-114">Οντότητες με δυνατότητα ανάκτησης</span><span class="sxs-lookup"><span data-stu-id="a2ddc-114">Retrievable entities</span></span>

<span data-ttu-id="a2ddc-115">Μπορείτε να ανακτήσετε μόνο τις οντότητες **Πελάτης**, **UnivifedActivity** και **Τμήματα** μέσω της σύνδεσης Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="a2ddc-116">Εμφανίζονται άλλες οντότητες επειδή τις υποστηρίζει η υποκείμενη σύνδεση μέσω εναυσμάτων στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="a2ddc-117">Ανάθεση</span><span class="sxs-lookup"><span data-stu-id="a2ddc-117">Delegation</span></span>

<span data-ttu-id="a2ddc-118">Η ανάθεση λειτουργεί για την οντότητα Πελάτης και την οντότητα UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="a2ddc-119">Ανάθεση για την οντότητα **Πελάτης**: για να χρησιμοποιήσετε την ανάθεση για αυτήν την οντότητα, τα πεδία πρέπει να καταχωρούνται σε ευρετήριο στην [Αναζήτηση και ευρετήριο φίλτρων](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="a2ddc-120">Ανάθεση για **UnifiedActivity**: Η ανάθεση για αυτή την οντότητα λειτουργεί μόνο για τα πεδία **ActivityId** και **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="a2ddc-121">Για περισσότερες πληροφορίες σχετικά με την ανάθεση, ανατρέξτε στο θέμα [Λειτουργίες με δυνατότητα ανάθεσης στο Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="a2ddc-122">Δείγμα στοιχείου ελέγχου συλλογής</span><span class="sxs-lookup"><span data-stu-id="a2ddc-122">Example gallery control</span></span>

<span data-ttu-id="a2ddc-123">Για παράδειγμα, μπορείτε να προσθέσετε προφίλ πελατών σε ένα [στοιχείο ελέγχου συλλογής](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="a2ddc-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="a2ddc-124">Προσθέστε ένα στοιχείο ελέγχου **Συλλογή** σε μια εφαρμογή που δημιουργείτε.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a2ddc-125">![Προσθήκη στοιχείου συλλογής](media/connector-powerapps9.png "Προσθήκη στοιχείου συλλογής")</span><span class="sxs-lookup"><span data-stu-id="a2ddc-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="a2ddc-126">Επιλέξτε **Πελάτης** ως προέλευση δεδομένων για τα στοιχεία.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a2ddc-127">![Επιλογή μιας προέλευσης δεδομένων](media/choose-datasource-powerapps.png "Επιλογή μιας προέλευσης δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="a2ddc-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="a2ddc-128">Μπορείτε να αλλάξετε τον πίνακα δεδομένων στα δεξιά για να επιλέξετε το πεδίο για την οντότητα Πελάτη που θα εμφανίζεται στη συλλογή.</span><span class="sxs-lookup"><span data-stu-id="a2ddc-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="a2ddc-129">Εάν θέλετε να εμφανίσετε οποιοδήποτε πεδίο από τον επιλεγμένο πελάτη στη συλλογή, συμπληρώστε την ιδιότητα Κείμενο μιας ετικέτας:  **{Name_of_the_gallery}.Επιλεγμένο.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="a2ddc-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="a2ddc-130">Παράδειγμα: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="a2ddc-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="a2ddc-131">Για να εμφανίσετε την ενοποιημένη λωρίδα χρόνου για έναν πελάτη, προσθέστε ένα στοιχείο Συλλογής και προσθέστε την ιδιότητα Στοιχεία: **Filter('Ενοποιημένη δραστηριότητα πελάτη', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="a2ddc-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="a2ddc-132">Παράδειγμα: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="a2ddc-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]