---
title: Εμπλουτισμός με τον εμπλουτισμό τρίτου μέρους HERE Technologies
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτου μέρους της HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896051"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="b54b7-103">Εμπλουτισμός προφίλ πελατών με την HERE Technologies (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="b54b7-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="b54b7-104">Η HERE Technologies είναι μια εταιρεία πλατφόρμας θέσης η οποία παρέχει δεδομένα και υπηρεσίες με επίκεντρο την τοποθεσία.</span><span class="sxs-lookup"><span data-stu-id="b54b7-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="b54b7-105">Με τις υπηρεσίες εμπλουτισμού δεδομένων του HERE Technologies, μπορείτε να δημιουργήσετε μια ακριβέστερη κατανόηση τοποθεσίας για τους πελάτες σας με την κανονικοποίηση διευθύνσεων, την εξαγωγή γεωγραφικού πλάτους και μήκους και άλλα πολλά.</span><span class="sxs-lookup"><span data-stu-id="b54b7-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b54b7-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="b54b7-106">Prerequisites</span></span>

<span data-ttu-id="b54b7-107">Για να ρυθμίσετε τις παραμέτρους του εμπλουτισμού HERE Technologies, θα πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="b54b7-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b54b7-108">Έχετε ενεργή συνδρομή HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="b54b7-109">Για να λάβετε μια συνδρομή, μπορείτε να [εγγραφείτε εδώ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ή να [επικοινωνήσετε νε τη HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="b54b7-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="b54b7-110">Μάθετε περισσότερα σχετικά με τον εμπλουτισμό τοποθεσίας της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="b54b7-111">Υπάρχει διαθέσιμη μια [σύνδεση](connections.md) HERE *ή* έχετε δικαιώματα [διαχειριστή](permissions.md#administrator) και το κλειδί API της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b54b7-112">Ρύθμιση παραμέτρων του εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="b54b7-112">Configure the enrichment</span></span>

1. <span data-ttu-id="b54b7-113">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="b54b7-114">Επιλέξτε **Εμπλουτισμός των δεδομένω μου** στο πλακίδιο HERE Technologies και επιλέξτε **Γρήγορα αποτελέσματα**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54b7-115">![Πλακίδιο HERE Technologies](media/HERE-tile.png "Πλακίδιο HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="b54b7-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="b54b7-116">Επιλέξτε μια [σύνδεση](connections.md) από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="b54b7-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="b54b7-117">Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="b54b7-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="b54b7-118">Εάν είστε ένας διαχειριστής, μπορείτε να δημιουργήσετε μια σύνδεση επιλέγοντας **Προσθήκη σύνδεσης**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="b54b7-119">Επιλέξτε **HERE Technologies** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="b54b7-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="b54b7-120">Επιλέξτε **Σύνδεση με HERE Technologies** για να επιβεβαιώσετε την επιλογή.</span><span class="sxs-lookup"><span data-stu-id="b54b7-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="b54b7-121">Επιλέξτε **Επόμενο** και επιλέξτε το **σύνολο δεδομένων πελατών** που θέλετε να εμπλουτίσετε με δεδομένα τοποθεσίας από τη HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="b54b7-122">Μπορείτε να επιλέξετε την οντότητα **Πελάτης** για να εμπλουτίσετε όλα τα προφίλ πελατών σας ή να επιλέξετε μια οντότητα τμήματος αγοράς για να εμπλουτίσετε μόνο τα προφίλ πελατών που περιέχονται σε αυτό το τμήμα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="b54b7-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Στιγμιότυπο οθόνης κατά την επιλογή του συνόλου δεδομένων πελάτη.":::

1. <span data-ttu-id="b54b7-124">Επιλέξτε εάν θέλετε να αντιστοιχίσετε τα πεδία με την κύρια ή/και τη δευτερεύουσα διεύθυνση.</span><span class="sxs-lookup"><span data-stu-id="b54b7-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="b54b7-125">Μπορείτε να καθορίσετε μια αντιστοίχιση πεδίων και για τις δύο διευθύνσεις και να εμπλουτίσετε τα προφίλ και για τις δύο διευθύνσεις ξεχωριστά.</span><span class="sxs-lookup"><span data-stu-id="b54b7-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="b54b7-126">Για παράδειγμα, εάν υπάρχει διεύθυνση οικίας και επιχείρησης.</span><span class="sxs-lookup"><span data-stu-id="b54b7-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="b54b7-127">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-127">Select **Next**.</span></span>

1. <span data-ttu-id="b54b7-128">Καθορίστε ποια πεδία από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιηθούν για την αναζήτηση αντιστοίχισης δεδομένων τοποθεσίας από τη HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="b54b7-129">Τα πεδία **Οδός 1** και **Ταχυδρομικός Κώδικας** είναι απαραίτητα για την επιλεγμένη κύρια ή/και δευτερεύουσα διεύθυνση.</span><span class="sxs-lookup"><span data-stu-id="b54b7-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="b54b7-130">Για μεγαλύτερη ακρίβεια αντιστοίχισης, είναι δυνατή η προσθήκη περισσότερων πεδίων.</span><span class="sxs-lookup"><span data-stu-id="b54b7-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54b7-131">![Σελίδα ρύθμισης παραμέτρων εμπλουτισμού HERE Technologies](media/enrichment-HERE-configuration.png "Σελίδα ρύθμισης παραμέτρων εμπλουτισμού HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="b54b7-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="b54b7-132">Επιλέξτε **Επόμενο** για να ολοκληρώσετε την αντιστοίχιση πεδίων.</span><span class="sxs-lookup"><span data-stu-id="b54b7-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b54b7-133">Πληκτρολογήστε ένα όνομα για τον εμπλουτισμό.</span><span class="sxs-lookup"><span data-stu-id="b54b7-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="b54b7-134">1. Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.</span><span class="sxs-lookup"><span data-stu-id="b54b7-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="b54b7-135">Ρύθμιση παραμέτρων της σύνδεσης για τη HERE technologies</span><span class="sxs-lookup"><span data-stu-id="b54b7-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="b54b7-136">Για να ρυθμίσετε τις παραμέτρους των συνδέσεων, θα πρέπει να είστε διαχειριστής.</span><span class="sxs-lookup"><span data-stu-id="b54b7-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b54b7-137">Επιλέξτε **Προσθήκη σύνδεσης** κατά τη ρύθμιση παραμέτρων ενός εμπλουτισμού *ή* μεταβείτε στο **Διαχειριστής** > **Συνδέσεις** και επιλέξτε **Ρύθμιση** στο πλακίδιο HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="b54b7-138">Πληκτρολογήστε ένα όνομα για τη σύνδεση στο πλαίσιο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b54b7-139">Δώστε ένα έγκυρο κλειδί API για τη HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="b54b7-140">Ελέγξτε και δώστε τη συγκατάθεσή σας για το **Απόρρητο και τη συμμόρφωση των δεδομένων** επιλέγοντας το πλαίσιο ελέγχου **Συμφωνώ**</span><span class="sxs-lookup"><span data-stu-id="b54b7-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="b54b7-141">Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="b54b7-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b54b7-142">Αφού ολοκληρώσετε την επαλήθευση, επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54b7-143">![Σελίδα ρύθμισης παραμέτρων σύνδεσης HERE Technologies](media/enrichment-HERE-connection.png "Σελίδα ρύθμισης παραμέτρων σύνδεσης HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="b54b7-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b54b7-144">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="b54b7-144">Enrichment results</span></span>

<span data-ttu-id="b54b7-145">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b54b7-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b54b7-146">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b54b7-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b54b7-147">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων των πελατών σας και τους χρόνους απόκρισης API της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b54b7-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="b54b7-148">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα δεδομένα του προφίλ πελατών που έχουν εμπλουτιστεί πρόσφατα κάτω από την επιλογή **Οι εμπλουτισμοί μου**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b54b7-149">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="b54b7-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b54b7-150">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="b54b7-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b54b7-151">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="b54b7-151">Next steps</span></span>

<span data-ttu-id="b54b7-152">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="b54b7-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b54b7-153">Δημιουργήστε [τμήματα](segments.md), [μέτρα](measures.md) και κάντε [εξαγωγή των δεδομένων](export-destinations.md) για την παροχή εξατομικευμένων εμπειριών στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="b54b7-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b54b7-154">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="b54b7-154">Data privacy and compliance</span></span>

<span data-ttu-id="b54b7-155">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στη HERE Technologies, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="b54b7-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b54b7-156">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι η HERE Technologies πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="b54b7-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b54b7-157">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b54b7-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b54b7-158">Ο διαχειριστής Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον εμπλουτισό οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="b54b7-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
