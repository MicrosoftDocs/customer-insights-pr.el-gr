---
title: Εξαγωγή δεδομένων Customer Insights στο Marketo
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570403"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="a559b-103">Σύνδεση για Marketo (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="a559b-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="a559b-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών για τη δημιουργία εκστρατειών, την παροχή μάρκετινγκ μέσω ηλεκτρονικού ταχυδρομείου και τη χρήση συγκεκριμένων ομάδων πελατών με το Marketo.</span><span class="sxs-lookup"><span data-stu-id="a559b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a559b-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="a559b-105">Prerequisites</span></span>

-   <span data-ttu-id="a559b-106">Έχετε έναν [λογαριασμό Marketo](https://login.marketo.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="a559b-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a559b-107">Υπάρχουν υπάρχουσες λίστες στο Marketo και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="a559b-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="a559b-108">Για περισσότερες πληροφορίες, ανατρέξτε στις [λίστες Marketplace](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a559b-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="a559b-109">Έχετε [ρυθμίσει τμήματα](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a559b-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a559b-110">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="a559b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="a559b-111">Σύνδεση στο Marketo</span><span class="sxs-lookup"><span data-stu-id="a559b-111">Connect to Marketo</span></span>

1. <span data-ttu-id="a559b-112">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="a559b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a559b-113">Στην περιοχή **Marketo**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="a559b-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="a559b-114">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="a559b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a559b-115">Εισαγάγετε το **[αναγνωριστικό πελάτη Marketo, τον μυστικό κωδικό πελάτη και το όνομα κεντρικού υπολογιστή τελικού σημείου REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="a559b-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="a559b-116">Εισαγάγετε το **[αναγνωριστικό λίστας Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="a559b-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="a559b-117">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε την **Προστασία προσωπικών δεδομένων και τη συμμόρφωση** και επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο Marketo.</span><span class="sxs-lookup"><span data-stu-id="a559b-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="a559b-118">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a559b-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Εξαγωγή στιγμιότυπου οθόνης για σύνδεση Marketo":::

1. <span data-ttu-id="a559b-120">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="a559b-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a559b-121">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="a559b-121">Configure the connector</span></span>

1. <span data-ttu-id="a559b-122">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="a559b-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a559b-123">Προαιρετικά, μπορείτε να εξαγάγετε το **Όνομα**, το **Επώνυμο**, την **Πόλη**, την **Πολιτεία** και τη **Χώρα/περιοχή** ως πρόσθετα πεδία για τη δημιουργία πιο εξατομικευμένων μηνυμάτων ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="a559b-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="a559b-124">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="a559b-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a559b-125">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="a559b-125">Select the segments you want to export.</span></span> <span data-ttu-id="a559b-126">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Marketo.</span><span class="sxs-lookup"><span data-stu-id="a559b-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Επιλέξτε πεδία και τμήματα για εξαγωγή στο Marketo":::

1. <span data-ttu-id="a559b-128">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="a559b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a559b-129">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="a559b-129">Export the data</span></span>

<span data-ttu-id="a559b-130">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a559b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a559b-131">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a559b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a559b-132">Στο Marketo, μπορείτε πλέον να βρείτε τα τμήματά σας στις [λίστες Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a559b-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a559b-133">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="a559b-133">Known limitations</span></span>

- <span data-ttu-id="a559b-134">Έως 1000000 προφίλ ανά εξαγωγή σε Marketo.</span><span class="sxs-lookup"><span data-stu-id="a559b-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="a559b-135">Η εξαγωγή στο Marketo περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="a559b-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="a559b-136">Η εξαγωγή τμημάτων με σύνολο 1000000 προφίλ μπορεί να διαρκέσει έως και 3 ώρες.</span><span class="sxs-lookup"><span data-stu-id="a559b-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="a559b-137">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Marketo εξαρτάται και περιορίζεται στη σύμβασή σας με το Marketo.</span><span class="sxs-lookup"><span data-stu-id="a559b-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a559b-138">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="a559b-138">Data privacy and compliance</span></span>

<span data-ttu-id="a559b-139">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδώσετε δεδομένα στο Marketo, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="a559b-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a559b-140">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Marketo πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="a559b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a559b-141">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a559b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a559b-142">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="a559b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
