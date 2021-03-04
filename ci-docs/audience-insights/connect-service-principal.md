---
title: Σύνδεση με έναν λογαριασμό Azure Data Lake Storage Gen2 με έναν διευθυντή εξυπηρέτησης
description: Χρησιμοποιήστε έναν διευθυντή εξυπηρέτησης Azure για πληροφορίες κοινού για να συνδεθείτε με τη δική σας λίμνη δεδομένων όταν την επισυνάπτετε σε πληροφορίες κοινού.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267722"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="1465d-103">Σύνδεση με έναν λογαριασμό Azure Data Lake Storage Gen2 με έναν κύριο υπηρεσίας Azure για πληροφορίες κοινού</span><span class="sxs-lookup"><span data-stu-id="1465d-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="1465d-104">Τα αυτοματοποιημένα εργαλεία που χρησιμοποιούν υπηρεσίες Azure θα πρέπει να έχουν πάντοτε περιορισμένα δικαιώματα.</span><span class="sxs-lookup"><span data-stu-id="1465d-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="1465d-105">Αντί να συνδέεστε με εφαρμογές ως πλήρως προνομιούχος χρήστης, το Azure προσφέρει τις αρχές εξυπηρέτησης.</span><span class="sxs-lookup"><span data-stu-id="1465d-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="1465d-106">Διαβάστε παρακάτω για να μάθετε πώς να συνδέσετε πληροφορίες κοινού με έναν λογαριασμό Azure Data Lake Storage Gen2 χρησιμοποιώντας έναν διευθυντή εξυπηρέτησης Azure αντί για κλειδιά λογαριασμών αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="1465d-107">Μπορείτε να χρησιμοποιήσετε τον διευθυντή εξυπηρέτησης για να [προσθέσετε ή να επεξεργαστείτε με ασφάλεια έναν φάκελο Common Data Model ως προέλευση δεδομένων](connect-common-data-model.md) ή να [δημιουργήσετε ένα νέο ή να ενημερώσετε ένα υπάρχον περιβάλλον](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="1465d-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="1465d-108">Ο λογαριασμός αποθήκευσης Azure Data Lake Gen2 που σκοπεύει να χρησιμοποιήσει την αρχή της υπηρεσίας πρέπει να έχει [ενεργοποιημένο τον Ιεραρχικό χώρο ονομάτων (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="1465d-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="1465d-109">Χρειάζεστε δικαιώματα διαχειριστή για τη συνδρομή σας Azure για τη δημιουργία της αρχής εξυπηρέτησης.</span><span class="sxs-lookup"><span data-stu-id="1465d-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="1465d-110">Δημιουργία της αρχής εξυπηρέτησης Azure για πληροφορίες κοινού</span><span class="sxs-lookup"><span data-stu-id="1465d-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="1465d-111">Πριν από τη δημιουργία μιας νέας αρχής εξυπηρέτησης για πληροφορίες κοινού, ελέγξτε εάν υπάρχει ήδη στον οργανισμό σας.</span><span class="sxs-lookup"><span data-stu-id="1465d-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="1465d-112">Αναζήτηση υπάρχουσας αρχής εξυπηρέτησης</span><span class="sxs-lookup"><span data-stu-id="1465d-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="1465d-113">Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com) και συνδεθείτε στον οργανισμό σας.</span><span class="sxs-lookup"><span data-stu-id="1465d-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="1465d-114">Επιλέξτε **Azure Active Directory** από τις υπηρεσίες Azure.</span><span class="sxs-lookup"><span data-stu-id="1465d-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="1465d-115">Στην περιοχή **Διαχείριση**, επιλέξτε **Εταιρικές εφαρμογές**.</span><span class="sxs-lookup"><span data-stu-id="1465d-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="1465d-116">Αναζητήστε το αναγνωριστικό εφαρμογής πρώτου μέρους των πληροφοριών κοινού `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ή το όνομα `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="1465d-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="1465d-117">Εάν βρείτε μια αντίστοιχη καρτέλα, αυτό σημαίνει ότι υπάρχει ο διευθυντής εξυπηρέτησης για πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="1465d-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="1465d-118">Δεν χρειάζεται να τη δημιουργήσετε ξανά.</span><span class="sxs-lookup"><span data-stu-id="1465d-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Στιγμιότυπο οθόνης που εμφανίζει τον υπάρχοντα διευθυντή εξυπηρέτησης.":::
   
