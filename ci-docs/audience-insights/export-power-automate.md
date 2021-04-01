---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργία ροών στο Microsoft Power Automate από Dynamics 365 Customer Insights .
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597925"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="95905-103">Σύνδεση Power Automate (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="95905-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="95905-104">Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="95905-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="95905-105">Ενεργοποιήσεις Power Automate</span><span class="sxs-lookup"><span data-stu-id="95905-105">Power Automate triggers</span></span>

<span data-ttu-id="95905-106">Χρησιμοποιήστε εναύσματα για να δημιουργήσετε ροές cloud και να αυτοματοποιήσετε επαναλαμβανόμενες εργασίες, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="95905-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="95905-107">Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="95905-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="95905-108">Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="95905-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="95905-109">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="95905-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="95905-110">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="95905-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="95905-111">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="95905-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="95905-112">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="95905-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="95905-113">Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα,...).</span><span class="sxs-lookup"><span data-stu-id="95905-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="95905-114">Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).</span><span class="sxs-lookup"><span data-stu-id="95905-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="95905-115">[Ρυθμίστε τις παραμέτρους των εναυσμάτων στο Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="95905-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="95905-116">Ενέργειες Power Automate</span><span class="sxs-lookup"><span data-stu-id="95905-116">Power Automate actions</span></span>
<span data-ttu-id="95905-117">Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα.</span><span class="sxs-lookup"><span data-stu-id="95905-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="95905-118">Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="95905-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="95905-119">Δημιουργία μιας ροής Power Automate</span><span class="sxs-lookup"><span data-stu-id="95905-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="95905-120">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="95905-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="95905-121">Στο πλακίδιο **Power Automate**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="95905-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="95905-122">Ανοίγει η σύνδεση του Customer Insights (προεπισκόπηση) στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="95905-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="95905-123">**Συνδεθείτε** στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="95905-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="95905-124">Επιλέξτε ένα από τα διαθέσιμα εναύσματα και προσθέστε περισσότερα βήματα στη νέα σας ροή.</span><span class="sxs-lookup"><span data-stu-id="95905-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="95905-125">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία ροής cloud στο Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="95905-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="95905-126">Παραδείγματα τρόπου χρήσης ροών:</span><span class="sxs-lookup"><span data-stu-id="95905-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="95905-127">Δημοσιεύστε ένα μήνυμα σε ένα κανάλι Microsoft Teams εάν αποτύχει μια ανανέωση προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="95905-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="95905-128">Αποστολή μηνύματος ηλεκτρονικού ταχυδρομείου στους κατόχους δεδομένων όταν ξεπεραστεί ένα όριο σε ένα τμήμα.</span><span class="sxs-lookup"><span data-stu-id="95905-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]