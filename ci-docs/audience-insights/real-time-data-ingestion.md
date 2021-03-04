---
title: Λήψη και περιορισμοί δεδομένων σε πραγματικό χρόνο
description: Γενικές πληροφορίες σχετικά με τις δυνατότητες σε πραγματικό χρόνο σε πληροφορίες κοινού.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270280"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="fa46e-103">Συγκέντρωση δεδομένων σε πραγματικό χρόνο (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="fa46e-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="fa46e-104">Η λειτουργικότητα σε σχεδόν πραγματικό χρόνο σάς δίνει τη δυνατότητα να βλέπετε, εντός δευτερολέπτων, τις πιο πρόσφατες αλληλεπιδράσεις που έχουν πραγματοποιήσει οι πελάτες σας με τα προϊόντα ή τις υπηρεσίες σας.</span><span class="sxs-lookup"><span data-stu-id="fa46e-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="fa46e-105">[Οι προγραμματισμένες ανανεώσεις](system.md#schedule-tab) περιλαμβάνουν μεγάλο αριθμό καρτελών και διάφορες πολύπλοκες λειτουργίες.</span><span class="sxs-lookup"><span data-stu-id="fa46e-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="fa46e-106">Πρώτα, τα δεδομένα αντλούνται από την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="fa46e-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="fa46e-107">Στη συνέχεια, τα δεδομένα ενοποιούνται και, στη συνέχεια, εμπλουτίστηκαν με πρόσθετες πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="fa46e-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="fa46e-108">Κάθε εκτέλεση αυτής της διεργασίας μπορεί να διαρκέσει λεπτά έως ώρες.</span><span class="sxs-lookup"><span data-stu-id="fa46e-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="fa46e-109">Η λειτουργικότητα πραγματικού χρόνου παρέχει δεδομένα αμέσως για κατανάλωση, έως ότου η επόμενη προγραμματισμένη ανανέωση τραβήξει αυτά τα δεδομένα από την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="fa46e-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="fa46e-110">Οι ενημερώσεις σε πραγματικό χρόνο έχουν χρόνο λήξης μετά από την οποία δεν παρακάμπτουν πλέον την τιμή από την προέλευση δεδομένων:</span><span class="sxs-lookup"><span data-stu-id="fa46e-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="fa46e-111">Οι ενημερώσεις προφίλ θα διατηρούνται για 4 ώρες</span><span class="sxs-lookup"><span data-stu-id="fa46e-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="fa46e-112">Οι δραστηριότητες θα κρατηθούν για 30 ημέρες</span><span class="sxs-lookup"><span data-stu-id="fa46e-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="fa46e-113">Αυτές οι τιμές είναι παράμετροι κλήσεων API που μπορείτε να αλλάξετε.</span><span class="sxs-lookup"><span data-stu-id="fa46e-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="fa46e-114">Έχουν ως στόχο να διασφαλίσουν ότι τα δεδομένα προέλευσής σας παραμένουν η πηγή αλήθειας.</span><span class="sxs-lookup"><span data-stu-id="fa46e-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="fa46e-115">Εάν θέλετε οι ενημερώσεις πραγματικού χρόνου να συμπεριλαμβάνονται για μεγαλύτερο χρονικό διάστημα, θα πρέπει να τις προσθέσετε σε μια προέλευση δεδομένων ώστε να αντληθούν κατά την επόμενη προγραμματισμένη ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="fa46e-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="fa46e-116">Ενημέρωση σε πραγματικό χρόνο των πεδίων ενοποιημένων προφίλ πελατών</span><span class="sxs-lookup"><span data-stu-id="fa46e-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="fa46e-117">Τα ενημερωμένα προφίλ θα εμφανίζονται στην προβολή καρτών πελάτη ή σε οποιαδήποτε άλλη απεικόνιση, εντός μερικών δευτερολέπτων.</span><span class="sxs-lookup"><span data-stu-id="fa46e-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="fa46e-118">Επειδή οι λειτουργίες πραγματικού χρόνου λαμβάνουν χώρα μετά τη δημιουργία της ενοποίησης δεδομένων, εφαρμόζονται μόνο στα ενοποιημένα προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="fa46e-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="fa46e-119">Κατά συνέπεια, οι αλλαγές στο προφίλ σε πραγματικό χρόνο δεν θα ενημερώνουν τα μέτρα, την ιδιότητα μέλους τμήματος ή τις εμπλουτίσεις.</span><span class="sxs-lookup"><span data-stu-id="fa46e-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="fa46e-120">Περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="fa46e-120">Limitations</span></span>

