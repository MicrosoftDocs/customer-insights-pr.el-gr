---
title: Σύνδεσμος Power BI
description: Μάθετε πώς μπορείτε να χρησιμοποιείτε τον σύνδεσμο του Dynamics 365 Customer Insights στο Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405812"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="2bf7d-103">Σύνδεση για το Power BI (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="2bf7d-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="2bf7d-104">Δημιουργήστε απεικονίσεις για τα δεδομένα σας με το Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="2bf7d-105">Δημιουργήστε πρόσθετες πληροφορίες και δημιουργήστε αναφορές με τα ενοποιημένα δεδομένα πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bf7d-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="2bf7d-106">Prerequisites</span></span>

- <span data-ttu-id="2bf7d-107">Έχετε ενοποιημένα προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="2bf7d-108">Η πιο πρόσφατη έκδοση του [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) έχει εγκατασταθεί στον υπολογιστή σας.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="2bf7d-109">[Μάθετε περισσότερα για το Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="2bf7d-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="2bf7d-110">Ρυθμίστε τις παραμέτρους της σύνδεσης για το Power BI</span><span class="sxs-lookup"><span data-stu-id="2bf7d-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="2bf7d-111">Στο Power BI Desktop, επιλέξτε **Αρχείο** > **Λήψη δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="2bf7d-112">Επιλέξτε **Δείτε περισσότερα** και αναζητήστε το **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="2bf7d-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="2bf7d-113">Επιλέξτε το αποτέλεσμα και επιλέξτε **Σύνδεση**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="2bf7d-114">Κάντε **Σύνδεση** με τον ίδιο εταιρικό λογαριασμό που χρησιμοποιείτε για το Customer Insights και επιλέξτε **Σύνδεση**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2bf7d-115">Ο λογαριασμός που υποδείξατε σε αυτό το βήμα χρησιμοποιείται για τη λήψη δεδομένων από το Customer Insights και δεν χρειάζεται να είναι ο ίδιος με αυτόν με τον οποίο συνδέεστε στο Power BI.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="2bf7d-116">Για να επαναφέρετε τον λογαριασμό που χρησιμοποιείται για τη λήψη δεδομένων, ανοίξτε το Power BI και μεταβείτε στο **Αρχείο** > **Επιλογές** > **Ρυθμίσεις** > **Ρυθμίσεις προέλευσης δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="2bf7d-117">Στη λίστα προελεύσεων δεδομένων, επιλέξτε **Σύνδεση στο Dynamics 365 Customer Insights** και επιλέξτε **Δικαιώματα εκκαθάρισης**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="2bf7d-118">Στο πλαίσιο διαλόγου **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="2bf7d-119">βλέπετε τη λίστα όων των περιβαλλόντων στα οποία έχετε πρόσβαση.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="2bf7d-120">Αναπτύξτε ένα περιβάλλον και ανοίξτε οποιονδήποτε από τους φακέλους (οντότητες, μέτρα, τμήματα, εμπλουτισμοί).</span><span class="sxs-lookup"><span data-stu-id="2bf7d-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="2bf7d-121">Για παράδειγμα, ανοίξτε τον φάκελο **Οντότητες** για να δείτε όλες τις οντότητες που μπορείτε να εισαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="2bf7d-122">![Power BI Πλοηγός συνδέσμων](media/power-bi-navigator.png "Πλοηγός συνδέσμων Power BI")</span><span class="sxs-lookup"><span data-stu-id="2bf7d-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="2bf7d-123">Επιλέξτε τα πλαίσια ελέγχου που βρίσκονται δίπλα στις οντότητες για να συμπεριλάβετε και να **φορτώσετε**.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="2bf7d-124">Μπορείτε να επιλέξετε πολλές οντότητες από πολλά περιβάλλοντα.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="2bf7d-125">Θα εμφανιστεί ένα παράθυρο διαλόγου φόρτωσης, ενόσω οι οντότητες σας φορτώνονται.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="2bf7d-126">Αφού φορτωθούν όλες οι επιλεγμένες οντότητες, μπορείτε να χρησιμοποιήσετε τις δυνατότητες του Power BI για να απεικονίσετε τα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="2bf7d-127">Μεγάλα σύνολα δεδομένων</span><span class="sxs-lookup"><span data-stu-id="2bf7d-127">Large data sets</span></span>

<span data-ttu-id="2bf7d-128">Ο σύνδεσμος Customer Insights για το Power BI έχει σχεδιαστεί ώστε να λειτουργεί για σύνολα δεδομένων που περιέχουν έως 1 εκατομμύριο προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="2bf7d-129">Η εισαγωγή μεγαλύτερων σετ δεδομένων μπορεί να λειτουργήσει, αλλά απαιτεί πολύ χρόνο.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="2bf7d-130">Επιπρόσθετα, η διαδικασία θα μπορούσε να καταλήξει σε λήξη χρονικού ορίου λόγω περιορισμών του Power BI.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="2bf7d-131">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Power BI : Συστάσεις για μεγάλα σύνολα δεδομένων](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="2bf7d-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="2bf7d-132">Εργασία με ένα υποσύνολο δεδομένων</span><span class="sxs-lookup"><span data-stu-id="2bf7d-132">Work with a subset of data</span></span>

<span data-ttu-id="2bf7d-133">Εξετάστε το ενδεχόμενο να εργαστείτε με ένα υποσύνολο των δεδομένων σας.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="2bf7d-134">Για παράδειγμα, μπορείτε να δημιουργήσετε [τμήματα](segments.md) αντί να εξαγάγετε όλες τις καρτέλες πελατών στο Power BI.</span><span class="sxs-lookup"><span data-stu-id="2bf7d-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
