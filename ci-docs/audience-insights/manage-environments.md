---
title: Δημιουργία και διαχείριση περιβαλλόντων
description: Μάθετε πώς να εγγράφεστε στην υπηρεσία και πώς να διαχειρίζεστε περιβάλλοντα.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 06310ea6fc72f26e21e185a6abcb5d19d4b201f6
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259099"
---
# <a name="manage-environments"></a><span data-ttu-id="254cc-103">Διαχείριση περιβαλλόντων</span><span class="sxs-lookup"><span data-stu-id="254cc-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="254cc-104">Αυτό το άρθρο εξηγεί τον τρόπο δημιουργίας ενός νέου οργανισμού και τον τρόπο παροχής ενός περιβάλλοντος.</span><span class="sxs-lookup"><span data-stu-id="254cc-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="254cc-105">Εγγραφείτε και δημιουργήστε έναν οργανισμό</span><span class="sxs-lookup"><span data-stu-id="254cc-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="254cc-106">Μεταβείτε στην τοποθεσία web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="254cc-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="254cc-107">Επιλέξτε **Γρήγορα αποτελέσματα**.</span><span class="sxs-lookup"><span data-stu-id="254cc-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="254cc-108">Επιλέξτε το σενάριο προτιμώμενης εγγραφής και επιλέξτε την αντίστοιχη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="254cc-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="254cc-109">Αποδεχτείτε τους όρους και τις προϋποθέσεις και επιλέξτε **Συνέχεια** για να ξεκινήσετε τη δημιουργία του οργανισμού.</span><span class="sxs-lookup"><span data-stu-id="254cc-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="254cc-110">Μετά τη δημιουργία του περιβάλλοντος, θα ανακατευθυνθείτε στο [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="254cc-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="254cc-111">Χρησιμοποιήστε το περιβάλλον επίδειξης για να εξερευνήσετε την εφαρμογή ή δημιουργήστε ένα νέο περιβάλλον ακολουθώντας τα βήματα που περιγράφονται στην επόμενη ενότητα.</span><span class="sxs-lookup"><span data-stu-id="254cc-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="254cc-112">Αφού καθορίσετε τις ρυθμίσεις περιβάλλοντος, επιλέξτε **Δημιουργία**.</span><span class="sxs-lookup"><span data-stu-id="254cc-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="254cc-113">Θα συνδεθείτε μετά τη δημιουργία του περιβάλλοντος με επιτυχία.</span><span class="sxs-lookup"><span data-stu-id="254cc-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="254cc-114">Δημιουργία περιβάλλοντος σε έναν υπάρχοντα οργανισμό</span><span class="sxs-lookup"><span data-stu-id="254cc-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="254cc-115">Υπάρχουν δύο τρόποι δημιουργίας νέου περιβάλλοντος.</span><span class="sxs-lookup"><span data-stu-id="254cc-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="254cc-116">Μπορείτε είτε να καθορίσετε μια εντελώς νέα ρύθμιση παραμέτρων είτε να αντιγράψετε ορισμένες ρυθμίσεις παραμέτρων από ένα υπάρχον περιβάλλον.</span><span class="sxs-lookup"><span data-stu-id="254cc-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="254cc-117">Οι οργανισμοί μπορούν να δημιουγήσουν *δύο* περιβάλλοντα για κάθε άδεια χρήσης του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="254cc-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="254cc-118">Εάν ο οργανισμός σας αγοράσει περισσότερες από μία άδειες χρήσης, [επικοινωνήστε με την ομάδα υποστήριξής μας](https://go.microsoft.com/fwlink/?linkid=2079641) για να αυξήσετε τον αριθμό των διαθέσιμων περιβαλλόντων.</span><span class="sxs-lookup"><span data-stu-id="254cc-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="254cc-119">Για περισσότερες πληροφορίες σχετικά με τη χωρητικότητα και την πρόσθετη χωρητικότητα, κάντε λήψη του [οδηγού άδειας χρήσης του Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="254cc-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="254cc-120">Για δημιουργία περιβάλλοντος:</span><span class="sxs-lookup"><span data-stu-id="254cc-120">To create an environment:</span></span>