- <span data-ttu-id="fa46e-121">Τα προφίλ πελατών μπορούν να ενημερωθούν, αλλά όχι να δημιουργηθούν ή να διαγραφούν.</span><span class="sxs-lookup"><span data-stu-id="fa46e-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="fa46e-122">Η εξαγωγή ενημερώσεων σε πραγματικό χρόνο σε εξωτερικά συστήματα, όπως το Power BI, δεν είναι δυνατή αυτή τη στιγμή.</span><span class="sxs-lookup"><span data-stu-id="fa46e-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="fa46e-123">Δημιουργία δραστηριοτήτων πραγματικού χρόνου</span><span class="sxs-lookup"><span data-stu-id="fa46e-123">Real-time creation of activities</span></span>

<span data-ttu-id="fa46e-124">Το API σε πραγματικό χρόνο σάς δίνει τη δυνατότητα να δημοσιεύσετε μια νέα δραστηριότητα από το σύστημα προέλευσής σας (μια μεμονωμένη καρτέλα προέλευσης) σε ένα ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="fa46e-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="fa46e-125">Η νέα δραστηριότητα θα είναι διαθέσιμη ως ενοποιημένη δραστηριότητα στη λωρίδα χρόνου του ενιαίου προφίλ πελάτη εντός δευτερολέπτων.</span><span class="sxs-lookup"><span data-stu-id="fa46e-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="fa46e-126">Μπορείτε να δείτε τη λωρίδα χρόνου στην προβολή καρτών πελάτη ή σε οποιαδήποτε άλλη ενοποίηση λωρίδας χρόνου της οποίας τις παραμέτρους έχετε ρυθμίσει.</span><span class="sxs-lookup"><span data-stu-id="fa46e-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fa46e-127">Οι δραστηριότητες είναι αμετάβλητες.</span><span class="sxs-lookup"><span data-stu-id="fa46e-127">Activities are immutable.</span></span> <span data-ttu-id="fa46e-128">Δεν αλλάζουν μόλις δημιουργηθούν.</span><span class="sxs-lookup"><span data-stu-id="fa46e-128">They don't change once created.</span></span>
> - <span data-ttu-id="fa46e-129">Προς το παρόν, τα τμήματα και τα μέτρα δεν θα ενημερωθούν με βάση τη νέα δραστηριότητα.</span><span class="sxs-lookup"><span data-stu-id="fa46e-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="fa46e-130">Οι δραστηριότητες που προστίθενται μόνο μέσω του API πραγματικού χρόνου δεν αποτελούν μέρος των εξαγωγών και δεν θα εμφανίζονται στο PowerBI.</span><span class="sxs-lookup"><span data-stu-id="fa46e-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="fa46e-131">Υπάρχουν δύο τρόποι για να συνδεθείτε στο API πραγματικού χρόνου:</span><span class="sxs-lookup"><span data-stu-id="fa46e-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="fa46e-132">[έμμεσα](#connect-via-the-dynamics-365-customer-insights-connector), χρησιμοποιώντας τη [σύνδεση Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="fa46e-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="fa46e-133">[απευθείας](#connect-directly-to-the-real-time-api), με κωδικό</span><span class="sxs-lookup"><span data-stu-id="fa46e-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="fa46e-134">Οι ακόλουθες προϋποθέσεις ισχύουν και για τους δύο τρόπους:</span><span class="sxs-lookup"><span data-stu-id="fa46e-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="fa46e-135">Ένα περιβάλλον Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fa46e-135">A Customer Insights environment</span></span>
- <span data-ttu-id="fa46e-136">Ενοποιημένα προφίλ πελατών</span><span class="sxs-lookup"><span data-stu-id="fa46e-136">Unified customer profiles</span></span>
- <span data-ttu-id="fa46e-137">Δραστηριότητες ρυθμισμένες που εκτελούνται</span><span class="sxs-lookup"><span data-stu-id="fa46e-137">Activities configured and run</span></span>
- <span data-ttu-id="fa46e-138">Δικαιώματα συμμετέχονται ή διαχειριστή για τον έλεγχο ταυτότητας του λογαριασμού σας</span><span class="sxs-lookup"><span data-stu-id="fa46e-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="fa46e-139">Σύνδεση μέσω του Dynamics 365 Customer Insights συνδέσμου</span><span class="sxs-lookup"><span data-stu-id="fa46e-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="fa46e-140">Το API πραγματικού χρόνου μπορεί να λάβει δεδομένα από μια ειδική Power Platform σύνδεση, τη [σύνδεση Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), χωρίς να χρειάζεται να γράψουν και να αναπτύξουν οποιονδήποτε κώδικα.</span><span class="sxs-lookup"><span data-stu-id="fa46e-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="fa46e-141">Ο σύνδεσμος μπορεί να κάνει τις ίδιες ενέργειες πραγματικού χρόνου με το API.</span><span class="sxs-lookup"><span data-stu-id="fa46e-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="fa46e-142">Χρειάζεστε μια έγκυρη άδεια χρήσης για τους premium συνδέσμους.</span><span class="sxs-lookup"><span data-stu-id="fa46e-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="fa46e-143">Για περισσότερες πληροφορίες δείτε [Συχνές ερωτήσεις για τις άδειες χρήσης των Power Apps και Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="fa46e-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="fa46e-144">Power Platform [Power Apps ή/και Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="fa46e-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="fa46e-145">Azure [λογικές εφαρμογές](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="fa46e-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="fa46e-146">Για λεπτομέρειες σχετικά με τη δημιουργία ροών, ανατρέξτε στην [τεκμηρίωση του Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="fa46e-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="fa46e-147">Απευθείας σύνδεση στο API πραγματικού χρόνου</span><span class="sxs-lookup"><span data-stu-id="fa46e-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="fa46e-148">Μπορείτε να χρησιμοποιήσετε τις δυνατότητες πραγματικού χρόνου, δημιουργώντας τη δική σας διοχέτευση και συνδεόμενοι απευθείας στο API πραγματικού χρόνου.</span><span class="sxs-lookup"><span data-stu-id="fa46e-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="fa46e-149">Μπορείτε να καταχωρήσετε μια δραστηριότητα με τη μορφή του συστήματος προέλευσής σας ή σε μορφή UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="fa46e-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="fa46e-150">Λάβετε τη μορφή κάνοντας μια κλήση API στο /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="fa46e-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="fa46e-151">Λεπτομέρειες αυτού του API, συμπεριλαμβανομένων των παραμέτρων και των αποκρίσεων, μπορείτε να βρείτε στην ενότητα **EntityData** στην [αναφορά API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="fa46e-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="fa46e-152">Για περισσότερες πληροφορίες, ανατρέξτε στο [Εργασία με API Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="fa46e-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="fa46e-153">Κατανόηση της χρήσης σε πραγματικό χρόνο με τηλεμετρία</span><span class="sxs-lookup"><span data-stu-id="fa46e-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="fa46e-154">Δείτε μια επισκόπηση του όγκου των αιτήσεων στο API πραγματικού χρόνου και των πληροφοριών σχετικά με τα ζητήματα που ενδέχεται να αντιμετωπίσει το σύστημα.</span><span class="sxs-lookup"><span data-stu-id="fa46e-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="fa46e-155">Μπορείτε να έχετε [πρόσβαση στην τηλεμετρία σε πραγματικό χρόνο](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="fa46e-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]