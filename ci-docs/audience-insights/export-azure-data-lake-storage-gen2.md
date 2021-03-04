---
title: Εξαγωγή δεδομένων Customer Insights στο Azure Data Lake Storage Gen2
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477179"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="bf451-103">Σύνδεση για Azure Data Lake Storage Gen2 (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="bf451-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="bf451-104">Αποθηκεύστε τα δεδομένα του Customer Insights στο Azure Data Lake Storage Gen2 ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.</span><span class="sxs-lookup"><span data-stu-id="bf451-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="bf451-105">Ρύθμιση παραμέτρων του συνδέσμου για Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="bf451-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="bf451-106">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="bf451-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bf451-107">Στην περιοχή **Azure Data Lake Storage Gen2**, επιλέξτε **Set up**.</span><span class="sxs-lookup"><span data-stu-id="bf451-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="bf451-108">Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="bf451-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bf451-109">Καταχωρήστε τα **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Περιέκτης** για το δικό σας Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="bf451-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="bf451-110">Για να μάθετε πώς να δημιουργείτε ένα λογαριασμό χώρου αποθήκευσης για χρήση με το Azure Data Lake Storage Gen2, ανατρέξτε στο θέμα [Δημιουργία λογαριασμού χώρου αποθήκευσης](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="bf451-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="bf451-111">Για να μάθετε περισσότερα σχετικά με τον τρόπο εύρεσης του ονόματος λογαριασμού αποθήκευσης Azure Data Lake Storage Gen2 και του κλειδιού λογαριασμού, ανατρέξτε στο θέμα [Διαχείριση ρυθμίσεων λογαριασμού χώρου αποθήκευσης στην πύλη Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bf451-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="bf451-112">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="bf451-112">Select **Next**.</span></span>

1. <span data-ttu-id="bf451-113">Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.</span><span class="sxs-lookup"><span data-stu-id="bf451-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="bf451-114">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="bf451-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bf451-115">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="bf451-115">Export the data</span></span>

<span data-ttu-id="bf451-116">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bf451-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="bf451-117">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bf451-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
