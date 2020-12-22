---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργήστε ροές στο Microsoft Power Automate από το Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405807"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="94524-103">Σύνδεση Power Automate (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="94524-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="94524-104">Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="94524-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="94524-105">Ενεργοποιήσεις Power Automate</span><span class="sxs-lookup"><span data-stu-id="94524-105">Power Automate triggers</span></span>

<span data-ttu-id="94524-106">Μπορείτε να χρησιμοποιήσετε μια ποικιλία εναυσμάτων που σας επιτρέπουν να δημιουργείτε ροές για την αυτοματοποίηση επαναλαμβανόμενων εργασιών, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες.</span><span class="sxs-lookup"><span data-stu-id="94524-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="94524-107">Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="94524-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="94524-108">Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="94524-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="94524-109">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="94524-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="94524-110">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="94524-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="94524-111">Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="94524-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="94524-112">Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.</span><span class="sxs-lookup"><span data-stu-id="94524-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="94524-113">Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα,...).</span><span class="sxs-lookup"><span data-stu-id="94524-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="94524-114">Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).</span><span class="sxs-lookup"><span data-stu-id="94524-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="94524-115">[Ρυθμίστε τις παραμέτρους των εναυσμάτων στο Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="94524-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="94524-116">Ενέργειες Power Automate</span><span class="sxs-lookup"><span data-stu-id="94524-116">Power Automate actions</span></span>
<span data-ttu-id="94524-117">Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα.</span><span class="sxs-lookup"><span data-stu-id="94524-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="94524-118">Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="94524-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="94524-119">Δημιουργία ροής Power Automate σε πληροφορίες κοινού</span><span class="sxs-lookup"><span data-stu-id="94524-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="94524-120">Στις πληροφορίες κοινού, μεταβείτε στο **Διαχειριστής** > **Σύστημα**.</span><span class="sxs-lookup"><span data-stu-id="94524-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="94524-121">Στη σελίδα **Σύστημα**, επιλέξτε την καρτέλα **Κατάσταση**.</span><span class="sxs-lookup"><span data-stu-id="94524-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="94524-122">Στην ενότητα **Προελεύσεις δεδομένων**, επιλέξτε **Ροές** και επιλέξτε **Δημιουργία ροής** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="94524-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94524-123">![Η σύνδεση Power Automate που δείχνει μια ενέργεια "Δημιουργία μιας ροής"](media/power-automate-connector-create-flow.png "Η σύνδεση Power Automate που δείχνει μια ενέργεια "Δημιουργία μιας ροής"")</span><span class="sxs-lookup"><span data-stu-id="94524-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="94524-124">Στο στοιχείο Power Automate, επιλέξτε ένα από τα διαθέσιμα εναύσματα για να δημιουργήσετε τη ροή που προτιμάτε.</span><span class="sxs-lookup"><span data-stu-id="94524-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="94524-125">Εάν δημιουργείτε την πρώτη σας ροή, θα πρέπει πρώτα να πραγματοποιήσετε έλεγχο ταυτότητας με τη σύνδεση του Power Automate.</span><span class="sxs-lookup"><span data-stu-id="94524-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
