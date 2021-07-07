---
title: Εμπλουτισμός με εμπλουτισμού τρίτων Experian
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτων Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309820"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="d7c73-103">Εμπλουτισμός προφίλ πελατών με δημογραφικά στοιχεία από το Experian (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="d7c73-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="d7c73-104">H Experian είναι μια παγκοσμίως κορυφαία εταιρεία υπηρεσιών αναφορών και μάρκετινγκ για θέματα πιστώσεων πελατών και επιχειρήσεων.</span><span class="sxs-lookup"><span data-stu-id="d7c73-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="d7c73-105">Με τις υπηρεσίες εμπλουτισμού δεδομένων της υπηρεσίας Experian, μπορείτε να κατανοήσετε καλύτερα τους πελάτες σας εμπλουτίζοντας τα προφίλ των πελατών σας με δημογραφικά δεδομένα, όπως μέγεθος νυκοκοιριού, εισόδημα και άλλα.</span><span class="sxs-lookup"><span data-stu-id="d7c73-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7c73-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="d7c73-106">Prerequisites</span></span>

<span data-ttu-id="d7c73-107">Για την διαμόρφωση του Experian, πρέπει να πληρούνται οι παρακάτω προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="d7c73-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d7c73-108">Πρέπει να έχετε ενεργή συνδρομή στο Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-108">You have an active Experian subscription.</span></span> <span data-ttu-id="d7c73-109">Για να αποκτήσετε μια συνδρομή, [επικοινωνήστε απευθείας με την Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="d7c73-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="d7c73-110">[Μάθετε περισσότερα σχετικά με τον εμπλουτισμό δεδομένων της Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="d7c73-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="d7c73-111">Μια σύνδεση Experian έχει ήδη ρυθμιστεί από έναν διαχειριστή *ή* έχετε δικαιώματα [διαχειριστή](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="d7c73-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="d7c73-112">Χρειάζεστε επίσης το αναγνωριστικό χρήστη, το αναγνωριστικό μέρους και τον αριθμό μοντέλου για το λογαριασμό σας Secure Transport (ST) με δυνατότητα SSH που δημιούγησε η Experian για εσάς.</span><span class="sxs-lookup"><span data-stu-id="d7c73-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="d7c73-113">Υποστηριζόμενες χώρες/περιοχές</span><span class="sxs-lookup"><span data-stu-id="d7c73-113">Supported countries/regions</span></span>

<span data-ttu-id="d7c73-114">Προς το παρόν, υποστηρίζουμε τον εμπλουτισμό των προφίλ πελατών μόνο στις Ηνωμένες Πολιτείες.</span><span class="sxs-lookup"><span data-stu-id="d7c73-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d7c73-115">Ρύθμιση παραμέτρων του εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="d7c73-115">Configure the enrichment</span></span>

1. <span data-ttu-id="d7c73-116">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="d7c73-117">Επιλέξτε **Εμπλουτισμός των δεδομένων μου** στο πλακίδιο Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d7c73-118">![Experian πλακίδια](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="d7c73-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="d7c73-119">Επιλέξτε μια [σύνδεση](connections.md) από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="d7c73-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="d7c73-120">Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="d7c73-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d7c73-121">Αν είστε διαχειριστής, μπορείτε να δημιουργήσετε μια σύνδεση επιλέγοντας **Προσθήκη σύνδεσης** και επιλέγοντας Experian από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="d7c73-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="d7c73-122">Επιλέξτε **Σύνδεση στο Experian**, για να επιβεβαιώσετε την επιλογή σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="d7c73-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="d7c73-123">Επιλέξτε **Επόμενο** και επιλέξτε το **Σύνολο δεδομένων πελατών** που θέλετε να εμπλουτίσετε με δημογραφικά στοιχεία από το Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="d7c73-124">Μπορείτε να επιλέξετε την οντότητα **Πελάτης** για να εμπλουτίσετε όλα τα προφίλ πελατών σας ή να επιλέξετε μια οντότητα τμήματος αγοράς για να εμπλουτίσετε μόνο τα προφίλ πελατών που περιέχονται σε αυτό το τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="d7c73-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Στιγμιότυπο οθόνης κατά την επιλογή του συνόλου δεδομένων πελάτη.":::

1. <span data-ttu-id="d7c73-126">Επιλέξτε **Επόμενο** και καθορίστε ποιος τύπος πεδίων από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιηθεί για την αναζήτηση δεδομένων που αντιστοιχούν σε δημογραφικά στοιχεία από το Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="d7c73-127">Απαιτείται τουλάχιστον ένα από τα πεδία **Όνομα και διεύθυνση** μ **Τηλέφωνο** ή **Ηλεκτρονικό ταχυδρομείο**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="d7c73-128">Για μεγαλύτερη ακρίβεια αντιστοίχισης, μπορούν να προστεθούν έως δύο άλλα πεδία.</span><span class="sxs-lookup"><span data-stu-id="d7c73-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="d7c73-129">Αυτή η επιλογή θα επηρεάσει τα πεδία αντιστοίχισης στα οποία έχετε πρόσβαση στο επόμενο βήμα.</span><span class="sxs-lookup"><span data-stu-id="d7c73-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="d7c73-130">Περισσότερα χαρακτηριστικά αναγνωριστικού κλειδιού που αποστέλλονται στο Experian αποδίδουν πιθανότατα υψηλότερο ποσοστό αντιστοίχισης.</span><span class="sxs-lookup"><span data-stu-id="d7c73-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="d7c73-131">Επιλέξτε **Επόμενο** για να αρχίσετε την αντιστοίχιση πεδίων.</span><span class="sxs-lookup"><span data-stu-id="d7c73-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="d7c73-132">Καθορίστε ποια πεδία από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιηθούν για την αναζήτηση δεδομένων που αντιστοιχούν σε δημογραφικά στοιχεία από το Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="d7c73-133">Τα υποχρεωτικά πεδία φέρουν σήμανση.</span><span class="sxs-lookup"><span data-stu-id="d7c73-133">Required fields are marked.</span></span>

1. <span data-ttu-id="d7c73-134">Δώστε ένα όνομα για τον εμπλουτισμό και ένα όνομα για την οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="d7c73-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="d7c73-135">Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.</span><span class="sxs-lookup"><span data-stu-id="d7c73-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="d7c73-136">Διαμόρωση της σύνδεσης για το Experian</span><span class="sxs-lookup"><span data-stu-id="d7c73-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="d7c73-137">Για να ρυθμίσετε τις παραμέτρους των συνδέσεων, θα πρέπει να είστε διαχειριστής.</span><span class="sxs-lookup"><span data-stu-id="d7c73-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d7c73-138">Επιλέξτε **Προσθήκη σύνδεσης κατά τη ρύθμιση** κατά τη διαμόρφωση ενός εμπλουτισμού *ή* μεταβείτε στο **Διαχείριση** > **Συνδέσεις** και επίλεξτε **Ρύθμιση** στο πλακίδιο Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="d7c73-139">Επιλέξτε **Γρήγορα αποτελέσματα**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="d7c73-140">Πληκτρολογήστε ένα όνομα για τη σύνδεση στο πλαίσιο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d7c73-141">Πληκτρολογήστε έγκυρο αναγνωριστικό χρήστη, αναγνωριστικό μέρους και αριθμό μοντέλου για τον λογαριασμό σας Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="d7c73-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="d7c73-142">Ελέγξτε και δώστε τη συγκατάθεσή σας για το **Απόρρητο δεδομένων και συμμόρφωση** επιλέγοντας **Συμφωνώ**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="d7c73-143">Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="d7c73-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d7c73-144">Αφού ολοκληρώσετε την επαλήθευση, επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Τμήμα παραθύρου διαμόρφωσης σύνδεσης του Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="d7c73-146">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="d7c73-146">Enrichment results</span></span>

<span data-ttu-id="d7c73-147">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="d7c73-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d7c73-148">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d7c73-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d7c73-149">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων των πελατών σας και τις διαδικασίες εμπλουτισμού που έχουν ρυθμιστεί για τον λογαριασμό σας από το Experian.</span><span class="sxs-lookup"><span data-stu-id="d7c73-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="d7c73-150">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα δεδομένα του προφίλ πελατών που έχουν εμπλουτιστεί πρόσφατα κάτω από την επιλογή **Οι εμπλουτισμοί μου**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="d7c73-151">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="d7c73-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d7c73-152">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="d7c73-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7c73-153">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="d7c73-153">Next steps</span></span>

<span data-ttu-id="d7c73-154">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="d7c73-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d7c73-155">Δημιουργήστε [τμήματα](segments.md)και [μέτρα](measures.md) και, επιπλέον, [εξαγάγετε τα δεδομένα](export-destinations.md) για να παραδώσετε εξατομικευμένες εμπειρίες στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="d7c73-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d7c73-156">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="d7c73-156">Data privacy and compliance</span></span>

<span data-ttu-id="d7c73-157">Όταν ενεργοποιείτε τη δυνατότητα μεταβίβασης δεδομένων από το Dynamics 365 Customer Insights προς το Experian, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβάνων πιθανώς ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="d7c73-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d7c73-158">Η Microsoft θα μεταφέρει τέτοιου είδους δεδομένα κατόπιν οδηγιών σας, αλλά εσείς φέρετε την ευθύνη για τη διασφάλιση ότι το Experian ανταποκρίνεται σε οποιεσδήποτε υποχρεώσεις ιδιωτικού απορρήτου ή ασφάλειας που ενδεχομένως έχετε.</span><span class="sxs-lookup"><span data-stu-id="d7c73-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d7c73-159">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d7c73-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d7c73-160">Ο διαχειριστής σας για το Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον εμπλουτισό ανά πάσα στιγμή, ώστε να διακοπεί η χρήση αυτής της λειτουργικότητας.</span><span class="sxs-lookup"><span data-stu-id="d7c73-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
