---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργία ροών στο Microsoft Power Automate από Dynamics 365 Customer Insights .
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305064"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="89def-103">Σύνδεση Power Automate (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="89def-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="89def-104">Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="89def-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="89def-105">Ενεργοποιήσεις Power Automate</span><span class="sxs-lookup"><span data-stu-id="89def-105">Power Automate triggers</span></span>

<span data-ttu-id="89def-106">Χρησιμοποιήστε εναύσματα για να δημιουργήσετε ροές cloud και να αυτοματοποιήσετε επαναλαμβανόμενες εργασίες, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="89def-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="89def-107">Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="89def-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="89def-108">Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="89def-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="89def-109">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="89def-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="89def-110">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="89def-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="89def-111">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="89def-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="89def-112">Μόνο επιχειρηματικά μέτρα χωρίς διάσταση υποστηρίζονται.</span><span class="sxs-lookup"><span data-stu-id="89def-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="89def-113">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="89def-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="89def-114">Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα, ...).</span><span class="sxs-lookup"><span data-stu-id="89def-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="89def-115">Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).</span><span class="sxs-lookup"><span data-stu-id="89def-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="89def-116">Ρυθμίστε τις παραμέτρους στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="89def-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="89def-117">Ενέργειες Power Automate</span><span class="sxs-lookup"><span data-stu-id="89def-117">Power Automate actions</span></span>

<span data-ttu-id="89def-118">Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα.</span><span class="sxs-lookup"><span data-stu-id="89def-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="89def-119">Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="89def-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="89def-120">Δημιουργία μιας ροής Power Automate</span><span class="sxs-lookup"><span data-stu-id="89def-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="89def-121">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="89def-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="89def-122">Στο πλακίδιο **Power Automate**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="89def-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="89def-123">Ανοίγει η σύνδεση του Customer Insights (προεπισκόπηση) στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="89def-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="89def-124">**Συνδεθείτε** στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="89def-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="89def-125">Επιλέξτε ένα από τα διαθέσιμα εναύσματα και προσθέστε περισσότερα βήματα στη νέα σας ροή.</span><span class="sxs-lookup"><span data-stu-id="89def-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="89def-126">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία ροής cloud στο Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="89def-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="89def-127">Παραδείγματα του πώς να χρησιμοποιήσετε ροές:</span><span class="sxs-lookup"><span data-stu-id="89def-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="89def-128">Δημοσιεύστε ένα μήνυμα σε ένα κανάλι Microsoft Teams εάν αποτύχει μια ανανέωση προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="89def-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="89def-129">Αποστολή μηνύματος ηλεκτρονικού ταχυδρομείου στους κατόχους δεδομένων όταν ξεπεραστεί ένα όριο σε ένα τμήμα.</span><span class="sxs-lookup"><span data-stu-id="89def-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
