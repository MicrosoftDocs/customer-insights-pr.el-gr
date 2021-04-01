---
title: Εξαγωγή δεδομένων Customer Insights στο Mailchimp
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598201"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="5c26f-103">Σύνδεση για Mailchimp (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="5c26f-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="5c26f-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στο Mailchimp για να δημιουργήσετε ενημερωτικά δελτία και εκστρατείες ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="5c26f-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5c26f-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="5c26f-105">Prerequisites</span></span>

-   <span data-ttu-id="5c26f-106">Έχετε έναν [λογαριασμό Mailchimp](https://mailchimp.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="5c26f-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5c26f-107">Υπάρχουν υπάρχοντα κοινά στο Mailchimp και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="5c26f-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="5c26f-108">Για περισσότερες πληροφορίες, ανατρέξτε στα [ακροατήρια Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="5c26f-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="5c26f-109">Έχετε [ρυθμίσει τμήματα](segments.md)</span><span class="sxs-lookup"><span data-stu-id="5c26f-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="5c26f-110">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="5c26f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="5c26f-111">Σύνδεση στο MailChimp</span><span class="sxs-lookup"><span data-stu-id="5c26f-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="5c26f-112">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="5c26f-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5c26f-113">Στην περιοχή **Mailchimp**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="5c26f-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="5c26f-114">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="5c26f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5c26f-115">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="5c26f-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5c26f-116">Πληκτρολογήστε το **[αναγνωριστικό κοινού Mailchimp](https://mailchimp.com/help/find-audience-id/)** και επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση με το Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="5c26f-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="5c26f-117">Επιλέξτε **Έλεγχος ταυτότητας με Mailchimp** και δώστε τα διαπιστευτήρια Mailchimp σας.</span><span class="sxs-lookup"><span data-stu-id="5c26f-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="5c26f-118">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5c26f-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Εξαγωγή στιγμιότυπου οθόνης για σύνδεση Mailchimp":::

1. <span data-ttu-id="5c26f-120">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="5c26f-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5c26f-121">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="5c26f-121">Configure the connector</span></span>

1. <span data-ttu-id="5c26f-122">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="5c26f-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="5c26f-123">Προαιρετικά, μπορείτε να εξαγάγετε το **Όνομα** και το **Επώνυμο** ως πρόσθετα πεδία για τη δημιουργία πιο εξατομικευμένων μηνυμάτων ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="5c26f-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="5c26f-124">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε αυτά τα πεδία.</span><span class="sxs-lookup"><span data-stu-id="5c26f-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="5c26f-125">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="5c26f-125">Select the segments you want to export.</span></span> <span data-ttu-id="5c26f-126">Μπορείτε να εξαγάγετε έως και 1000000 προφίλ πελατών συνολικά στο Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="5c26f-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Επιλέξτε πεδία και τμήματα για εξαγωγή στο Mailchimp":::

1. <span data-ttu-id="5c26f-128">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="5c26f-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5c26f-129">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="5c26f-129">Export the data</span></span>

<span data-ttu-id="5c26f-130">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5c26f-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5c26f-131">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5c26f-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5c26f-132">Στο Mailchimp, μπορείτε πλέον να βρείτε τα τμήματά σας στα [ακροατήρια Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="5c26f-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5c26f-133">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="5c26f-133">Known limitations</span></span>

- <span data-ttu-id="5c26f-134">Έως 1000000 προφίλ ανά εξαγωγή σε Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="5c26f-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="5c26f-135">Η εξαγωγή στο Mailchimp περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="5c26f-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="5c26f-136">Η εξαγωγή τμημάτων με συνολικά 1 εκατομμύριο προφίλ μπορεί να διαρκέσει έως και τρεις ώρες λόγω περιορισμών από την πλευρά του παρόχου.</span><span class="sxs-lookup"><span data-stu-id="5c26f-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="5c26f-137">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο Mailchimp εξαρτάται και περιορίζεται στη σύμβασή σας με το Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="5c26f-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5c26f-138">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="5c26f-138">Data privacy and compliance</span></span>

<span data-ttu-id="5c26f-139">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Mailchimp, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="5c26f-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5c26f-140">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Mailchimp πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="5c26f-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5c26f-141">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5c26f-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5c26f-142">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="5c26f-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]