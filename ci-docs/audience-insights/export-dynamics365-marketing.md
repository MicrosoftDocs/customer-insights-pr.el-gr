---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Marketing
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759637"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="634cc-103">Χρήση τμημάτων στο Dynamics 365 Marketing (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="634cc-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="634cc-104">Χρησιμοποιήστε τα [τμήματα](segments.md) για τη δημιουργία εκστρατειών και την επικοινωνία με συγκεκριμένες ομάδες πελατών με το Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="634cc-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="634cc-105">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Χρήση τμημάτων από το Dynamics 365 Customer Insights με το Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="634cc-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="634cc-106">Προϋπόθεση για μια σύνδεση</span><span class="sxs-lookup"><span data-stu-id="634cc-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="634cc-107">Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Marketing για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στο Marketing.</span><span class="sxs-lookup"><span data-stu-id="634cc-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="634cc-108">Διαβάστε περισσότερα σχετικά με το πώς μπορείτε να ενσωματώσετε τις επαφές στο [Dynamics 365 Marketing χρησιμοποιώντας το Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="634cc-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="634cc-109">Η εξαγωγή τμημάτων από τις πληροφορίες κοινού στο Marketing δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες του Marketing.</span><span class="sxs-lookup"><span data-stu-id="634cc-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="634cc-110">Οι καρτέλες επαφών από το Marketing πρέπει να ενοποιηθούν με τις πληροφορίες κοινού και να χρησιμοποιούνται ως προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="634cc-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="634cc-111">Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.</span><span class="sxs-lookup"><span data-stu-id="634cc-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="634cc-112">Ρύθμιση σύνδεσης στο Marketing</span><span class="sxs-lookup"><span data-stu-id="634cc-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="634cc-113">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="634cc-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="634cc-114">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Dynamics 365 Marketing** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="634cc-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="634cc-115">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="634cc-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="634cc-116">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="634cc-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="634cc-117">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="634cc-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="634cc-118">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="634cc-118">Choose who can use this connection.</span></span> <span data-ttu-id="634cc-119">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="634cc-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="634cc-120">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="634cc-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="634cc-121">Καταγράψτε τη διεύθυνση URL του Marketing στο πεδίο **Αποθήκευση διεύθυνσης**.</span><span class="sxs-lookup"><span data-stu-id="634cc-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="634cc-122">Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="634cc-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="634cc-123">Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="634cc-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="634cc-124">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="634cc-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="634cc-125">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="634cc-125">Configure an export</span></span>

<span data-ttu-id="634cc-126">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="634cc-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="634cc-127">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="634cc-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="634cc-128">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="634cc-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="634cc-129">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="634cc-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="634cc-130">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="634cc-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="634cc-131">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="634cc-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="634cc-132">Επιλέξτε ένα ή περισσότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="634cc-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="634cc-133">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="634cc-133">Select **Save**.</span></span>

<span data-ttu-id="634cc-134">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="634cc-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="634cc-135">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="634cc-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="634cc-136">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="634cc-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
