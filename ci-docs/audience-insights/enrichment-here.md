---
title: Εμπλουτισμός με τον εμπλουτισμό τρίτου μέρους HERE Technologies
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτου μέρους της HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668678"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="b2397-103">Εμπλουτισμός προφίλ πελατών με την HERE Technologies (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="b2397-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="b2397-104">Η HERE Technologies είναι μια εταιρεία πλατφόρμας θέσης η οποία παρέχει δεδομένα και υπηρεσίες με επίκεντρο την τοποθεσία.</span><span class="sxs-lookup"><span data-stu-id="b2397-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="b2397-105">Με τις υπηρεσίες εμπλουτισμού δεδομένων του HERE Technologies, μπορείτε να δημιουργήσετε μια ακριβέστερη κατανόηση τοποθεσίας για τους πελάτες σας με την κανονικοποίηση διευθύνσεων, την εξαγωγή γεωγραφικού πλάτους και μήκους και άλλα πολλά.</span><span class="sxs-lookup"><span data-stu-id="b2397-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2397-106">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="b2397-106">Prerequisites</span></span>

<span data-ttu-id="b2397-107">Για να ρυθμίσετε τις παραμέτρους του εμπλουτισμού HERE Technologies, θα πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="b2397-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b2397-108">Έχετε ενεργή συνδρομή HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b2397-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="b2397-109">Για να λάβετε μια συνδρομή, μπορείτε να [εγγραφείτε εδώ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ή να [επικοινωνήσετε νε τη HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="b2397-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="b2397-110">Μάθετε περισσότερα σχετικά με τον εμπλουτισμό τοποθεσίας της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b2397-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="b2397-111">Έχετε το κλειδί API της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b2397-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="b2397-112">Έχετε δικαιώματα [Διαχειριστή](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="b2397-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="b2397-113">Ρύθμιση παραμέτρων</span><span class="sxs-lookup"><span data-stu-id="b2397-113">Configuration</span></span>

1. <span data-ttu-id="b2397-114">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός**.</span><span class="sxs-lookup"><span data-stu-id="b2397-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b2397-115">Επιλέξτε **Εμπλουτισμός των δεδομένων μου** στο πλακίδιο της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b2397-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b2397-116">![Πλακίδιο HERE Technologies](media/HERE-tile.png "Πλακίδιο HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="b2397-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="b2397-117">Εισαγάγετε ένα ενεργό **κλειδί της HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="b2397-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="b2397-118">Ελέγξτε και δώστε τη συγκατάθεσή σας για το **Απόρρητο και τη συμμόρφωση των δεδομένων** επιλέγοντας το πλαίσιο ελέγχου **Συμφωνώ**.</span><span class="sxs-lookup"><span data-stu-id="b2397-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="b2397-119">Επιβεβαιώστε και τις δύο εισόδους επιλέγοντας **Σύνδεση στη HERE**.</span><span class="sxs-lookup"><span data-stu-id="b2397-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="b2397-120">Επιλέξτε **Προσθήκη δεδομένων** και επιλέξτε εάν θέλετε να αντιστοιχίσετε τα πεδία με την κύρια ή/και τη δευτερεύουσα διεύθυνση.</span><span class="sxs-lookup"><span data-stu-id="b2397-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="b2397-121">Μπορείτε να καθορίσετε μια αντιστοίχιση πεδίου για τις δύο διευθύνσεις (για παράδειγμα, μια διεύθυνση οικίας και μια επαγγελματική διεύθυνση) και να εμπλουτίσετε τα προφίλ και για τις δύο διευθύνσεις ξεχωριστά.</span><span class="sxs-lookup"><span data-stu-id="b2397-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="b2397-122">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="b2397-122">Select **Next**.</span></span>

1. <span data-ttu-id="b2397-123">Καθορίστε ποια πεδία από τα ενοποιημένα προφίλ σας θα πρέπει να χρησιμοποιηθούν για την αναζήτηση αντιστοίχισης δεδομένων τοποθεσίας από τη HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b2397-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="b2397-124">Τα πεδία **Οδός 1** και **Ταχυδρομικός Κώδικας** είναι απαραίτητα για την επιλεγμένη κύρια ή/και δευτερεύουσα διεύθυνση.</span><span class="sxs-lookup"><span data-stu-id="b2397-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="b2397-125">Για μεγαλύτερη ακρίβεια αντιστοίχισης, είναι δυνατή η προσθήκη περισσότερων πεδίων.</span><span class="sxs-lookup"><span data-stu-id="b2397-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b2397-126">![Σελίδα ρύθμισης παραμέτρων εμπλουτισμού HERE Technologies](media/enrichment-HERE-configuration.png "Σελίδα ρύθμισης παραμέτρων εμπλουτισμού HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="b2397-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="b2397-127">Επιλέξτε **Εφαρμογή** για να ολοκληρώσετε την αντιστοίχιση πεδίου.</span><span class="sxs-lookup"><span data-stu-id="b2397-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b2397-128">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="b2397-128">Enrichment results</span></span>

<span data-ttu-id="b2397-129">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="b2397-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b2397-130">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b2397-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b2397-131">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων των πελατών σας και τους χρόνους απόκρισης API της HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="b2397-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="b2397-132">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα δεδομένα του προφίλ πελατών που έχουν εμπλουτιστεί πρόσφατα κάτω από την επιλογή **Οι εμπλουτισμοί μου**.</span><span class="sxs-lookup"><span data-stu-id="b2397-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b2397-133">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="b2397-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b2397-134">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="b2397-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2397-135">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="b2397-135">Next steps</span></span>

<span data-ttu-id="b2397-136">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="b2397-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b2397-137">Δημιουργήστε [τμήματα](segments.md), [μέτρα](measures.md) και κάντε [εξαγωγή των δεδομένων](export-destinations.md) για την παροχή εξατομικευμένων εμπειριών στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="b2397-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b2397-138">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="b2397-138">Data privacy and compliance</span></span>

<span data-ttu-id="b2397-139">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στη HERE Technologies, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="b2397-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b2397-140">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι η HERE Technologies πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="b2397-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b2397-141">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b2397-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b2397-142">Ο διαχειριστής Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον εμπλουτισό οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="b2397-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