1. <span data-ttu-id="254cc-121">Επιλέξτε τον επιλογέα **Περιβάλλον** στην κεφαλίδα της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="254cc-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="254cc-122">Επιλέξτε **Νέα**.</span><span class="sxs-lookup"><span data-stu-id="254cc-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="254cc-123">![Ρυθμίσεις περιβάλλοντος](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="254cc-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="254cc-124">Στο παράθυρο διαλόγου **Δημιουργία νέου περιβάλλοντος**, επιλέξτε **Νέο περιβάλλον**.</span><span class="sxs-lookup"><span data-stu-id="254cc-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="254cc-125">Εάν θέλετε να [αντιγράψετε δεδομένα από το τρέχον περιβάλλον](#considerations-for-copy-configuration-preview), επιλέξτε **Αντιγραφή από υπάρχον περιβάλλον**.</span><span class="sxs-lookup"><span data-stu-id="254cc-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="254cc-126">Θα δείτε μια λίστα όλων των διαθέσιμων περιβαλλόντων στον οργανισμό σας, από όπου μπορείτε να αντιγράψετε δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="254cc-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="254cc-127">Δώστε τις παρακάτω λεπτομέρειες:</span><span class="sxs-lookup"><span data-stu-id="254cc-127">Provide the following details:</span></span>
   - <span data-ttu-id="254cc-128">**Όνομα**: το όνομα για αυτό το περιβάλλον.</span><span class="sxs-lookup"><span data-stu-id="254cc-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="254cc-129">Αυτό το πεδίο είναι ήδη συμπληρωμένο εάν αντιγράψετε από ένα υπάρχον περιβάλλον, αλλά μπορείτε να το αλλάξετε.</span><span class="sxs-lookup"><span data-stu-id="254cc-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="254cc-130">**Περιοχή**: η περιοχή στην οποία αναπτύσσεται και φιλοξενείται η υπηρεσία.</span><span class="sxs-lookup"><span data-stu-id="254cc-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="254cc-131">**Τύπος** : Επιλέξτε εάν θέλετε να δημιουργήσετε ένα περιβάλλον παραγωγής ή προστατευμένης εκτέλεσης.</span><span class="sxs-lookup"><span data-stu-id="254cc-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="254cc-132">Προαιρετικά, μπορείτε να επιλέξετε **Ρυθμίσεις για προχωρημένους**:</span><span class="sxs-lookup"><span data-stu-id="254cc-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="254cc-133">**Αποθηκεύστε όλα τα δεδομένα σε**: καθορίζει τη θέση στην οποία θέλετε να αποθηκεύσετε τα δεδομένα εξόδου που δημιουργούνται από το Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="254cc-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="254cc-134">Θα έχετε δύο επιλογές: **Χώρος αποθήκευσης Customer Insights** (ένα Azure Data Lake που το διαχειρίζεται η ομάδα Customer Insights) και  **Azure Data Lake Storage Gen2** (το δικό σας Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="254cc-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="254cc-135">Από προεπιλογή, ο χώρος αποθήκευσης Customer Insights είναι επιλεγμένος.</span><span class="sxs-lookup"><span data-stu-id="254cc-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="254cc-136">Αποθηκεύοντας δεδομένα σε Azure Data Lake Storage, αποδέχεστε ότι τα δεδομένα θα μεταφερθούν και θα αποθηκευτούν στην κατάλληλη γεωγραφική θέση για αυτόν τον λογαριασμό χώρου αποθήκευσης Azure, η οποία μπορεί να διαφέρει από τη θέση στην οποία αποθηκεύονται τα δεδομένα στο Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="254cc-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="254cc-137">Μάθετε περισσότερα στο Κέντρο αξιοπιστίας της Microsoft.</span><span class="sxs-lookup"><span data-stu-id="254cc-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="254cc-138">Προς το παρόν, οι οντότητες που καταναλώνονται αποθηκεύονται πάντα στη λίμνη διαχειριζόμενo data lake Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="254cc-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="254cc-139">Υποστηρίζουμε μόνο λογαριασμούς αποθήκευσης Azure Data Lake Gen2 από την ίδια περιοχή Azure που επιλέξατε κατά τη δημιουργία του περιβάλλοντος.</span><span class="sxs-lookup"><span data-stu-id="254cc-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="254cc-140">Υποστηρίζουμε μόνο λογαριασμούς χώρου αποθήκευσης με χώρο ονομάτων κατά ιεραρχία Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="254cc-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="254cc-141">Για την επιλογή Azure Data Lake Storage Gen2, μπορείτε να επιλέξετε ανάμεσα σε μια επιλογή βασισμένη σε πόρους και μια επιλογή βασισμένη σε συνδρομή για έλεγχο ταυτότητας.</span><span class="sxs-lookup"><span data-stu-id="254cc-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="254cc-142">Για περισσότερες πληροφορίες, δείτε [Σύνδεση πληροφοριών κοινού σε έναν λογαριασμό Azure Data Lake Storage Gen2 με έναν διευθυντή εξυπηρέτησης Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="254cc-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="254cc-143">Το όνομα του **Περιέκτη** δεν μπορεί να αλλάξει και θα είναι `customerinsights`.</span><span class="sxs-lookup"><span data-stu-id="254cc-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="254cc-144">Αν θέλετε να χρησιμοποιήσετε [προβλέψεις](predictions.md), ρυθμίστε τις παραμέτρους κοινής χρήσης δεδομένων με το Microsoft Dataverse ή ενεργοποιήστε την εισαγωγή δεδομένων από προελεύσεις δεδομένων εσωτερικής εγκατάστασης, δώστε τη διεύθυνση URL του περιβάλλοντος Microsoft Dataverse στην περιοχή **Ρύθμιση παραμέτρων κοινής χρήσης δεδομένων με Microsoft Dataverse και ενεργοποιήστε πρόσθετες δυνατότητες**.</span><span class="sxs-lookup"><span data-stu-id="254cc-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="254cc-145">Επιλέξτε **Ενεργοποίηση κοινής χρήσης δεδομένων** για κοινή χρήση δεδομένων εξόδου του Customer Insights με ένα Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="254cc-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="254cc-146">Η κοινή χρήση δεδομένων με το Microsoft Dataverse Managed Data Lake δεν υποστηρίζεται αυτή τη στιγμή όταν αποθηκεύετε όλα τα δεδομένα στη δική σας Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="254cc-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="254cc-147">Η [Πρόβλεψη τιμών που λείπουν σε μια οντότητα](predictions.md) δεν υποστηρίζεται αυτή τη στιγμή όταν ενεργοποιείτε την κοινή χρήση δεδομένων με το Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="254cc-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="254cc-148">![Επιλογές ρύθμισης παραμέτρων για ενεργοποίηση της κοινής χρήσης δεδομένων με το Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="254cc-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="254cc-149">Όταν εκτελείτε διεργασίες, όπως η λήψη δεδομένων ή η δημιουργία τμήματος, οι αντίστοιχοι φάκελοι θα δημιουργηθούν στον λογαριασμό αποθήκευσης που καθορίσατε παραπάνω.</span><span class="sxs-lookup"><span data-stu-id="254cc-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="254cc-150">Τα αρχεία δεδομένων και τα αρχεία model.json θα δημιουργηθούν και θα προστεθούν στους φακέλους, ανάλογα με το όνομα διεργασίας.</span><span class="sxs-lookup"><span data-stu-id="254cc-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="254cc-151">Εάν δημιουργείτε πολλαπλά περιβάλλοντα του Customer Insights και επιλέξετε να αποθηκεύσετε τις οντότητες εξόδου από εκείνα τα περιβάλλοντα στον λογαριασμό αποθήκευσης, θα δημιουργηθούν ξεχωριστοί φάκελοι για κάθε περιβάλλον με ci_<environmentid> στο κοντέινερ.</span><span class="sxs-lookup"><span data-stu-id="254cc-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="254cc-152">Ζητήματα προς εξέταση για τη ρύθμιση παραμέτρων αντιγραφής (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="254cc-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="254cc-153">Αντιγράφονται οι παρακάτω διαμορφώσεις:</span><span class="sxs-lookup"><span data-stu-id="254cc-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="254cc-154">Ρύθμιση παραμέτρων δυνατότητας</span><span class="sxs-lookup"><span data-stu-id="254cc-154">Feature configurations</span></span>
- <span data-ttu-id="254cc-155">Προέλευση δεδομένων που έχουν ενσωματωθεί/εξαχθεί</span><span class="sxs-lookup"><span data-stu-id="254cc-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="254cc-156">Ρύθμιση παραμέτρων ενοποίησης δεδομένων (αντιστοίχιση, αντιστοιχία, συγχώνευση)</span><span class="sxs-lookup"><span data-stu-id="254cc-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="254cc-157">Τμήματα</span><span class="sxs-lookup"><span data-stu-id="254cc-157">Segments</span></span>
- <span data-ttu-id="254cc-158">Μετρήσεις</span><span class="sxs-lookup"><span data-stu-id="254cc-158">Measures</span></span>
- <span data-ttu-id="254cc-159">Σχέσεις</span><span class="sxs-lookup"><span data-stu-id="254cc-159">Relationships</span></span>
- <span data-ttu-id="254cc-160">Δραστηριότητες</span><span class="sxs-lookup"><span data-stu-id="254cc-160">Activities</span></span>
- <span data-ttu-id="254cc-161">Αναζήτηση και φιλτράρισμα ευρετηρίου</span><span class="sxs-lookup"><span data-stu-id="254cc-161">Search & filter Index</span></span>
- <span data-ttu-id="254cc-162">Προορισμοί εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="254cc-162">Export destinations</span></span>
- <span data-ttu-id="254cc-163">Προγραμματισμένη ανανέωση</span><span class="sxs-lookup"><span data-stu-id="254cc-163">Scheduled refresh</span></span>
- <span data-ttu-id="254cc-164">Εμπλουτισμοί</span><span class="sxs-lookup"><span data-stu-id="254cc-164">Enrichments</span></span>
- <span data-ttu-id="254cc-165">Διαχείριση μοντέλου</span><span class="sxs-lookup"><span data-stu-id="254cc-165">Model management</span></span>
- <span data-ttu-id="254cc-166">Αναθέσεις ρόλων</span><span class="sxs-lookup"><span data-stu-id="254cc-166">Role assignments</span></span>

<span data-ttu-id="254cc-167">*Δεν* αντιγράφονται οι παρακάτω ρυθμίσεις:</span><span class="sxs-lookup"><span data-stu-id="254cc-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="254cc-168">Προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="254cc-168">Customer profiles.</span></span>
- <span data-ttu-id="254cc-169">Διαπιστευτήρια προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="254cc-169">Data source credentials.</span></span> <span data-ttu-id="254cc-170">Θα πρέπει να παρέχετε τα διαπιστευτήρια για κάθε προέλευση δεδομένων και να ανανεώνετε τις προελεύσεις δεδομένων με μη αυτόματο τρόπο.</span><span class="sxs-lookup"><span data-stu-id="254cc-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="254cc-171">Προελεύσεις δεδομένων από φάκελο Common Data Model και το Common Data Service διαχειριζόμενη lake.</span><span class="sxs-lookup"><span data-stu-id="254cc-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="254cc-172">Θα πρέπει να δημιουργήσετε αυτές τις προελεύσεις δεδομένων με μη αυτόματο τρόπο, με το ίδιο όνομα όπως στο περιβάλλον προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="254cc-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="254cc-173">Όταν αντιγράφετε ένα περιβάλλον, θα δείτε ένα μήνυμα επιβεβαίωσης ότι το νέο περιβάλλον έχει δημιουργηθεί.</span><span class="sxs-lookup"><span data-stu-id="254cc-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="254cc-174">Επιλέξτε **Μετάβαση σε προελεύσεις δεδομένων** για να δείτε τη λίστα των προελεύσεων δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="254cc-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="254cc-175">Σε όλες τις προελεύσεις δεδομένων θα εμφανίζεται μια κατάσταση **Απαιτούνται διαπιστευτήρια**.</span><span class="sxs-lookup"><span data-stu-id="254cc-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="254cc-176">Επεξεργαστείτε τις προελεύσεις δεδομένων και καταχωρίστε τα διαπιστευτήρια για την ανανέωσή τους.</span><span class="sxs-lookup"><span data-stu-id="254cc-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="254cc-177">![Προελεύσεις δεδομένων που έχουν αντιγραφεί](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="254cc-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="254cc-178">Αφού ανανεώσετε τις προελεύσεις δεδομένων, μεταβείτε στην ενότητα **Δεδομένα** > **Ενοποίηση**.</span><span class="sxs-lookup"><span data-stu-id="254cc-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="254cc-179">Εδώ θα βρείτε τις ρυθμίσεις από το περιβάλλον προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="254cc-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="254cc-180">Επεξεργαστείτε όπως απαιτείται ή επιλέξτε **Εκτέλεση** για να ξεκινήσετε τη διεργασία ενοποίησης δεδομένων και να δημιουργήσετε την ενοποιημένη οντότητα πελάτη.</span><span class="sxs-lookup"><span data-stu-id="254cc-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="254cc-181">Όταν ολοκληρωθεί η ενοποίηση των δεδομένων, μεταβείτε στην επιλογή **Μέτρα** και **Τμήματα** για να τα ανανεώσετε.</span><span class="sxs-lookup"><span data-stu-id="254cc-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="254cc-182">Επεξεργασία υφιστάμενου περιβάλλοντος</span><span class="sxs-lookup"><span data-stu-id="254cc-182">Edit an existing environment</span></span>

<span data-ttu-id="254cc-183">Μπορείτε να επεξεργαστείτε ορισμένες από τις λεπτομέρειες των υπαρχουσών περιβαλλόντων.</span><span class="sxs-lookup"><span data-stu-id="254cc-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="254cc-184">Επιλέξτε τον επιλογέα **Περιβάλλον** στην κεφαλίδα της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="254cc-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="254cc-185">Επιλέξτε το εικονίδιο **Επεξεργασία**.</span><span class="sxs-lookup"><span data-stu-id="254cc-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="254cc-186">Στο πλαίσιο **Επεξεργασία περιβάλλοντος**, μπορείτε να ενημερώσετε για το περιβάλλον εργασίας το **εμφανιζόμενο όνομα**, αλλά δεν μπορείτε να αλλάξετε την **περιοχή** ή τον **τύπο**.</span><span class="sxs-lookup"><span data-stu-id="254cc-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="254cc-187">Εάν ένα περιβάλλον έχει ρυθμιστεί για την αποθήκευση δεδομένων στο Azure Data Lake Storage Gen2, μπορείτε να ενημερώσετε το **Κλειδί λογαριασμού**.</span><span class="sxs-lookup"><span data-stu-id="254cc-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="254cc-188">Ωστόσο, δεν μπορείτε να αλλάξετε το **Όνομα λογαριασμού** ή το όνομα του **Κοντέινερ**.</span><span class="sxs-lookup"><span data-stu-id="254cc-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="254cc-189">Προαιρετικά, μπορείτε να κάνετε ενημέρωση από μια σύνδεση βάσει κλειδιού λογαριασμού σε μια σύνδεση βασισμένη σε πόρους ή σε μια σύνδεση βασισμένη σε συνδρομή.</span><span class="sxs-lookup"><span data-stu-id="254cc-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="254cc-190">Μετά την αναβάθμιση, δεν μπορείτε να επιστρέψετε στο κλειδί λογαριασμού μετά την ενημέρωση.</span><span class="sxs-lookup"><span data-stu-id="254cc-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="254cc-191">Για περισσότερες πληροφορίες, δείτε [Σύνδεση πληροφοριών κοινού σε έναν λογαριασμό Azure Data Lake Storage Gen2 με έναν διευθυντή εξυπηρέτησης Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="254cc-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="254cc-192">Δεν μπορείτε να αλλάξετε τις πληροφορίες **Κοντέινερ** κατά την ενημέρωση της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="254cc-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="254cc-193">Προαιρετικά, μπορείτε να παρέχετε μια διεύθυνση URL περιβάλλοντος Microsoft Dataverse στην περιοχή **Ρύθμιση παραμέτρων κοινής χρήσης δεδομένων με το Microsoft Dataverse και ενεργοποίηση πρόσθετων δυνατοτήτων**.</span><span class="sxs-lookup"><span data-stu-id="254cc-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="254cc-194">Αυτές οι δυνατότητες περιλαμβάνουν την κοινή χρήση δεδομένων με εφαρμογές και λύσεις που βασίζονται στο Microsoft Dataverse, την κατάποση δεδομένων προελεύσεις δεδομένων εσωτερικής εγκατάστασης ή τις [προβλέψεις](predictions.md) χρήσης.</span><span class="sxs-lookup"><span data-stu-id="254cc-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="254cc-195">Επιλέξτε **Ενεργοποίηση κοινής χρήσης δεδομένων** για κοινή χρήση δεδομένων εξόδου του Customer Insights με ένα Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="254cc-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="254cc-196">Η κοινή χρήση δεδομένων με το Microsoft Dataverse Managed Data Lake δεν υποστηρίζεται αυτή τη στιγμή όταν αποθηκεύετε όλα τα δεδομένα στη δική σας Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="254cc-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="254cc-197">[Η πρόβλεψη τιμών που λείπουν σε μια οντότητα](predictions.md) δεν υποστηρίζεται αυτή τη στιγμή όταν ενεργοποιείτε την κοινή χρήση δεδομένων με το Microsoft Dataverse Διαχειριζόμενο Data Lake.</span><span class="sxs-lookup"><span data-stu-id="254cc-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="254cc-198">Μετά την ενεργοποίηση της κοινής χρήση δεδομένων με το Microsoft Dataverse, θα ξεκινήσει μια πλήρης ανανέωση των προελεύσεων δεδομένων και άλλων διαδικασιών.</span><span class="sxs-lookup"><span data-stu-id="254cc-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="254cc-199">Εάν εκτελούνται και βρίσκονται σε ουρά διεργασίες, δεν θα δείτε την επιλογή για να ενεργοποιήσετε την κοινή χρήση δεδομένων με το Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="254cc-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="254cc-200">Περιμένετε μέχρι να ολοκληρωθεί ή να ακυρωθεί αυτή η διαδικασία, ώστε να είναι δυνατή η κοινή χρήση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="254cc-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Επιλογές ρύθμισης παραμέτρων για ενεργοποίηση της κοινής χρήσης δεδομένων με το Microsoft Dataverse.":::
   
   <span data-ttu-id="254cc-202">Όταν εκτελείτε διεργασίες, όπως η λήψη δεδομένων ή η δημιουργία τμήματος, οι αντίστοιχοι φάκελοι θα δημιουργηθούν στον λογαριασμό αποθήκευσης που καθορίσατε παραπάνω.</span><span class="sxs-lookup"><span data-stu-id="254cc-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="254cc-203">Τα αρχεία δεδομένων και τα αρχεία model.json θα δημιουργηθούν και θα προστεθούν στους αντίστοιχους υποφακέλους, ανάλογα με τη διεργασία που εκτελείτε.</span><span class="sxs-lookup"><span data-stu-id="254cc-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="254cc-204">Επαναφέρετε ένα υπάρχον περιβάλλον</span><span class="sxs-lookup"><span data-stu-id="254cc-204">Reset an existing environment</span></span>

<span data-ttu-id="254cc-205">Ως διαχειριστής μπορείτε να επαναφέρετε ένα περιβάλλον σε μια κενή κατάσταση, εάν θέλετε να διαγράψετε όλες τις ρυθμίσεις παραμέτρων και να καταργήσετε τα δεδομένα που έχετε λάβει.</span><span class="sxs-lookup"><span data-stu-id="254cc-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="254cc-206">Επιλέξτε τον επιλογέα **Περιβάλλον** στην κεφαλίδα της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="254cc-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="254cc-207">Επιλέξτε το περιβάλλον που θέλετε να επαναφέρετε και επιλέξτε τα αποσιωπητικά **...**.</span><span class="sxs-lookup"><span data-stu-id="254cc-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="254cc-208">Ενεργοποιήστε την επιλογή **Επαναφορά**.</span><span class="sxs-lookup"><span data-stu-id="254cc-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="254cc-209">Για να επιβεβαιώσετε τη διαγραφή, εισαγάγετε το όνομα του περιβάλλοντος και επιλέξτε **Επαναφορά**.</span><span class="sxs-lookup"><span data-stu-id="254cc-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="254cc-210">Διαγραφή υπάρχοντος περιβάλλοντος (διαθέσιμο μόνο για διαχειριστές)</span><span class="sxs-lookup"><span data-stu-id="254cc-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="254cc-211">Ως διαχειριστής, μπορείτε να διαγράψετε ένα περιβάλλον που διαχειρίζεστε.</span><span class="sxs-lookup"><span data-stu-id="254cc-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="254cc-212">Επιλέξτε τον επιλογέα **Περιβάλλον** στην κεφαλίδα της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="254cc-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="254cc-213">Επιλέξτε το περιβάλλον που θέλετε να επαναφέρετε και επιλέξτε τα αποσιωπητικά **...**.</span><span class="sxs-lookup"><span data-stu-id="254cc-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="254cc-214">Ενεργοποιήστε την επιλογή **Διαγραφή**.</span><span class="sxs-lookup"><span data-stu-id="254cc-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="254cc-215">Για να επιβεβαιώσετε τη διαγραφή, καταγράψτε το όνομα του περιβάλλοντος και επιλέξτε **Διαγραφή**.</span><span class="sxs-lookup"><span data-stu-id="254cc-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