6. <span data-ttu-id="1465d-120">Εάν δεν επιστραφούν αποτελέσματα, δημιουργήστε έναν νέο διευθυντή εξυπηρέτησης.</span><span class="sxs-lookup"><span data-stu-id="1465d-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="1465d-121">Δημιουργία μιας νέας αρχής εξυπηρέτησης</span><span class="sxs-lookup"><span data-stu-id="1465d-121">Create a new service principal</span></span>

1. <span data-ttu-id="1465d-122">Εγκαταστήστε την πιο πρόσφατη έκδοση του **Azure Active Directory PowerShell για Graph**.</span><span class="sxs-lookup"><span data-stu-id="1465d-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="1465d-123">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Εγκατάσταση Azure Active Directory PowerShell για Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="1465d-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="1465d-124">Στον υπολογιστή σας, επιλέξτε το πλήκτρο Windows στο πληκτρολόγιό σας και πραγματοποιήστε αναζήτηση για **Windows PowerShell** και **Εκτέλεση ως Διαχειριστής**.</span><span class="sxs-lookup"><span data-stu-id="1465d-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="1465d-125">Στο παράθυρο PowerShell που ανοίγει, καταχωρείστε `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="1465d-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="1465d-126">Δημιουργήστε τον διευθυντή εξυπηρέτησης για πληροφορίες κοινού με τη μονάδα Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1465d-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="1465d-127">Στο παράθυρο PowerShell, καταχωρείστε `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="1465d-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="1465d-128">Αντικαταστήστε το αναγνωριστικό μισθωτή με το πραγματικό αναγνωριστικό του μισθωτή σας, στον οποίο θέλετε να δημιουργήσετε τον διευθυντή εξυπηρέτησης.</span><span class="sxs-lookup"><span data-stu-id="1465d-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="1465d-129">Η παράμετρος ονόματος περιβάλλοντος `AzureEnvironmentName` είναι προαιρετική.</span><span class="sxs-lookup"><span data-stu-id="1465d-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="1465d-130">Εισαγάγετε `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="1465d-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="1465d-131">Αυτή η εντολή δημιουργεί τον διευθυντή εξυπηρέτησης για πληροφορίες κοινού σχετικά με τον επιλεγμένο μισθωτή.</span><span class="sxs-lookup"><span data-stu-id="1465d-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="1465d-132">Εκχώρηση δικαιωμάτων στον διευθυντή εξυπηρέτησης για πρόσβαση στον λογαριασμό αποθήκευσης</span><span class="sxs-lookup"><span data-stu-id="1465d-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="1465d-133">Μεταβείτε στην πύλη Azure για να εκχωρήσετε δικαιώματα στον διευθυντή εξυπηρέτησης για τον λογαριασμό χώρου αποθήκευσης που θέλετε να χρησιμοποιήσετε στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="1465d-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="1465d-134">Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com) και συνδεθείτε στον οργανισμό σας.</span><span class="sxs-lookup"><span data-stu-id="1465d-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="1465d-135">Ανοίξτε τον λογαριασμό χώρου αποθήκευσης στον οποίο θέλετε να έχει πρόσβαση ο διευθυντής εξυπηρέτησης για πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="1465d-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="1465d-136">Επιλέξτε **Έλεγχος πρόσβασης (IAM)** από το παράθυρο περιήγησης και επιλέξτε **Προσθήκη** > **Προσθήκη εκχώρησης ρόλου**.</span><span class="sxs-lookup"><span data-stu-id="1465d-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Στιγμιότυπο οθόνης που εμφανίζει την πύλη Azure κατά την προσθήκη μιας ανάθεσης ρόλου.":::
   
1. <span data-ttu-id="1465d-138">Στο τμήμα παραθύρου **Προσθήκη ρόλου ανάθεσης**, ορίστε τις ακόλουθες ιδιότητες:</span><span class="sxs-lookup"><span data-stu-id="1465d-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="1465d-139">Ρόλος: *Συμβάλλων δεδομένων αντικειμένου Blob αποθήκευσης*</span><span class="sxs-lookup"><span data-stu-id="1465d-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="1465d-140">Ανάθεση πρόσβασης σε: *Χρήστη, ομάδα ή διευθυντή εξυπηρέτησης*</span><span class="sxs-lookup"><span data-stu-id="1465d-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="1465d-141">Επιλέξτε: *Dynamics 365 AI για Customer Insights* (ο [διευθυντής εξυπηρέτησης που δημιουργήσατε](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="1465d-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="1465d-142">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="1465d-142">Select **Save**.</span></span>

