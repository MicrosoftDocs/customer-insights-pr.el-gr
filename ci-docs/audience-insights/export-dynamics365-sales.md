---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Sales
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976226"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="9809f-103">Χρήση τμημάτων στο Dynamics 365 Sales (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="9809f-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9809f-104">Χρησιμοποιήστε τα δεδομένα πελατών σας για να δημιουργήσετε λίστες μάρκετινγκ, ροές εργασιών παρακολούθησης και να στείλετε προσφορές με το Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9809f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="9809f-105">Προϋπόθεση για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="9809f-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="9809f-106">Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Sales για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στις Πωλήσεις.</span><span class="sxs-lookup"><span data-stu-id="9809f-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="9809f-107">Διαβάστε περισσότερα σχετικά με το πώς μπορείτε να χρησιμοποιήσετε τις επαφές στο [Dynamics 365 Sales χρησιμοποιώντας το Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9809f-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9809f-108">Η εξαγωγή τμημάτων από τις πληροφορίες κοινού στις Πωλήσεις δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες των Πωλήσεων.</span><span class="sxs-lookup"><span data-stu-id="9809f-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="9809f-109">Οι καρτέλες επαφών από τις Πωλήσεις πρέπει να ενοποιηθούν με τις πληροφορίες κοινού και να χρησιμοποιούνται ως προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="9809f-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9809f-110">Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.</span><span class="sxs-lookup"><span data-stu-id="9809f-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="9809f-111">Ρυθμίστε τη σύνδεση στο Sales</span><span class="sxs-lookup"><span data-stu-id="9809f-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="9809f-112">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="9809f-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9809f-113">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Dynamics 365 Sales** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="9809f-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="9809f-114">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="9809f-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9809f-115">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="9809f-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9809f-116">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="9809f-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9809f-117">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="9809f-117">Choose who can use this connection.</span></span> <span data-ttu-id="9809f-118">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="9809f-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9809f-119">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9809f-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9809f-120">Καταγράψτε τη διεύθυνση URL του οργανισμού Sales σας στο πεδίο **Αποθήκευση διεύθυνσης**.</span><span class="sxs-lookup"><span data-stu-id="9809f-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9809f-121">Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9809f-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="9809f-122">Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9809f-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9809f-123">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="9809f-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="9809f-124">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="9809f-124">Configure an export</span></span>

<span data-ttu-id="9809f-125">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="9809f-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9809f-126">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9809f-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9809f-127">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="9809f-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9809f-128">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="9809f-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9809f-129">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9809f-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="9809f-130">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="9809f-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9809f-131">Επιλέξτε ένα ή περισσότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="9809f-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="9809f-132">\`Επιλέξτε **Αποθήκευση**</span><span class="sxs-lookup"><span data-stu-id="9809f-132">Select **Save**</span></span>

<span data-ttu-id="9809f-133">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="9809f-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9809f-134">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9809f-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9809f-135">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9809f-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
