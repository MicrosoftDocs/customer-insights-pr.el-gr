---
title: Εξαγωγή δεδομένων Customer Insights στο Azure Data Lake Storage Gen2
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760051"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="3a7d0-103">Ρυθμίστε τη σύνδεση στο Azure Data Lake Storage Gen2 (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="3a7d0-104">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3a7d0-105">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Azure Data Lake Gen 2** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="3a7d0-106">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3a7d0-107">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3a7d0-108">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3a7d0-109">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-109">Choose who can use this connection.</span></span> <span data-ttu-id="3a7d0-110">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3a7d0-111">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3a7d0-112">Καταχωρήστε τα **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Περιέκτης** για το δικό σας Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="3a7d0-113">Για να μάθετε πώς να δημιουργείτε ένα λογαριασμό χώρου αποθήκευσης για χρήση με το Azure Data Lake Storage Gen2, ανατρέξτε στο θέμα [Δημιουργία λογαριασμού χώρου αποθήκευσης](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="3a7d0-114">Για να μάθετε περισσότερα σχετικά με το όνομα λογαριασμού και το κλειδί λογαριασμού χώρου αποθήκευσης Azure Data Lake Gen 2, ανατρέξτε στο θέμα [Διαχείριση ρυθμίσεων λογαριασμών χώρου αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="3a7d0-115">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="3a7d0-116">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="3a7d0-116">Configure an export</span></span>

<span data-ttu-id="3a7d0-117">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3a7d0-118">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3a7d0-119">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3a7d0-120">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη εξαγωγής**.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="3a7d0-121">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="3a7d0-122">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3a7d0-123">Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="3a7d0-124">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-124">Select **Save**.</span></span>

<span data-ttu-id="3a7d0-125">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3a7d0-126">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3a7d0-127">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="3a7d0-128">Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ χώρου αποθήκευσης Azure Data Lake Gen 2 που ρυθμίσατε.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
