---
title: Σύνδεσμος Power BI
description: Μάθετε πώς μπορείτε να χρησιμοποιείτε τον σύνδεσμο του Dynamics 365 Customer Insights στο Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477088"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="4ab99-103">Σύνδεση για το Power BI (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="4ab99-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="4ab99-104">Δημιουργήστε απεικονίσεις για τα δεδομένα σας με το Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="4ab99-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="4ab99-105">Δημιουργήστε πρόσθετες πληροφορίες και δημιουργήστε αναφορές με τα ενοποιημένα δεδομένα πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="4ab99-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ab99-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="4ab99-106">Prerequisites</span></span>

- <span data-ttu-id="4ab99-107">Έχετε ενοποιημένα προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="4ab99-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="4ab99-108">Η πιο πρόσφατη έκδοση του [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) έχει εγκατασταθεί στον υπολογιστή σας.</span><span class="sxs-lookup"><span data-stu-id="4ab99-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="4ab99-109">[Μάθετε περισσότερα για το Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="4ab99-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="4ab99-110">Ρυθμίστε τις παραμέτρους της σύνδεσης για το Power BI</span><span class="sxs-lookup"><span data-stu-id="4ab99-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="4ab99-111">Στο Power BI Desktop, επιλέξτε **Αρχείο** > **Λήψη δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="4ab99-112">Επιλέξτε **Δείτε περισσότερα** και αναζητήστε το **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="4ab99-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="4ab99-113">Επιλέξτε **Σύνδεση**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-113">Select **Connect**.</span></span>

1. <span data-ttu-id="4ab99-114">Κάντε **Σύνδεση** με τον ίδιο εταιρικό λογαριασμό που χρησιμοποιείτε για το Customer Insights και επιλέξτε **Σύνδεση**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4ab99-115">Ο λογαριασμός που υποδείξατε σε αυτό το βήμα χρησιμοποιείται για τη λήψη δεδομένων από το Customer Insights και δεν χρειάζεται να είναι ο ίδιος με αυτόν με τον οποίο συνδέεστε στο Power BI.</span><span class="sxs-lookup"><span data-stu-id="4ab99-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="4ab99-116">Για να επαναφέρετε τον λογαριασμό που χρησιμοποιείται για τη λήψη δεδομένων, ανοίξτε το Power BI και μεταβείτε στο **Αρχείο** > **Επιλογές** > **Ρυθμίσεις** > **Ρυθμίσεις προέλευσης δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="4ab99-117">Στη λίστα προελεύσεων δεδομένων, επιλέξτε **Σύνδεση στο Dynamics 365 Customer Insights** και επιλέξτε **Δικαιώματα εκκαθάρισης**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="4ab99-118">Στο πλαίσιο διαλόγου **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="4ab99-119">βλέπετε τη λίστα όων των περιβαλλόντων στα οποία έχετε πρόσβαση.</span><span class="sxs-lookup"><span data-stu-id="4ab99-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="4ab99-120">Αναπτύξτε ένα περιβάλλον και ανοίξτε οποιονδήποτε από τους φακέλους (οντότητες, μέτρα, τμήματα, εμπλουτισμοί).</span><span class="sxs-lookup"><span data-stu-id="4ab99-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="4ab99-121">Για παράδειγμα, ανοίξτε τον φάκελο **Οντότητες** για να δείτε όλες τις οντότητες που μπορείτε να εισαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="4ab99-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="4ab99-122">![Power BI Πλοηγός συνδέσμων](media/power-bi-navigator.png "Πλοηγός συνδέσμων Power BI")</span><span class="sxs-lookup"><span data-stu-id="4ab99-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="4ab99-123">Επιλέξτε τα πλαίσια ελέγχου που βρίσκονται δίπλα στις οντότητες για να συμπεριλάβετε και να **φορτώσετε**.</span><span class="sxs-lookup"><span data-stu-id="4ab99-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="4ab99-124">Μπορείτε να επιλέξετε πολλές οντότητες από πολλά περιβάλλοντα.</span><span class="sxs-lookup"><span data-stu-id="4ab99-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="4ab99-125">Θα εμφανιστεί ένα παράθυρο διαλόγου φόρτωσης, ενόσω οι οντότητες σας φορτώνονται.</span><span class="sxs-lookup"><span data-stu-id="4ab99-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="4ab99-126">Αφού φορτωθούν όλες οι επιλεγμένες οντότητες, μπορείτε να χρησιμοποιήσετε τις δυνατότητες του Power BI για να απεικονίσετε τα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="4ab99-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="4ab99-127">Μεγάλα σύνολα δεδομένων</span><span class="sxs-lookup"><span data-stu-id="4ab99-127">Large data sets</span></span>

<span data-ttu-id="4ab99-128">Ο σύνδεσμος Customer Insights για το Power BI έχει σχεδιαστεί ώστε να λειτουργεί για σύνολα δεδομένων που περιέχουν έως 1 εκατομμύριο προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="4ab99-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="4ab99-129">Η εισαγωγή μεγαλύτερων σετ δεδομένων μπορεί να λειτουργήσει, αλλά απαιτεί πολύ χρόνο.</span><span class="sxs-lookup"><span data-stu-id="4ab99-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="4ab99-130">Επιπρόσθετα, η διαδικασία θα μπορούσε να καταλήξει σε λήξη χρονικού ορίου λόγω περιορισμών του Power BI.</span><span class="sxs-lookup"><span data-stu-id="4ab99-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="4ab99-131">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Power BI : Συστάσεις για μεγάλα σύνολα δεδομένων](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="4ab99-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="4ab99-132">Εργασία με ένα υποσύνολο δεδομένων</span><span class="sxs-lookup"><span data-stu-id="4ab99-132">Work with a subset of data</span></span>

<span data-ttu-id="4ab99-133">Εξετάστε το ενδεχόμενο να εργαστείτε με ένα υποσύνολο των δεδομένων σας.</span><span class="sxs-lookup"><span data-stu-id="4ab99-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="4ab99-134">Για παράδειγμα, μπορείτε να δημιουργήσετε [τμήματα](segments.md) αντί να εξαγάγετε όλες τις καρτέλες πελατών στο Power BI.</span><span class="sxs-lookup"><span data-stu-id="4ab99-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4ab99-135">Αντιμετώπιση προβλημάτων</span><span class="sxs-lookup"><span data-stu-id="4ab99-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="4ab99-136">Το περιβάλλον Customer Insights δεν εμφανίζεται στο Power BI</span><span class="sxs-lookup"><span data-stu-id="4ab99-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="4ab99-137">Τα περιβάλλοντα που έχουν περισσότερες από μία [σχέσεις](relationships.md) που έχουν οριστεί μεταξύ δύο πανομοιότυπων οντοτήτων σε πληροφορίες κοινού δεν θα είναι διαθέσιμα στο σύνδεσμο Power BI.</span><span class="sxs-lookup"><span data-stu-id="4ab99-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="4ab99-138">Μπορείτε να αναγνωρίσετε και να καταργήσετε τις διπλότυπες σχέσεις.</span><span class="sxs-lookup"><span data-stu-id="4ab99-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="4ab99-139">Στις πληροφορίες κοινού, μεταβείτε στα **Δεδομένα** > **Σχέσεις** στο περιβάλλον που λείπει στο Power BI.</span><span class="sxs-lookup"><span data-stu-id="4ab99-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="4ab99-140">Προσδιορισμός διπλότυπων σχέσεων:</span><span class="sxs-lookup"><span data-stu-id="4ab99-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="4ab99-141">Ελέγξτε εάν έχουν καθοριστεί περισσότερες από μία σχέσεις μεταξύ των δύο οντοτήτων.</span><span class="sxs-lookup"><span data-stu-id="4ab99-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="4ab99-142">Ελέγξτε αν έχει δημιουργηθεί μια σχέση μεταξύ δύο οντοτήτων που περιλαμβάνονται και οι δύο στη διεργασία ενοποίησης.</span><span class="sxs-lookup"><span data-stu-id="4ab99-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="4ab99-143">Υπάρχει μια έμμεση σχέση που ορίζεται μεταξύ όλων των οντοτήτων που περιλαμβάνονται στη διεργασία ενοποίησης.</span><span class="sxs-lookup"><span data-stu-id="4ab99-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="4ab99-144">Καταργήστε τυχόν διπλότυπες σχέσεις που έχουν αναγνωριστεί.</span><span class="sxs-lookup"><span data-stu-id="4ab99-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="4ab99-145">Μετά την κατάργηση των διπλότυπων σχέσεων, προσπαθήστε να ρυθμίσετε ξανά τις παραμέτρους του συνδέσμου Power BI.</span><span class="sxs-lookup"><span data-stu-id="4ab99-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="4ab99-146">Το περιβάλλον θα πρέπει να είναι τώρα διαθέσιμο.</span><span class="sxs-lookup"><span data-stu-id="4ab99-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

