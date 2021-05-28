---
title: Εξαγωγή δεδομένων του Customer Insights στο Azure Synapse Analytics
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977377"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="22f6b-103">Εξαγωγή δεδομένων σε Azure Synapse Analytics (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="22f6b-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="22f6b-104">Το Azure Synapse είναι μια υπηρεσία ανάλυσης που επιταχύνει το χρόνο λήψης πληροφοριών σε αποθήκες δεδομένων και συστήματα μαζικών δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="22f6b-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="22f6b-105">Μπορείτε να συγκεντρώνετε και να χρησιμοποιείτε δεδομένα του Customer Insights στο [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="22f6b-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22f6b-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="22f6b-106">Prerequisites</span></span>

<span data-ttu-id="22f6b-107">Πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις για τη ρύθμιση παραμέτρων της σύνδεσης από το Customer Insights στο Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="22f6b-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="22f6b-108">Φροντίστε να ορίσετε όλες τις **αντιστοιχίσεις ρόλων** όπως περιγράφεται.</span><span class="sxs-lookup"><span data-stu-id="22f6b-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="22f6b-109">Προϋποθέσεις στο Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22f6b-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="22f6b-110">Έχετε τον ρόλο **Διαχειριστή** στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="22f6b-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="22f6b-111">Μάθετε περισσότερα σχετικά με τον [ορισμό δικαιωμάτων χρήστη σε πληροφορίες κοινού](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="22f6b-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="22f6b-112">Στο Azure:</span><span class="sxs-lookup"><span data-stu-id="22f6b-112">In Azure:</span></span> 

- <span data-ttu-id="22f6b-113">Μια ενεργή συνδρομή Azure.</span><span class="sxs-lookup"><span data-stu-id="22f6b-113">An active Azure subscription.</span></span>

