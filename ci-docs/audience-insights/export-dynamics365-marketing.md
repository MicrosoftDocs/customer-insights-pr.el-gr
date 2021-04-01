---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Marketing
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597603"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c337a-103">Σύνδεσμος για το Dynamics 365 Marketing (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="c337a-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c337a-104">Χρησιμοποιήστε τα [τμήματα](segments.md) για τη δημιουργία εκστρατειών και την επικοινωνία με συγκεκριμένες ομάδες πελατών με το Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c337a-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c337a-105">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Χρήση τμημάτων από το Dynamics 365 Customer Insights με το Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="c337a-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c337a-106">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="c337a-106">Prerequisite</span></span>

- <span data-ttu-id="c337a-107">Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Marketing για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στο Marketing.</span><span class="sxs-lookup"><span data-stu-id="c337a-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="c337a-108">Διαβάστε περισσότερα σχετικά με το πώς μπορείτε να ενσωματώσετε τις επαφές στο [Dynamics 365 Marketing χρησιμοποιώντας το Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c337a-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c337a-109">Η εξαγωγή τμημάτων από τις πληροφορίες κοινού στο Marketing δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες του Marketing.</span><span class="sxs-lookup"><span data-stu-id="c337a-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="c337a-110">Οι καρτέλες επαφών από το Marketing πρέπει να ενοποιηθούν με τις πληροφορίες κοινού και να χρησιμοποιούνται ως προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="c337a-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="c337a-111">Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.</span><span class="sxs-lookup"><span data-stu-id="c337a-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c337a-112">Ρύθμιση παραμέτρων του συνδέσμου για το Marketing</span><span class="sxs-lookup"><span data-stu-id="c337a-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c337a-113">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="c337a-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c337a-114">Στην περιοχή **Dynamics 365 Marketing**, επιλέξτε **Ρύθμιση παραμέτρων**.</span><span class="sxs-lookup"><span data-stu-id="c337a-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c337a-115">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="c337a-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c337a-116">Καταγράψτε τη διεύθυνση URL του Marketing στο πεδίο **Αποθήκευση διεύθυνσης**.</span><span class="sxs-lookup"><span data-stu-id="c337a-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c337a-117">Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c337a-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c337a-118">Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c337a-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c337a-119">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="c337a-119">Select **Next**.</span></span>

1. <span data-ttu-id="c337a-120">Επιλέξτε ένα ή περισσότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="c337a-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="c337a-121">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="c337a-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c337a-122">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="c337a-122">Export the data</span></span>

<span data-ttu-id="c337a-123">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c337a-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c337a-124">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c337a-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]