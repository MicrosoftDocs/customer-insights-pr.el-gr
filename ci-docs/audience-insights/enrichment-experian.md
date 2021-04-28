---
title: Εμπλουτισμός με τον εμπλουτισμό τρίτου μέρους Experian
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτου μέρους της Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896373"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="bb4c3-103">Εμπλουτισμός προφίλ πελατών με δημογραφικά στοιχεία από το Experian (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="bb4c3-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="bb4c3-104">Το Experian είναι παγκόσμιος ηγέτης στις υπηρεσίες αναφοράς και μάρκετινγκ για τους καταναλωτές και τις επιχειρήσεις.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="bb4c3-105">Με τις υπηρεσίες εμπλουτισμού δεδομένων του Experian, μπορείτε να δημιουργήσετε μια βαθύτερη κατανόηση των πελατών σας εμπλουτίζοντας τα προφίλ των πελατών σας με δημογραφικά δεδομένα, όπως το μέγεθος του νοικοκυριού, τα εισοδήματα και πολλά άλλα.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb4c3-106">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="bb4c3-106">Prerequisites</span></span>

<span data-ttu-id="bb4c3-107">Για να ρυθμίσετε το Experian, πρέπει να πληρούνται οι παρακάτω προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="bb4c3-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bb4c3-108">Έχετε μια ενεργή συνδρομή στο Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-108">You have an active Experian subscription.</span></span> <span data-ttu-id="bb4c3-109">Για να λάβετε μια συνδρομή, [επικοινωνήστε με το Experian](https://www.experian.com/marketing-services/contact) απευθείας.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="bb4c3-110">[Μάθετε περισσότερα σχετικά με τον εμπλουτισμό δεδομένων Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="bb4c3-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="bb4c3-111">Μια σύνδεση Experian έχει ήδη ρυθμιστεί από έναν διαχειριστή *ή* έχετε δικαιώματα [διαχειριστή](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="bb4c3-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="bb4c3-112">Χρειάζεστε, επίσης, το αναγνωριστικό χρήστη, το αναγνωριστικό μέρους και τον αριθμό μοντέλου για τον λογαριασμό ασφαλούς μεταφοράς (ST) με δυνατότητα SSH, που δημιούργησε για λογαριασμό σας το Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="bb4c3-113">Ρύθμιση παραμέτρων του εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="bb4c3-113">Configure the enrichment</span></span>

1. <span data-ttu-id="bb4c3-114">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="bb4c3-115">Επιλέξτε **Εμπλουτισμός των δεδομένων μου** στο πλακίδιο Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb4c3-116">![Πλακίδιο Experian](media/experian-tile.png "Πλακίδιο Experian")</span><span class="sxs-lookup"><span data-stu-id="bb4c3-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="bb4c3-117">Επιλέξτε μια [σύνδεση](connections.md) από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="bb4c3-118">Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="bb4c3-119">Εάν είστε διαχειριστής, μπορείτε να δημιουργήσετε μια σύνδεση επιλέγοντας **Προσθήκη σύνδεσης** και επιλέγοντας το Experian από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="bb4c3-120">Επιλέξτε **Σύνδεση με Experian** για να επιβεβαιώσετε την επιλογή σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="bb4c3-121">Επιλέξτε **Επόμενο** και επιλέξτε το **σύνολο δεδομένων πελατών** που θέλετε να εμπλουτίσετε με δημογραφικά στοιχεία από το Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="bb4c3-122">Μπορείτε να επιλέξετε την οντότητα **Πελάτης** για να εμπλουτίσετε όλα τα προφίλ πελατών σας ή να επιλέξετε μια οντότητα τμήματος αγοράς για να εμπλουτίσετε μόνο τα προφίλ πελατών που περιέχονται σε αυτό το τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Στιγμιότυπο οθόνης κατά την επιλογή του συνόλου δεδομένων πελάτη.":::

1. <span data-ttu-id="bb4c3-124">Επιλέξτε **Επόμενο** και καθορίστε ποιον τύπο πεδίων από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιούνται για την αναζήτηση δεδομένων που αντιστοιχούν στα δημογραφικά στοιχεία από το Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="bb4c3-125">Απαιτείται τουλάχιστον ένα από τα πεδία **Όνομα και διεύθυνση** μ **Τηλέφωνο** ή **Ηλεκτρονικό ταχυδρομείο**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="bb4c3-126">Για μεγαλύτερη ακρίβεια αντιστοίχισης, μπορούν να προστεθούν έως δύο άλλα πεδία.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="bb4c3-127">Αυτή η επιλογή θα επηρεάσει τα πεδία αντιστοίχισης στα οποία έχετε πρόσβαση στο επόμενο βήμα.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="bb4c3-128">Περισσότερα βασικά χαρακτηριστικά αναγνωριστικού που στάλθηκαν στο Experian πιθανών αποδίδουν υψηλότερο ποσοστό αντιστοιχίας.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="bb4c3-129">Επιλέξτε **Επόμενο** για να αρχίσετε την αντιστοίχιση πεδίων.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="bb4c3-130">Ορίστε ποια πεδία από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιούνται για την αναζήτηση δεδομένων που αντιστοιχούν στα δημογραφικά στοιχεία από το Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="bb4c3-131">Τα υποχρεωτικά πεδία φέρουν σήμανση.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-131">Required fields are marked.</span></span>

1. <span data-ttu-id="bb4c3-132">Δώστε ένα όνομα για τον εμπλουτισμό και ένα όνομα για την οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="bb4c3-133">Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="bb4c3-134">Ρύθμιση παραμέτρων της σύνδεσης για το Experian</span><span class="sxs-lookup"><span data-stu-id="bb4c3-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="bb4c3-135">Για να ρυθμίσετε τις παραμέτρους των συνδέσεων, θα πρέπει να είστε διαχειριστής.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="bb4c3-136">Επιλέξτε **Προσθήκη σύνδεσης** κατά τη ρύθμιση παραμέτρων ενός εμπλουτισμού *ή* μεταβείτε στο **Διαχειριστής** > **Συνδέσεις** και επιλέξτε **Ρύθμιση** στο πλακίδιο Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="bb4c3-137">Επιλέξτε **Γρήγορα αποτελέσματα**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="bb4c3-138">Πληκτρολογήστε ένα όνομα για τη σύνδεση στο πλαίσιο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="bb4c3-139">Πληκτρολογήστε έγκυρο αναγνωριστικό χρήστη, αναγνωριστικό μέρους και αριθμό μοντέλου για τον λογαριασμό ασφαλούς μεταφοράς Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="bb4c3-140">Ελέγξτε και δώστε τη συγκατάθεσή σας για το **Απόρρητο και τη συμμόρφωση των δεδομένων** επιλέγοντας το πλαίσιο ελέγχου **Συμφωνώ**</span><span class="sxs-lookup"><span data-stu-id="bb4c3-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="bb4c3-141">Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="bb4c3-142">Αφού ολοκληρώσετε την επαλήθευση, επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Τμήμα απραθύρου ρύθμισης παραμέτρων σύνδεσης Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="bb4c3-144">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="bb4c3-144">Enrichment results</span></span>

<span data-ttu-id="bb4c3-145">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bb4c3-146">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb4c3-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb4c3-147">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων των πελατών σας και τις διαδικασίες εμπλουτισμού που έχουν δημιουργηθεί για το λογαριασμό σας από το Experian.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="bb4c3-148">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα δεδομένα του προφίλ πελατών που έχουν εμπλουτιστεί πρόσφατα κάτω από την επιλογή **Οι εμπλουτισμοί μου**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bb4c3-149">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bb4c3-150">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb4c3-151">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="bb4c3-151">Next steps</span></span>

<span data-ttu-id="bb4c3-152">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bb4c3-153">Δημιουργήστε [τμήματα](segments.md), [μέτρα](measures.md) και κάντε [εξαγωγή των δεδομένων](export-destinations.md) για την παροχή εξατομικευμένων εμπειριών στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb4c3-154">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="bb4c3-154">Data privacy and compliance</span></span>

<span data-ttu-id="bb4c3-155">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στη Experian, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb4c3-156">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι η Experian πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb4c3-157">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb4c3-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bb4c3-158">Ο διαχειριστής Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον εμπλουτισό οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="bb4c3-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
