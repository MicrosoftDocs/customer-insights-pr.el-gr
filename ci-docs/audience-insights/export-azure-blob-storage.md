---
title: Εξαγωγή δεδομένων Customer Insights σε έναν χώρο αποθήκευσης αντικειμένων blob Azure
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής σε χώρο αποθήκευσης blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760189"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="dda4d-103">Εξαγωγή λίστας τμημάτων και άλλων δεδομένων στον χώρο αποθήκευσης αντικειμένων blob Azure (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="dda4d-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="dda4d-104">Αποθηκεύστε τα δεδομένα του Customer Insights σε έναν χώρο αποθήκευσης αντικειμένου blob ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.</span><span class="sxs-lookup"><span data-stu-id="dda4d-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="dda4d-105">Ρυθμίστε τη σύνδεση στον χώρου αποθήκευσης αντικειμένων blob</span><span class="sxs-lookup"><span data-stu-id="dda4d-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="dda4d-106">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="dda4d-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dda4d-107">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Χώρος αποθήκευσης αντικειμένων blob Azure** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="dda4d-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="dda4d-108">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="dda4d-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dda4d-109">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="dda4d-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dda4d-110">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="dda4d-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dda4d-111">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="dda4d-111">Choose who can use this connection.</span></span> <span data-ttu-id="dda4d-112">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="dda4d-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dda4d-113">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dda4d-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dda4d-114">Εισαγάγετε το **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Κοντέινερ** για τον λογαριασμό του χώρου αποθήκευσης αντικειμένων blob.</span><span class="sxs-lookup"><span data-stu-id="dda4d-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="dda4d-115">Για να μάθετε περισσότερα σχετικά με τον τρόπο εύρεσης του ονόματος λογαριασμού και του κλειδιού λογαριασμού χώρου αποθήκευσης αντικειμένων Blob, ανατρέξτε στο θέμα [Διαχείριση ρυθμίσεων λογαριασμών χώρου αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="dda4d-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="dda4d-116">Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="dda4d-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="dda4d-117">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="dda4d-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="dda4d-118">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="dda4d-118">Configure an export</span></span>

<span data-ttu-id="dda4d-119">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="dda4d-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dda4d-120">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dda4d-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dda4d-121">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="dda4d-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dda4d-122">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="dda4d-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dda4d-123">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα χώρος αποθήκευσης αντικειμένων blob Azure.</span><span class="sxs-lookup"><span data-stu-id="dda4d-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="dda4d-124">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="dda4d-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dda4d-125">Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.</span><span class="sxs-lookup"><span data-stu-id="dda4d-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="dda4d-126">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="dda4d-126">Select **Save**.</span></span>

<span data-ttu-id="dda4d-127">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="dda4d-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dda4d-128">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dda4d-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="dda4d-129">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dda4d-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="dda4d-130">Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ χώρου αποθήκευσης αντικειμένων Blob που ρυθμίσατε.</span><span class="sxs-lookup"><span data-stu-id="dda4d-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="dda4d-131">Οι παρακάτω διαδρομές φακέλων δημιουργούνται αυτόματα στο κοντέινερ που διαθέτετε:</span><span class="sxs-lookup"><span data-stu-id="dda4d-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="dda4d-132">Για τις οντότητες προέλευσης και τις οντότητες που δημιουργούνται από το σύστημα: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="dda4d-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="dda4d-133">Παράδειγμα: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="dda4d-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="dda4d-134">Το model.json για τις οντότητες που έχουν εξαχθεί θα βρίσκεται στο επίπεδο %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="dda4d-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="dda4d-135">Παράδειγμα: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="dda4d-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
