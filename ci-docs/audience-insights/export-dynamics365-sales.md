---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Sales
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269008"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="9dcc3-103">Σύνδεσμος για το Dynamics 365 Sales (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="9dcc3-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9dcc3-104">Χρησιμοποιήστε τα δεδομένα πελατών σας για να δημιουργήσετε λίστες μάρκετινγκ, ροές εργασιών παρακολούθησης και να στείλετε προσφορές με το Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="9dcc3-105">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="9dcc3-105">Prerequisite</span></span>

1. <span data-ttu-id="9dcc3-106">Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Sales για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στις Πωλήσεις.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="9dcc3-107">Διαβάστε περισσότερα σχετικά με το πώς μπορείτε να χρησιμοποιήσετε τις επαφές στο [Dynamics 365 Sales χρησιμοποιώντας το Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9dcc3-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9dcc3-108">Η εξαγωγή τμημάτων από τις πληροφορίες κοινού στις Πωλήσεις δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες των Πωλήσεων.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="9dcc3-109">Οι καρτέλες επαφών από τις Πωλήσεις πρέπει να ενοποιηθούν με τις πληροφορίες κοινού και να χρησιμοποιούνται ως προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9dcc3-110">Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="9dcc3-111">Ρύθμιση παραμέτρων του συνδέσμου για το Sales</span><span class="sxs-lookup"><span data-stu-id="9dcc3-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="9dcc3-112">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9dcc3-113">Στην περιοχή **Dynamics 365 Sales**, επιλέξτε **Ρύθμιση παραμέτρων**.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="9dcc3-114">Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9dcc3-115">Καταγράψτε τη διεύθυνση URL του οργανισμού Sales σας στο πεδίο **Αποθήκευση διεύθυνσης**.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9dcc3-116">Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="9dcc3-117">Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9dcc3-118">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-118">Select **Next**.</span></span>

1. <span data-ttu-id="9dcc3-119">Επιλέξτε ένα ή περισσότερα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="9dcc3-120">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="9dcc3-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9dcc3-121">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="9dcc3-121">Export the data</span></span>

<span data-ttu-id="9dcc3-122">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9dcc3-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9dcc3-123">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9dcc3-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]