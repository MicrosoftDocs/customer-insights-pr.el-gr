---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Marketing
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643773"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="d1a75-103">Σύνδεσμος για το Dynamics 365 Marketing (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="d1a75-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d1a75-104">Χρησιμοποιήστε τα [τμήματα](segments.md) για τη δημιουργία εκστρατειών και την επικοινωνία με συγκεκριμένες ομάδες πελατών με το Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d1a75-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="d1a75-105">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Χρήση τμημάτων από το Dynamics 365 Customer Insights με το Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="d1a75-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="d1a75-106">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="d1a75-106">Prerequisite</span></span>

<span data-ttu-id="d1a75-107">Καρτέλες επαφών [από το Dynamics 365 Marketing που λαμβάνονται με χρήση του Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d1a75-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="d1a75-108">Ρύθμιση παραμέτρων του συνδέσμου για το Marketing</span><span class="sxs-lookup"><span data-stu-id="d1a75-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="d1a75-109">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="d1a75-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d1a75-110">Στην περιοχή **Dynamics 365 Marketing**, επιλέξτε **Ρύθμιση παραμέτρων**.</span><span class="sxs-lookup"><span data-stu-id="d1a75-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="d1a75-111">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="d1a75-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d1a75-112">Καταγράψτε τη διεύθυνση URL του Marketing στο πεδίο **Αποθήκευση διεύθυνσης**.</span><span class="sxs-lookup"><span data-stu-id="d1a75-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="d1a75-113">Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d1a75-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="d1a75-114">Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1a75-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="d1a75-115">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="d1a75-115">Select **Next**.</span></span>

1. <span data-ttu-id="d1a75-116">Επιλέξτε ένα ή περισσότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="d1a75-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="d1a75-117">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="d1a75-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d1a75-118">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="d1a75-118">Export the data</span></span>

<span data-ttu-id="d1a75-119">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d1a75-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d1a75-120">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d1a75-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
