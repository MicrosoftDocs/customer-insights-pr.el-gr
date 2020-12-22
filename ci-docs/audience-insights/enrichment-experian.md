---
title: Εμπλουτισμός με τον εμπλουτισμό τρίτου μέρους Experian
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό τρίτου μέρους της Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668812"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f4a71-103">Εμπλουτισμός προφίλ πελατών με δημογραφικά στοιχεία από το Experian (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="f4a71-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f4a71-104">Το Experian είναι παγκόσμιος ηγέτης στις υπηρεσίες αναφοράς και μάρκετινγκ για τους καταναλωτές και τις επιχειρήσεις.</span><span class="sxs-lookup"><span data-stu-id="f4a71-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f4a71-105">Με τις υπηρεσίες εμπλουτισμού δεδομένων του Experian, μπορείτε να δημιουργήσετε μια βαθύτερη κατανόηση των πελατών σας εμπλουτίζοντας τα προφίλ των πελατών σας με δημογραφικά δεδομένα, όπως το μέγεθος του νοικοκυριού, τα εισοδήματα και πολλά άλλα.</span><span class="sxs-lookup"><span data-stu-id="f4a71-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4a71-106">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="f4a71-106">Prerequisites</span></span>

<span data-ttu-id="f4a71-107">Για να ρυθμίσετε το Experian, πρέπει να πληρούνται οι παρακάτω προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="f4a71-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f4a71-108">Έχετε μια ενεργή συνδρομή στο Experian.</span><span class="sxs-lookup"><span data-stu-id="f4a71-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f4a71-109">Για να λάβετε μια συνδρομή, [επικοινωνήστε με το Experian](https://www.experian.com/marketing-services/contact) απευθείας.</span><span class="sxs-lookup"><span data-stu-id="f4a71-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f4a71-110">[Μάθετε περισσότερα σχετικά με τον εμπλουτισμό δεδομένων Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f4a71-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f4a71-111">Διαθέτετε το αναγνωριστικό χρήστη, το αναγνωριστικό μέρους και τον αριθμό μοντέλου για τον λογαριασμό σας SSH-enabled Secure Transport (ST) τον οποίο το Experian δημιούργησε για εσάς.</span><span class="sxs-lookup"><span data-stu-id="f4a71-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f4a71-112">Διαθέτετε δικαιώματα [Διαχειριστή](permissions.md#administrator) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="f4a71-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f4a71-113">Ρύθμιση παραμέτρων</span><span class="sxs-lookup"><span data-stu-id="f4a71-113">Configuration</span></span>

1. <span data-ttu-id="f4a71-114">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.</span><span class="sxs-lookup"><span data-stu-id="f4a71-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f4a71-115">Επιλέξτε **Εμπλουτισμός των δεδομένων μου** στο πλακίδιο Experian.</span><span class="sxs-lookup"><span data-stu-id="f4a71-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4a71-116">![Πλακίδιο Experian](media/experian-tile.png "Πλακίδιο Experian")</span><span class="sxs-lookup"><span data-stu-id="f4a71-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f4a71-117">Επιλέξτε **Έναρξη** και καταχωρίστε το αναγνωριστικό χρήστη, το αναγνωριστικό μέρους και τον αριθμό μοντέλου για τον λογαριασμό σας στο Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="f4a71-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f4a71-118">Ελέγξτε και δώστε τη συγκατάθεσή σας για το **Απόρρητο και τη συμμόρφωση των δεδομένων** επιλέγοντας το πλαίσιο ελέγχου **Συμφωνώ**.</span><span class="sxs-lookup"><span data-stu-id="f4a71-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f4a71-119">Επιβεβαιώστε όλες τις καταχωρίσεις επιλέγοντας **Εφαρμογή**.</span><span class="sxs-lookup"><span data-stu-id="f4a71-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f4a71-120">Αντιστοίχιση πεδίων</span><span class="sxs-lookup"><span data-stu-id="f4a71-120">Map your fields</span></span>

1. <span data-ttu-id="f4a71-121">Επιλέξτε **Προσθήκη δεδομένων** και επιλέξτε τα βασικά αναγνωριστικά σας από τα στοιχεία **Όνομα και διεύθυνση**, **Ηλεκτρονικό ταχυδρομείο** ή **Τηλέφωνο** για αποστολή στο Experian για επίλυση ταυτοποίησης.</span><span class="sxs-lookup"><span data-stu-id="f4a71-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f4a71-122">Περισσότερα βασικά χαρακτηριστικά αναγνωριστικού που στάλθηκαν στο Experian πιθανών αποδίδουν υψηλότερο ποσοστό αντιστοιχίας.</span><span class="sxs-lookup"><span data-stu-id="f4a71-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f4a71-123">Επιλέξτε **Επόμενο** και αντιστοιχίστε τα αντίστοιχα χαρακτηριστικά από την ενοποιημένη οντότητα "πελάτης" για τα επιλεγμένα πεδία αναγνωριστικού κλειδιού.</span><span class="sxs-lookup"><span data-stu-id="f4a71-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f4a71-124">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε τυχόν πρόσθετα χαρακτηριστικά που θα θέλατε να στείλετε στο Experian.</span><span class="sxs-lookup"><span data-stu-id="f4a71-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f4a71-125">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε την αντιστοίχιση πεδίου.</span><span class="sxs-lookup"><span data-stu-id="f4a71-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4a71-126">![Αντιστοίχιση πεδίων Experian](media/experian-field-mapping.png "Αντιστοίχιση πεδίων Experian")</span><span class="sxs-lookup"><span data-stu-id="f4a71-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f4a71-127">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="f4a71-127">Enrichment results</span></span>

<span data-ttu-id="f4a71-128">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="f4a71-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f4a71-129">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f4a71-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4a71-130">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων των πελατών σας και τις διαδικασίες εμπλουτισμού που έχουν δημιουργηθεί για το λογαριασμό σας από το Experian.</span><span class="sxs-lookup"><span data-stu-id="f4a71-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f4a71-131">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα δεδομένα του προφίλ πελατών που έχουν εμπλουτιστεί πρόσφατα κάτω από την επιλογή **Οι εμπλουτισμοί μου**.</span><span class="sxs-lookup"><span data-stu-id="f4a71-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f4a71-132">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="f4a71-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f4a71-133">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="f4a71-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4a71-134">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="f4a71-134">Next steps</span></span>

<span data-ttu-id="f4a71-135">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="f4a71-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f4a71-136">Δημιουργήστε [τμήματα](segments.md), [μέτρα](measures.md) και κάντε [εξαγωγή των δεδομένων](export-destinations.md) για την παροχή εξατομικευμένων εμπειριών στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="f4a71-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f4a71-137">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="f4a71-137">Data privacy and compliance</span></span>

<span data-ttu-id="f4a71-138">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στη Experian, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="f4a71-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f4a71-139">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι η Experian πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="f4a71-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f4a71-140">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f4a71-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f4a71-141">Ο διαχειριστής Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον εμπλουτισό οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="f4a71-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
