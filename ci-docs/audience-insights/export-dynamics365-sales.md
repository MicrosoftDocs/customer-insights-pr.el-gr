---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Sales
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643818"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="95b9f-103">Σύνδεσμος για το Dynamics 365 Sales (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="95b9f-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="95b9f-104">Χρησιμοποιήστε τα δεδομένα πελατών σας για να δημιουργήσετε λίστες μάρκετινγκ, ροές εργασιών παρακολούθησης και να στείλετε προσφορές με το Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="95b9f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="95b9f-105">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="95b9f-105">Prerequisite</span></span>

<span data-ttu-id="95b9f-106">Καρτέλες επαφών [από το Dynamics 365 Sales που λαμβάνονται με χρήση του Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="95b9f-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="95b9f-107">Ρύθμιση παραμέτρων του συνδέσμου για το Sales</span><span class="sxs-lookup"><span data-stu-id="95b9f-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="95b9f-108">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="95b9f-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="95b9f-109">Στην περιοχή **Dynamics 365 Sales**, επιλέξτε **Ρύθμιση παραμέτρων**.</span><span class="sxs-lookup"><span data-stu-id="95b9f-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="95b9f-110">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="95b9f-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="95b9f-111">Καταγράψτε τη διεύθυνση URL του οργανισμού Sales σας στο πεδίο **Αποθήκευση διεύθυνσης**.</span><span class="sxs-lookup"><span data-stu-id="95b9f-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="95b9f-112">Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="95b9f-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="95b9f-113">Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="95b9f-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="95b9f-114">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="95b9f-114">Select **Next**.</span></span>

1. <span data-ttu-id="95b9f-115">Επιλέξτε ένα ή περισσότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="95b9f-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="95b9f-116">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="95b9f-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="95b9f-117">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="95b9f-117">Export the data</span></span>

<span data-ttu-id="95b9f-118">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="95b9f-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="95b9f-119">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="95b9f-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