<span data-ttu-id="1465d-143">Μπορεί να διαρκέσει έως και 15 λεπτά για να γίνουν οι αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="1465d-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="1465d-144">Εισαγάγετε το αναγνωριστικό πόρου Azure ή τις λεπτομέρειες συνδρομής Azure μέσα στο συνημμένο λογαριασμού χώρου αποθήκευσης σε Πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="1465d-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="1465d-145">Επισυνάψτε έναν λογαριασμό αποθήκευσης Azure Data Lake στις πληροφορίες κοινού για να [αποθηκεύσετε δεδομένα εξόδου](manage-environments.md) ή να [τα χρησιμοποιήσετε ως προέλευση δεδομένων](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="1465d-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="1465d-146">Με την επιλογή της δυνατότητας Azure Data Lake μπορείτε να επιλέξετε μεταξύ μιας προσέγγισης βασισμένης σε πόρους ή μιας προσέγγισης βασισμένης σε συνδρομή.</span><span class="sxs-lookup"><span data-stu-id="1465d-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="1465d-147">Ακολουθήστε τα παρακάτω βήματα για να παράσχετε τις απαιτούμενες πληροφορίες σχετικά με την επιλεγμένη προσέγγιση.</span><span class="sxs-lookup"><span data-stu-id="1465d-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="1465d-148">Σύνδεση λογαριασμού χώρου αποθήκευσης βάσει πόρων</span><span class="sxs-lookup"><span data-stu-id="1465d-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="1465d-149">Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com), συνδεθείτε στη συνδρομή σας και ανοίξτε τον λογαριασμό χώρου αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="1465d-150">Μεταβείτε στις **Ρυθμίσεις** > **Ιδιότητες** στο τμήμα παραθήρου περιήγησης.</span><span class="sxs-lookup"><span data-stu-id="1465d-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="1465d-151">Αντιγράψτε την τιμή αναγνωριστικού πόρου του λογαριασμού αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Αντιγράψτε το αναγνωριστικό πόρου του λογαριασμού αποθήκευσης.":::

1. <span data-ttu-id="1465d-153">Στις πληροφορίες κοινού, εισαγάγετε το αναγνωριστικό πόρου στο πεδίο πόρου που εμφανίζεται στην οθόνη σύνδεσης του λογαριασμού αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Εισαγάγετε τις πληροφορίες αναγνωριστικού πόρου του λογαριασμού αποθήκευσης.":::   
   
1. <span data-ttu-id="1465d-155">Συνεχίστε με τα υπόλοιπα βήματα στις πληροφορίες κοινού για να επισυνάψετε τον λογαριασμό χώρου αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="1465d-156">Σύνδεση λογαριασμού χώρου αποθήκευσης βάσει συνδρομής</span><span class="sxs-lookup"><span data-stu-id="1465d-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="1465d-157">Μεταβείτε στην [πύλη διαχείρισης Azure](https://portal.azure.com), συνδεθείτε στη συνδρομή σας και ανοίξτε τον λογαριασμό χώρου αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="1465d-158">Μεταβείτε στις **Ρυθμίσεις** > **Ιδιότητες** στο τμήμα παραθήρου περιήγησης.</span><span class="sxs-lookup"><span data-stu-id="1465d-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="1465d-159">Επανεξετάστε τη **Συνδρομή**, την **Ομάδα πόρων** και το **Όνομα** του λογαριασμού χώρου αποθήκευσης, για να βεβαιωθείτε ότι έχετε επιλέξει τις σωστές τιμές στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="1465d-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="1465d-160">Στις πληροφορίες κοινού, επιλέξτε τις τιμές ή τα αντίστοιχα πεδία κατά την προσάρτηση του λογαριασμού χώρου αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="1465d-161">Συνεχίστε με τα υπόλοιπα βήματα στις πληροφορίες κοινού για να επισυνάψετε τον λογαριασμό χώρου αποθήκευσης.</span><span class="sxs-lookup"><span data-stu-id="1465d-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]