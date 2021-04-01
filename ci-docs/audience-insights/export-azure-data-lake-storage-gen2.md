---
title: Εξαγωγή δεδομένων Customer Insights στο Azure Data Lake Storage Gen2
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596637"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="57167-103">Σύνδεση για Azure Data Lake Storage Gen2 (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="57167-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="57167-104">Αποθηκεύστε τα δεδομένα του Customer Insights στο Azure Data Lake Storage Gen2 ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.</span><span class="sxs-lookup"><span data-stu-id="57167-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="57167-105">Ρύθμιση παραμέτρων του συνδέσμου για Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="57167-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="57167-106">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="57167-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="57167-107">Στην περιοχή **Azure Data Lake Storage Gen2**, επιλέξτε **Set up**.</span><span class="sxs-lookup"><span data-stu-id="57167-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="57167-108">Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="57167-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="57167-109">Καταχωρήστε τα **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Περιέκτης** για το δικό σας Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="57167-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="57167-110">Για να μάθετε πώς να δημιουργείτε ένα λογαριασμό χώρου αποθήκευσης για χρήση με το Azure Data Lake Storage Gen2, ανατρέξτε στο θέμα [Δημιουργία λογαριασμού χώρου αποθήκευσης](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="57167-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="57167-111">Για να μάθετε περισσότερα σχετικά με τον τρόπο εύρεσης του ονόματος λογαριασμού αποθήκευσης Azure Data Lake Storage Gen2 και του κλειδιού λογαριασμού, ανατρέξτε στο θέμα [Διαχείριση ρυθμίσεων λογαριασμού χώρου αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="57167-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="57167-112">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="57167-112">Select **Next**.</span></span>

1. <span data-ttu-id="57167-113">Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.</span><span class="sxs-lookup"><span data-stu-id="57167-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="57167-114">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="57167-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="57167-115">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="57167-115">Export the data</span></span>

<span data-ttu-id="57167-116">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="57167-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="57167-117">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57167-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>