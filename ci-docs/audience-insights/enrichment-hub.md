---
title: Εμπλουτισμός ενοποιημένων προφίλ πελάτη
description: Χρησιμοποιήστε τις δυνατότητες για να εμπλουτίσετε τα δεδομένα των πελατών σας.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269468"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="0bd65-103">Εμπλουτισμός για προφίλ πελατών (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="0bd65-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="0bd65-104">Χρησιμοποιήστε δεδομένα από προελεύσεις όπως η Microsoft και άλλοι συνεργάτες για τον εμπλουτισμό των δεδομένων των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="0bd65-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Σελίδα κέντρου εμπλουτισμού":::

<span data-ttu-id="0bd65-106">Στις πληροφορίες κοινού, μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** για να εργαστείτε με επιλογές εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="0bd65-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="0bd65-107">Πρέπει να έχετε ρόλο Συμμετέχων ή Διαχειριστής για να δημιουργήσετε ή να επεξεργαστείτε εμπλουτισμούς.</span><span class="sxs-lookup"><span data-stu-id="0bd65-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="0bd65-108">Για περισσότερες πληροφορίες, δείτε [Δικαιώματα](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0bd65-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="0bd65-109">Στην καρτέλα **Ανακάλυψη**, θα βρείτε τους παρακάτω εμπλουτισμούς:</span><span class="sxs-lookup"><span data-stu-id="0bd65-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="0bd65-110">[Επωνυμίες](enrichment-microsoft-graph.md) που παρέχονται από το Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="0bd65-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="0bd65-111">[Ενδιαφέροντα](enrichment-microsoft-graph.md) που παρέχονται από το Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="0bd65-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="0bd65-112">[Εταιρικά δεδομένα](enrichment-leadspace.md) που παρέχονται από το Leadspace</span><span class="sxs-lookup"><span data-stu-id="0bd65-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="0bd65-113">[Δημογραφικά στοιχεία](enrichment-experian.md) που παρέχονται από το Experian</span><span class="sxs-lookup"><span data-stu-id="0bd65-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="0bd65-114">[Δεδομένα θέσης](enrichment-here.md) παρέχονται από τις τεχνολογίες HERE</span><span class="sxs-lookup"><span data-stu-id="0bd65-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="0bd65-115">[Προσαρμοσμένα δεδομένα](enrichment-SFTP-custom-import.md) μέσω πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP)</span><span class="sxs-lookup"><span data-stu-id="0bd65-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="0bd65-116">Στην καρτέλα **Οι εμπλουτισμοί μου**, μπορείτε να δείτε τους εμπλουτισμούς που έχετε ρυθμίσει και να επεξεργαστείτε τις ιδιότητές τους.</span><span class="sxs-lookup"><span data-stu-id="0bd65-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="0bd65-117">Διαχείριση υφιστάμενων εμπλουτισμών</span><span class="sxs-lookup"><span data-stu-id="0bd65-117">Manage existing enrichments</span></span>

<span data-ttu-id="0bd65-118">Μεταβείτε στην επιλογή **Οι εμπλουτισμοί μου** για να δείτε όλους τους ρυθμισμένους εμπλουτισμούς.</span><span class="sxs-lookup"><span data-stu-id="0bd65-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="0bd65-119">Κάθε εμπλουτισμός απεικονίζεται ως μια γραμμή που περιλαμβάνει πρόσθετες πληροφορίες σχετικά με τον εμπλουτισμό.</span><span class="sxs-lookup"><span data-stu-id="0bd65-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="0bd65-120">Επιλέξτε έναν εμπλουτισμό για να δείτε τις διαθέσιμες επιλογές.</span><span class="sxs-lookup"><span data-stu-id="0bd65-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="0bd65-121">Εναλλακτικά, μπορείτε να επιλέξετε τα αποσιωπητικά (...) σε ένα στοιχείο λίστας, για να δείτε τις επιλογές.</span><span class="sxs-lookup"><span data-stu-id="0bd65-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Επιλογές για τη διαχείριση των εμπλουτισμών στη λίστα των εμπλουτισμών":::

- <span data-ttu-id="0bd65-123">**Προβολή** λεπτομερειών εμπλουτισμού με τον αριθμό των εμπλουτισμένων προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="0bd65-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="0bd65-124">**Επεξεργαστείτε** τη ρύθμιση παραμέτρων του εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="0bd65-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="0bd65-125">**Εκτελέστε** τον εμπλουτισμό για ενημέρωση των προφίλ πελατών με τα πιο πρόσφατα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="0bd65-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="0bd65-126">**Απενεργοποίηση** ενός υπάρχοντος εμπλουτισμού για να διακόψετε την αυτόματη ανανέωσή του με κάθε προγραμματισμένη ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="0bd65-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="0bd65-127">Τα δεδομένα από την τελευταία επιτυχημένη ανανέωση θα συνεχίσουν να είναι διαθέσιμα.</span><span class="sxs-lookup"><span data-stu-id="0bd65-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="0bd65-128">**Ενεργοποιήστε** έναν ανενεργό εμπλουτισμό για να επανεκκινήσετε την αυτόματη ανανέωση με κάθε προγραμματισμένη ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="0bd65-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="0bd65-129">**Διαγραφή** ενός εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="0bd65-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="0bd65-130">Μπορείτε να εκτελείτε ή να απενεργοποιείτε πολλαπλούς εμπλουτισμούς ταυτόχρονα, επιλέγοντάς τους από τη λίστα.</span><span class="sxs-lookup"><span data-stu-id="0bd65-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="0bd65-131">Οι επιλογές προβολής και επεξεργασίας δεν είναι διαθέσιμες ως μαζικές ενέργειες και λειτουργούν μόνο για έναν εμπλουτισμό κάθε φορά.</span><span class="sxs-lookup"><span data-stu-id="0bd65-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]