---
title: Εμπλουτισμός ενοποιημένων προφίλ πελάτη
description: Χρησιμοποιήστε τις δυνατότητες για να εμπλουτίσετε τα δεδομένα των πελατών σας.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597695"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="ef9d2-103">Εμπλουτισμός για προφίλ πελατών (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="ef9d2-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="ef9d2-104">Χρησιμοποιήστε δεδομένα από προελεύσεις όπως η Microsoft και άλλοι συνεργάτες για τον εμπλουτισμό των δεδομένων των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Σελίδα κέντρου εμπλουτισμού":::

<span data-ttu-id="ef9d2-106">Στις πληροφορίες κοινού, μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** για να εργαστείτε με επιλογές εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="ef9d2-107">Πρέπει να έχετε ρόλο Συμμετέχων ή Διαχειριστής για να δημιουργήσετε ή να επεξεργαστείτε εμπλουτισμούς.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="ef9d2-108">Για περισσότερες πληροφορίες, δείτε [Δικαιώματα](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ef9d2-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="ef9d2-109">Στην καρτέλα **Ανακάλυψη**, θα βρείτε τους παρακάτω εμπλουτισμούς:</span><span class="sxs-lookup"><span data-stu-id="ef9d2-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="ef9d2-110">[Επωνυμίες](enrichment-microsoft-graph.md) που παρέχονται από το Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ef9d2-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="ef9d2-111">[Ενδιαφέροντα](enrichment-microsoft-graph.md) που παρέχονται από το Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ef9d2-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="ef9d2-112">[Εταιρικά δεδομένα](enrichment-leadspace.md) που παρέχονται από το Leadspace</span><span class="sxs-lookup"><span data-stu-id="ef9d2-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="ef9d2-113">[Δημογραφικά στοιχεία](enrichment-experian.md) που παρέχονται από το Experian</span><span class="sxs-lookup"><span data-stu-id="ef9d2-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="ef9d2-114">[Δεδομένα θέσης](enrichment-here.md) παρέχονται από τις τεχνολογίες HERE</span><span class="sxs-lookup"><span data-stu-id="ef9d2-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="ef9d2-115">[Προσαρμοσμένα δεδομένα](enrichment-SFTP-custom-import.md) μέσω πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP)</span><span class="sxs-lookup"><span data-stu-id="ef9d2-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="ef9d2-116">Στην καρτέλα **Οι εμπλουτισμοί μου**, μπορείτε να δείτε τους εμπλουτισμούς που έχετε ρυθμίσει και να επεξεργαστείτε τις ιδιότητές τους.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="ef9d2-117">Διαχείριση υφιστάμενων εμπλουτισμών</span><span class="sxs-lookup"><span data-stu-id="ef9d2-117">Manage existing enrichments</span></span>

<span data-ttu-id="ef9d2-118">Μεταβείτε στην επιλογή **Οι εμπλουτισμοί μου** για να δείτε όλους τους ρυθμισμένους εμπλουτισμούς.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="ef9d2-119">Κάθε εμπλουτισμός απεικονίζεται ως μια γραμμή που περιλαμβάνει πρόσθετες πληροφορίες σχετικά με τον εμπλουτισμό.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="ef9d2-120">Επιλέξτε έναν εμπλουτισμό για να δείτε τις διαθέσιμες επιλογές.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="ef9d2-121">Εναλλακτικά, μπορείτε να επιλέξετε τα αποσιωπητικά (...) σε ένα στοιχείο λίστας, για να δείτε τις επιλογές.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Επιλογές για τη διαχείριση των εμπλουτισμών στη λίστα των εμπλουτισμών":::

- <span data-ttu-id="ef9d2-123">**Προβολή** λεπτομερειών εμπλουτισμού με τον αριθμό των εμπλουτισμένων προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="ef9d2-124">**Επεξεργαστείτε** τη ρύθμιση παραμέτρων του εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="ef9d2-125">**Εκτελέστε** τον εμπλουτισμό για ενημέρωση των προφίλ πελατών με τα πιο πρόσφατα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="ef9d2-126">**Απενεργοποίηση** ενός υπάρχοντος εμπλουτισμού για να διακόψετε την αυτόματη ανανέωσή του με κάθε προγραμματισμένη ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="ef9d2-127">Τα δεδομένα από την τελευταία επιτυχημένη ανανέωση θα συνεχίσουν να είναι διαθέσιμα.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="ef9d2-128">**Ενεργοποιήστε** έναν ανενεργό εμπλουτισμό για να επανεκκινήσετε την αυτόματη ανανέωση με κάθε προγραμματισμένη ανανέωση.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="ef9d2-129">**Διαγραφή** ενός εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="ef9d2-130">Μπορείτε να εκτελείτε ή να απενεργοποιείτε πολλαπλούς εμπλουτισμούς ταυτόχρονα, επιλέγοντάς τους από τη λίστα.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="ef9d2-131">Οι επιλογές προβολής και επεξεργασίας δεν είναι διαθέσιμες ως μαζικές ενέργειες και λειτουργούν μόνο για έναν εμπλουτισμό κάθε φορά.</span><span class="sxs-lookup"><span data-stu-id="ef9d2-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]