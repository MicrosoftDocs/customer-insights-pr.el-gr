---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργία ροών στο Microsoft Power Automate από Dynamics 365 Customer Insights .
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976088"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="8a6b7-103">Σύνδεση Power Automate (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="8a6b7-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="8a6b7-104">Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8a6b7-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="8a6b7-105">Ενεργοποιήσεις Power Automate</span><span class="sxs-lookup"><span data-stu-id="8a6b7-105">Power Automate triggers</span></span>

<span data-ttu-id="8a6b7-106">Χρησιμοποιήστε εναύσματα για να δημιουργήσετε ροές cloud και να αυτοματοποιήσετε επαναλαμβανόμενες εργασίες, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="8a6b7-107">Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="8a6b7-108">Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="8a6b7-109">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="8a6b7-110">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="8a6b7-111">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="8a6b7-112">Μόνο επιχειρηματικά μέτρα χωρίς διάσταση υποστηρίζονται.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="8a6b7-113">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="8a6b7-114">Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα,...).</span><span class="sxs-lookup"><span data-stu-id="8a6b7-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="8a6b7-115">Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).</span><span class="sxs-lookup"><span data-stu-id="8a6b7-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="8a6b7-116">[Ρυθμίστε τις παραμέτρους των εναυσμάτων στο Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="8a6b7-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="8a6b7-117">Ενέργειες Power Automate</span><span class="sxs-lookup"><span data-stu-id="8a6b7-117">Power Automate actions</span></span>
<span data-ttu-id="8a6b7-118">Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="8a6b7-119">Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="8a6b7-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="8a6b7-120">Δημιουργία μιας ροής Power Automate</span><span class="sxs-lookup"><span data-stu-id="8a6b7-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="8a6b7-121">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8a6b7-122">Στο πλακίδιο **Power Automate**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="8a6b7-123">Ανοίγει η σύνδεση του Customer Insights (προεπισκόπηση) στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="8a6b7-124">**Συνδεθείτε** στο Power Automate.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="8a6b7-125">Επιλέξτε ένα από τα διαθέσιμα εναύσματα και προσθέστε περισσότερα βήματα στη νέα σας ροή.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="8a6b7-126">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία ροής cloud στο Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="8a6b7-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="8a6b7-127">Παραδείγματα τρόπου χρήσης ροών:</span><span class="sxs-lookup"><span data-stu-id="8a6b7-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="8a6b7-128">Δημοσιεύστε ένα μήνυμα σε ένα κανάλι Microsoft Teams εάν αποτύχει μια ανανέωση προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="8a6b7-129">Αποστολή μηνύματος ηλεκτρονικού ταχυδρομείου στους κατόχους δεδομένων όταν ξεπεραστεί ένα όριο σε ένα τμήμα.</span><span class="sxs-lookup"><span data-stu-id="8a6b7-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
