---
title: Bot για Microsoft Teams
description: Αναζητήστε ενοποιημένα προφίλ πελατών στο Microsoft Teams με τη βοήθεια ενός bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405840"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="c0425-103">Bot του Teams για το Dynamics 365 Customer Insights (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="c0425-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="c0425-104">Συνδεθείτε με το Microsoft Teams για να επιτρέψετε σε ένα bot να αναζητήσει ενοποιημένα προφίλ πελατών στα κανάλια Teams.</span><span class="sxs-lookup"><span data-stu-id="c0425-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0425-105">![Bot Teams που εμφανίζουν μια καρτέλα πελάτη](media/teams-bot.png "Bot Teams που εμφανίζουν μια καρτέλα πελάτη")</span><span class="sxs-lookup"><span data-stu-id="c0425-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c0425-106">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="c0425-106">Prerequisites</span></span>

<span data-ttu-id="c0425-107">Για να ρυθμίσετε και να ρυθμίσετε τις παραμέτρους του bot, πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="c0425-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c0425-108">Να έχει προστεθεί τουλάχιστον μία [προέλευση δεδομένων](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="c0425-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="c0425-109">Η [διαδικασία ενοποίησης](data-unification.md) να έχει ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="c0425-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="c0425-110">Τα πεδία να έχουν προστεθεί στο [ευρετήριο αναζήτησης και φιλτραρίσματος](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="c0425-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="c0425-111">Το Customer Insights και το Teams να βρίσκονται στον ίδιο οργανισμό.</span><span class="sxs-lookup"><span data-stu-id="c0425-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="c0425-112">Ρυθμίστε τις παραμέτρους του bot</span><span class="sxs-lookup"><span data-stu-id="c0425-112">Configure the bot</span></span>

1. <span data-ttu-id="c0425-113">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="c0425-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="c0425-114">Στο πλακίδιο Microsoft Teams, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="c0425-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="c0425-115">Θα ανακατευθυνθείτε στην περιοχή **Εφαρμογές** στο Teams.</span><span class="sxs-lookup"><span data-stu-id="c0425-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="c0425-116">Μπορείτε, επίσης, να ανοίξετε το Teams και να επιλέξετε **Εφαρμογές** στην κάτω αριστερή γωνία ή [να το λάβετε από το AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) απευθείας.</span><span class="sxs-lookup"><span data-stu-id="c0425-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="c0425-117">Αναζητήστε το **Customer Insights** και επιλέξτε την εφαρμογή.</span><span class="sxs-lookup"><span data-stu-id="c0425-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="c0425-118">Επιλέξτε **Προσθήκη**.</span><span class="sxs-lookup"><span data-stu-id="c0425-118">Select **Add**.</span></span>
1. <span data-ttu-id="c0425-119">Αφού συνδέσετε το Customer Insights με το Teams, θα δείτε ένα μήνυμα καλωσορίσματος και μπορείτε να ξεκινήσετε.</span><span class="sxs-lookup"><span data-stu-id="c0425-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="c0425-120">Πράγματα που μπορείτε να κάνετε με το bot</span><span class="sxs-lookup"><span data-stu-id="c0425-120">Things you can do with the bot</span></span>

<span data-ttu-id="c0425-121">Το bot παρέχει δυνατότητες αναζήτησης για ενοποιημένα προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="c0425-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="c0425-122">Καταχωρίστε **αναζήτηση** που ακολουθείται από ένα όνομα, μια διεύθυνση ηλεκτρονικού ταχυδρομείου ή οποιοδήποτε άλλο πεδίο στο ενοποιημένο προφίλ πελάτη, το οποίο προστίθεται στο ευρετήριο αναζήτησης και φιλτραρίσματος.</span><span class="sxs-lookup"><span data-stu-id="c0425-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="c0425-123">Θα λάβετε μια κάρτα με έως και 15 πεδία από το προφίλ πελάτη που προκύπτει.</span><span class="sxs-lookup"><span data-stu-id="c0425-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="c0425-124">Οι πολλαπλοί συνδυασμοί επιστρέφουν μια λίστα αποτελεσμάτων όπου μπορείτε να επιλέξετε ένα προφίλ.</span><span class="sxs-lookup"><span data-stu-id="c0425-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="c0425-125">Μπορείτε να προσθέσετε τον όρο αναζήτησης σε διπλά εισαγωγικά για να αναζητήσετε μια ακριβή αντιστοίχιση.</span><span class="sxs-lookup"><span data-stu-id="c0425-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="c0425-126">Εάν ο οργανισμός σας διατηρεί πολλά περιβάλλοντα Customer Insights στον ίδιο οργανισμό, μπορείτε να εισαγάγετε **switchinstance** για να επιλέξετε σε ποιο περιβάλλον θέλετε να συνδέσετε το bot.</span><span class="sxs-lookup"><span data-stu-id="c0425-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="c0425-127">Εισάγετε **βοήθεια** για να δείτε μια λίστα με τις διαθέσιμες εντολές για το bot.</span><span class="sxs-lookup"><span data-stu-id="c0425-127">Enter **help** to see a list of available commands for the bot.</span></span>  
