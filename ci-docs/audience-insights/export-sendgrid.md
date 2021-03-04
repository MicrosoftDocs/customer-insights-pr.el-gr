---
title: Εξαγωγή δεδομένων Customer Insights στο SendGrid
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268732"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="01c3d-103">Σύνδεση για SendGrid (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="01c3d-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="01c3d-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών σε λίστες επαφών SendGrid και χρησιμοποιήστε τα για εκστρατείες και μάρκετινγκ ηλεκτρονικού ταχυδρομείου στο SendGrid.</span><span class="sxs-lookup"><span data-stu-id="01c3d-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="01c3d-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="01c3d-105">Prerequisites</span></span>

-   <span data-ttu-id="01c3d-106">Έχετε έναν [λογαριασμό SendGrid](https://sendgrid.com/) και αντίστοιχα διαπιστευτήρια διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="01c3d-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="01c3d-107">Υπάρχουν υπάρχουσες λίστες επαφών στο SendGrid και στα αντίστοιχα αναγνωριστικά.</span><span class="sxs-lookup"><span data-stu-id="01c3d-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="01c3d-108">Για περισσότερες πληροφορίες, ανατρέξτε στο [SendGrid - Διαχείριση επαφών](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="01c3d-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="01c3d-109">Διαθέτετε [ρυθμισμένα τμήματα](segments.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="01c3d-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="01c3d-110">Τα ενοποιημένα προφίλ πελατών στα εξαγόμενα τμήματα περιέχουν ένα πεδίο που αντιπροσωπεύει μια διεύθυνση ηλεκτρονικού ταχυδρομείου.</span><span class="sxs-lookup"><span data-stu-id="01c3d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="01c3d-111">Σύνδεση στο SendGrid</span><span class="sxs-lookup"><span data-stu-id="01c3d-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="01c3d-112">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="01c3d-113">Στην περιοχή **SendGrid**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="01c3d-114">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Παράθυρο ρύθμισης παραμέτρων εξαγωγής SendGrid.":::

1. <span data-ttu-id="01c3d-116">Εισαγάγετε το **κλειδί SendGrid API** [κλειδί SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="01c3d-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="01c3d-117">Εισαγάγετε το **[αναγνωριστικό λίστας SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="01c3d-118">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="01c3d-119">Επιλέξτε **Σύνδεση** για να προετοιμάσετε τη σύνδεση στο SendGrid.</span><span class="sxs-lookup"><span data-stu-id="01c3d-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="01c3d-120">Επιλέξτε **Προσθήκη ιδίου ως χρήστη εξαγωγής** και δώστε τα διαπιστευτήρια του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="01c3d-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="01c3d-121">Επιλέξτε **Επόμενο** για να ρυθμίσετε τις παραμέτρους της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="01c3d-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="01c3d-122">Ρυθμίστε τις παραμέτρους της σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="01c3d-122">Configure the connector</span></span>

1. <span data-ttu-id="01c3d-123">Στην ενότητα **Αντιστοίχιση δεδομένων**, στο πεδίο **Ηλεκτρονικό ταχυδρομείο**, επιλέξτε το πεδίο στο ενοποιημένο προφίλ πελάτη που αντιπροσωπεύει τη διεύθυνση ηλεκτρονικού ταχυδρομείου ενός πελάτη.</span><span class="sxs-lookup"><span data-stu-id="01c3d-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="01c3d-124">Επαναλάβετε τα ίδια βήματα για άλλα προαιρετικά πεδία, όπως **Όνομα**, **Επώνυμο**, **Χώρα /περιοχή**, **Πολιτεία**, **Πόλη** και **Ταχυδρομικός κώδικας**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="01c3d-125">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="01c3d-125">Select the segments you want to export.</span></span> <span data-ttu-id="01c3d-126">Συνιστούμε ιδιαίτερα **να μην εξάγετε περισσότερα από 100.000 προφίλ πελατών συνολικά** στο SendGrid.</span><span class="sxs-lookup"><span data-stu-id="01c3d-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="01c3d-127">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="01c3d-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="01c3d-128">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="01c3d-128">Export the data</span></span>

<span data-ttu-id="01c3d-129">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="01c3d-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="01c3d-130">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01c3d-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="01c3d-131">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="01c3d-131">Known limitations</span></span>

- <span data-ttu-id="01c3d-132">Έως 100.000 προφίλ συνολικά στο SendGrid.</span><span class="sxs-lookup"><span data-stu-id="01c3d-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="01c3d-133">Η εξαγωγή στο SendGrid περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="01c3d-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="01c3d-134">Η εξαγωγή έως και 100.000 προφίλ στο SendGrid μπορεί να διαρκέσει έως και λίγες ώρες για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="01c3d-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="01c3d-135">Ο αριθμός των προφίλ που μπορείτε να εξαγάγετε στο SendGrid εξαρτάται και περιορίζεται στη σύμβασή σας με το SendGrid.</span><span class="sxs-lookup"><span data-stu-id="01c3d-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="01c3d-136">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="01c3d-136">Data privacy and compliance</span></span>

<span data-ttu-id="01c3d-137">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο SendGrid, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="01c3d-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="01c3d-138">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το SendGrid πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="01c3d-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="01c3d-139">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="01c3d-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="01c3d-140">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="01c3d-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]