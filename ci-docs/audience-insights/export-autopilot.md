---
title: Εξαγωγή δεδομένων Customer Insights στο Autopilot
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596130"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="093cc-103">Σύνδεση για Autopilot (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="093cc-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="093cc-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στο Autopilot και χρησιμοποιήστε τα για μάρκετινγκ ηλεκτρονικού ταχυδρομείου στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="093cc-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="093cc-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="093cc-105">Prerequisites</span></span>

-   <span data-ttu-id="093cc-106">Έχετε έναν [λογαριασμό Autopilot](https://www.autopilothq.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="093cc-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="093cc-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="093cc-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="093cc-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="093cc-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="093cc-109">Σύνδεση σε Autopilot</span><span class="sxs-lookup"><span data-stu-id="093cc-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="093cc-110">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="093cc-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="093cc-111">Στην περιοχή **Autopilot**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="093cc-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="093cc-112">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="093cc-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Τμήμα παραθύρου ρύθμισης παραμέτρων για σύνδεση Autopilot.":::

1. <span data-ttu-id="093cc-114">Εισαγάγετε το **κλειδί API του Autopilot** [κλειδί API του Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="093cc-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="093cc-115">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="093cc-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="093cc-116">Επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="093cc-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="093cc-117">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="093cc-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="093cc-118">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="093cc-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="093cc-119">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="093cc-119">Configure the connector</span></span>

1. <span data-ttu-id="093cc-120">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="093cc-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="093cc-121">Επαναλάβετε τα ίδια βήματα για άλλα προαιρετικά πεδία, όπως **Όνομα**, **Επώνυμο**.</span><span class="sxs-lookup"><span data-stu-id="093cc-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="093cc-122">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="093cc-122">Select the segments you want to export.</span></span> <span data-ttu-id="093cc-123">**Συνιστούμε ιδιαίτερα να μην εξάγετε περισσότερα από 100.000 προφίλ πελατών συνολικά** στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="093cc-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="093cc-124">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="093cc-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="093cc-125">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="093cc-125">Export the data</span></span>

<span data-ttu-id="093cc-126">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="093cc-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="093cc-127">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="093cc-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="093cc-128">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="093cc-128">Known limitations</span></span>

- <span data-ttu-id="093cc-129">Μπορείτε να εξαγάγετε έως και 100.000 προφίλ συνολικά στο Autopilot.</span><span class="sxs-lookup"><span data-stu-id="093cc-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="093cc-130">Η εξαγωγή στο Autopilot περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="093cc-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="093cc-131">Η εξαγωγή έως και 100.000 προφίλ στο Autopilot μπορεί να διαρκέσει έως και λίγες ώρες για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="093cc-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="093cc-132">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Autopilot εξαρτάται και περιορίζεται στη σύμβασή σας με το Autopilot.</span><span class="sxs-lookup"><span data-stu-id="093cc-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="093cc-133">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="093cc-133">Data privacy and compliance</span></span>

<span data-ttu-id="093cc-134">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Autopilot, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="093cc-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="093cc-135">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Autopilot πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="093cc-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="093cc-136">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="093cc-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="093cc-137">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="093cc-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]