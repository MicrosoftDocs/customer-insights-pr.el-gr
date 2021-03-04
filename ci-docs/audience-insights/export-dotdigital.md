---
title: Εξαγωγή δεδομένων Customer Insights στο DotDigital
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269100"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="56f0a-103">Σύνδεση για το DotDigital (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="56f0a-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="56f0a-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών σσε βιβλία διευθύνσεων DotDigital και χρησιμοποιήστε τα για εκστρατείες, μάρκετινγκ μέσω ηλεκτρονικού ταχυδρομείου και για να δημιουργήσετε τμήματα πελατών με το DotDigital.</span><span class="sxs-lookup"><span data-stu-id="56f0a-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="56f0a-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="56f0a-105">Prerequisites</span></span>

-   <span data-ttu-id="56f0a-106">Έχετε έναν [λογαριασμό DotDigital](https://dotdigital.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="56f0a-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="56f0a-107">Υπάρχουν υπάρχοντα βιβλία διευθύνσεων στο DotDigital και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="56f0a-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="56f0a-108">Μπορείτε να βρείτε το αναγνωριστικό στη διεύθυνση URL, όταν επιλέγετε και ανοίγετε ένα βιβλίο διευθύνσεων.</span><span class="sxs-lookup"><span data-stu-id="56f0a-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="56f0a-109">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [βιβλία διευθύνσεων DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="56f0a-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="56f0a-110">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="56f0a-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="56f0a-111">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="56f0a-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="56f0a-112">Σύνδεση στο DotDigital</span><span class="sxs-lookup"><span data-stu-id="56f0a-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="56f0a-113">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="56f0a-114">Στο **DotDigital**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="56f0a-115">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Τμήμα παραθύρου ρύθμισης παραμέτρων για εξαγωγή DotDigital.":::

1. <span data-ttu-id="56f0a-117">Πληκτρολογήστε το **όνομα χρήστη και τον κωδικό πρόσβασης DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="56f0a-118">Εισαγάγετε το **[αναγνωριστικό βιβλίου διευθύνσεων του DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="56f0a-119">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="56f0a-120">Επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο DotDigital.</span><span class="sxs-lookup"><span data-stu-id="56f0a-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="56f0a-121">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56f0a-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="56f0a-122">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="56f0a-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="56f0a-123">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="56f0a-123">Configure the connector</span></span>

1. <span data-ttu-id="56f0a-124">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="56f0a-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="56f0a-125">Επαναλάβετε τα ίδια βήματα για άλλα προαιρετικά πεδία, όπως **Όνομα**, **Επώνυμο**, **Ονοματεπώνυμο**, **Φύλο** και **Ταχυδρομικός κώδικας**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="56f0a-126">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="56f0a-126">Select the segments you want to export.</span></span> <span data-ttu-id="56f0a-127">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο DotDigital.</span><span class="sxs-lookup"><span data-stu-id="56f0a-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="56f0a-128">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="56f0a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="56f0a-129">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="56f0a-129">Export the data</span></span>

<span data-ttu-id="56f0a-130">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="56f0a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="56f0a-131">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="56f0a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="56f0a-132">Στο DotDigital, μπορείτε πλέον να βρείτε τα τμήματά σας στα [βιβλία διευθύνσεων του DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="56f0a-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="56f0a-133">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="56f0a-133">Known limitations</span></span>

- <span data-ttu-id="56f0a-134">Έως 1000000 προφίλ ανά εξαγωγή στο DotDigital.</span><span class="sxs-lookup"><span data-stu-id="56f0a-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="56f0a-135">Η εξαγωγή στο DotDigital περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="56f0a-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="56f0a-136">Η εξαγωγή τμημάτων με συνολικά 1 εκατομμύριο προφίλ μπορεί να διαρκέσει έως και τρεις ώρες λόγω περιορισμών από την πλευρά του παρόχου.</span><span class="sxs-lookup"><span data-stu-id="56f0a-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="56f0a-137">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο DotDigital εξαρτάται και περιορίζεται στη σύμβασή σας με το DotDigital.</span><span class="sxs-lookup"><span data-stu-id="56f0a-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="56f0a-138">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="56f0a-138">Data privacy and compliance</span></span>

<span data-ttu-id="56f0a-139">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο DotDigital, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="56f0a-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="56f0a-140">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το DotDigital πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="56f0a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="56f0a-141">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="56f0a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="56f0a-142">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="56f0a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]