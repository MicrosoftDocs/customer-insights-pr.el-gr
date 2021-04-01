---
title: Εξαγωγή δεδομένων Customer Insights στο AdRoll
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697074"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="84c39-103">Σύνδεση για AdRoll (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="84c39-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="84c39-104">Εξαγάγετε τμήματα των ενοποιημένων προφίλ πελατών στο AdRoll και χρησιμοποιήστε τα για διαφημίσεις.</span><span class="sxs-lookup"><span data-stu-id="84c39-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="84c39-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="84c39-105">Prerequisites</span></span>

-   <span data-ttu-id="84c39-106">Έχετε έναν [λογαριασμό AdRoll](https://www.adroll.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="84c39-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="84c39-107">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="84c39-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="84c39-108">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="84c39-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="84c39-109">Σύνδεση στο AdRoll</span><span class="sxs-lookup"><span data-stu-id="84c39-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="84c39-110">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="84c39-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="84c39-111">Στην περιοχή **AdRoll**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="84c39-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="84c39-112">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="84c39-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Τμήμα παραθύρου ρύθμισης παραμέτρων για σύνδεση AdRoll.":::

1. <span data-ttu-id="84c39-114">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="84c39-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="84c39-115">Επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84c39-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="84c39-116">Επιλέξτε **Έλεγχος ταυτότητας με το AdRoll** και δώστε στον διαχειριστή σας τα διαπιστευτήρια για το AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84c39-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="84c39-117">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84c39-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="84c39-118">Πληκτρολογήστε το **Αναγνωριστικό διαφημιστή AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="84c39-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="84c39-119">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="84c39-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="84c39-120">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="84c39-120">Configure the connector</span></span>

1. <span data-ttu-id="84c39-121">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="84c39-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="84c39-122">Είναι υποχρεωτικό να εξαγάγετε τμήματα στο AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84c39-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="84c39-123">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="84c39-123">Select the segments you want to export.</span></span> <span data-ttu-id="84c39-124">Επιλέξτε ένα τμήμα με τουλάχιστον 100 μέλη.</span><span class="sxs-lookup"><span data-stu-id="84c39-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="84c39-125">Δεν μπορείτε να εξαγάγετε μικρότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="84c39-125">You can't export smaller segments.</span></span> <span data-ttu-id="84c39-126">Επιπλέον, το μέγιστο μέγεθος ενός τμήματος προς εξαγωγή είναι 250.000 μέλη ανά εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="84c39-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="84c39-127">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="84c39-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="84c39-128">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="84c39-128">Export the data</span></span>

<span data-ttu-id="84c39-129">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="84c39-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="84c39-130">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="84c39-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="84c39-131">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="84c39-131">Known limitations</span></span>

- <span data-ttu-id="84c39-132">Μπορείτε να εξαγάγετε έως και 250.000 προφίλ ανά εξαγωγή στο AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84c39-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="84c39-133">Δεν μπορείτε να εξαγάγετε τμήματα με λιγότερα από 100 προφίλ στο AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84c39-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="84c39-134">Η εξαγωγή στο AdRoll περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="84c39-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="84c39-135">Για την εξαγωγή έως 250.000 προφίλ στο AdRoll μπορείτε να ολοκληρώσετε έως και 10 λεπτά.</span><span class="sxs-lookup"><span data-stu-id="84c39-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="84c39-136">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο AdRoll εξαρτάται και περιορίζεται στη σύμβασή σας με το AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84c39-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84c39-137">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="84c39-137">Data privacy and compliance</span></span>

<span data-ttu-id="84c39-138">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο AdRoll, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="84c39-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84c39-139">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το AdRoll πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="84c39-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="84c39-140">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84c39-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="84c39-141">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="84c39-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