- <span data-ttu-id="22f6b-114">Εάν χρησιμοποιείτε ένα νέο λογαριασμό Azure Data Lake Storage Gen2, η *κύρια υπηρεσία για πληροφορίες κοινού* χρειάζεται δικαιώματα **συμβαλλόντος δεδομένων BLOB αποθήκευσης**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="22f6b-115">Μάθετε περισσότερα σχετικά με τη [σύνδεση σε λογαριασμό Azure Data Lake Storage Gen2 με την κύρια υπηρεσία Azure για πληροφορίες κοινού](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="22f6b-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="22f6b-116">Το Data Lake Storage Gen2 **πρέπει να έχει ενεργοποιημένο τον** [ιεραρχικό χώρο ονομάτων](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="22f6b-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="22f6b-117">Στην ομάδα πόρων βρίσκεται ο χώρος εργασίας Azure Synapse, στην *κύρια υπηρεσία* και στον *χρήστη για πληροφορίες κοινού* πρέπει να εκχωρηθούν τουλάχιστον δικαιώματα **Αναγνώστη**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="22f6b-118">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Εκχώρηση ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="22f6b-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="22f6b-119">Ο *χρήστης* χρειάζεται δικαιώματα **Συμβαλλόντος δεδομένων BLOB αποθήκευσης** στον λογαριασμό Azure Data Lake Storage Gen2 όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="22f6b-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="22f6b-120">Μάθετε περισσότερα σχετικά με [τη χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="22f6b-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="22f6b-121">Η *[διαχειριζόμενη ταυτότητα χώρου εργασίας Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* χρειάζεται δικαιώματα **χρειάζεται δικαιώματα** στο λογαριασμό Azure Data Lake Storage Gen2όπου τα δεδομένα βρίσκονται και συνδέονται με τον χώρο εργασίας Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="22f6b-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="22f6b-122">Μάθετε περισσότερα σχετικά για τη [χρήση της πύλης Azure για την εκχώρηση ενός ρόλου Azure για πρόσβαση σε δεδομένα blob και ουράς](/azure/storage/common/storage-auth-aad-rbac-portal) και [δικαιώματα συμμετέχοντα δεδομένων blob αποθήκευσης ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="22f6b-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="22f6b-123">Στον χώρο εργασίας Azure Synapse, η *κύρια υπηρεσία για πληροφορίες κοινού* χρειάζεται να ανατεθεί ο ρόλος **Διαχειριστής Synapse**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="22f6b-124">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Τρόπος ρύθμισης ελέγχου πρόσβασης για το χώρο εργασίας Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="22f6b-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="22f6b-125">Ρυθμίστε τη σύνδεση και κάντε εξαγωγή στο Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="22f6b-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="22f6b-126">Ρύθμιση παραμέτρων μιας σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="22f6b-126">Configure a connection</span></span>

1. <span data-ttu-id="22f6b-127">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="22f6b-128">Επιλέξτε **Προσθήκη σύνδεσης** κι επιλέξτε **Azure Synapse Analytics** ή επιλέξτε **Ρύθμιση** στο πλακίδιο **Azure Synapse Analytics** για τη ρύθμιση παραμέτρων της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="22f6b-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="22f6b-129">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο Εμφανιζόμενο όνομα.</span><span class="sxs-lookup"><span data-stu-id="22f6b-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="22f6b-130">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="22f6b-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="22f6b-131">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="22f6b-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="22f6b-132">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="22f6b-132">Choose who can use this connection.</span></span> <span data-ttu-id="22f6b-133">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="22f6b-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="22f6b-134">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="22f6b-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="22f6b-135">Επιλέξτε ή αναζητήστε τη συνδρομή στην οποία θέλετε να χρησιμοποιήσετε τα δεδομένα του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="22f6b-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="22f6b-136">Μόλις επιλεγεί μια συνδρομή, μπορείτε επίσης να επιλέξετε **Χώρος εργασίας**, **Λογαριασμός χώρου αποθήκευσης** και **Περιέκτης**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="22f6b-137">Επιλέξτε **Αποθήκευση** για να αποθηκεύσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="22f6b-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="22f6b-138">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="22f6b-138">Configure an export</span></span>

<span data-ttu-id="22f6b-139">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="22f6b-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="22f6b-140">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="22f6b-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="22f6b-141">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="22f6b-142">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη εξαγωγής**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="22f6b-143">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="22f6b-144">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες [συνδέσεις](connections.md) αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="22f6b-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="22f6b-145">Παράσχετε ένα αναγνωρίσιμο **εμφανιζόμενο όνομα** για την εξαγωγή σας και ένα **όνομα βάσης δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="22f6b-146">Επιλέξτε ποιες οντότητες θέλετε να εξαγάγετε στο Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="22f6b-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="22f6b-147">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-147">Select **Save**.</span></span>

<span data-ttu-id="22f6b-148">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="22f6b-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="22f6b-149">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="22f6b-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="22f6b-150">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="22f6b-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="22f6b-151">Ενημέρωση εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="22f6b-151">Update an export</span></span>

1. <span data-ttu-id="22f6b-152">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="22f6b-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="22f6b-153">Επιλέξτε **Επεξεργασία** στην εξαγωγή που θέλετε να ενημερώσετε.</span><span class="sxs-lookup"><span data-stu-id="22f6b-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="22f6b-154">**Προσθέστε** ή **Καταργήστε** οντότητες από την επιλογή.</span><span class="sxs-lookup"><span data-stu-id="22f6b-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="22f6b-155">Εάν οι οντότητες καταργηθούν από την επιλογή, δεν διαγράφονται από τη βάση δεδομένων Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="22f6b-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="22f6b-156">Ωστόσο, οι μελλοντικές ανανεώσεις δεδομένων δεν θα ενημερώσουν τις οντότητες που καταργήθηκαν σε αυτήν τη βάση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="22f6b-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="22f6b-157">Η **Αλλαγή του ονόματος βάσης δεδομένων** δημιουργεί μια νέα βάση δεδομένων Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="22f6b-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="22f6b-158">Η βάση δεδομένων με το όνομα που είχε ρυθμιστεί προηγουμένως δεν θα λαμβάνει ενημερώσεις σε μελλοντικές ανανεώσεις.</span><span class="sxs-lookup"><span data-stu-id="22f6b-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
