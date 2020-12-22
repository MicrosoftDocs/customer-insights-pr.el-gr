---
title: Εξαγωγή δεδομένων Customer Insights σε ένα χώρο αποθήκευσης αντικειμένων BLOB Azure
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με τον χώρο αποθήκευσης αντικειμένων blob Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667139"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="8c3aa-103">Σύνδεση για χώρο αποθήκευσης αντικειμένων blob Azure (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="8c3aa-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="8c3aa-104">Αποθηκεύστε τα δεδομένα του Customer Insights στον χώρο αποθήκευσης αντικειμένου blob Azure ή χρησιμοποιήστε το για τη μεταφορά των δεδομένων σας σε άλλες εφαρμογές.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="8c3aa-105">Ρύθμιση σύνδεσης για χώρο αποθήκευσης αντικειμένων blob Azure</span><span class="sxs-lookup"><span data-stu-id="8c3aa-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="8c3aa-106">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8c3aa-107">Στην περιοχή **Χώρος αποθήκευσης Azure Blob**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="8c3aa-108">Εισάγετε το **Όνομα λογαριασμού**, το **Κλειδί λογαριασμού** και το **Κοντέινερ** για το λογαριασμό χώρου αποθήκευσης Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="8c3aa-109">Για να μάθετε περισσότερα σχετικά με το πώς μπορείτε να βρείτε το όνομα του λογαριασμού αποθήκευσηςAzure Blob και το κλειδί λογαριασμού, δείτε [Διαχείριση ρυθμίσεων λογαριασμού αποθήκευσης στην πύλη Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="8c3aa-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="8c3aa-110">Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="8c3aa-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="8c3aa-111">Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8c3aa-112">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-112">Select **Next**.</span></span>

1. <span data-ttu-id="8c3aa-113">Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="8c3aa-114">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-114">Select **Save**.</span></span>

<span data-ttu-id="8c3aa-115">Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ χώρου αποθήκευσης αντικειμένων blob Azure που ρυθμίσατε.</span><span class="sxs-lookup"><span data-stu-id="8c3aa-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="8c3aa-116">Οι παρακάτω διαδρομές φακέλων δημιουργούνται αυτόματα στο κοντέινερ που διαθέτετε:</span><span class="sxs-lookup"><span data-stu-id="8c3aa-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="8c3aa-117">Για τις οντότητες προέλευσης και τις οντότητες που δημιουργούνται από το σύστημα: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="8c3aa-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="8c3aa-118">Παράδειγμα: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="8c3aa-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="8c3aa-119">Το model.json για τις οντότητες που έχουν εξαχθεί θα βρίσκεται στο επίπεδο %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="8c3aa-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="8c3aa-120">Παράδειγμα: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="8c3aa-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8c3aa-121">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="8c3aa-121">Export the data</span></span>

<span data-ttu-id="8c3aa-122">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](/export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8c3aa-122">You can [export data on demand](/export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="8c3aa-123">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8c3aa-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
