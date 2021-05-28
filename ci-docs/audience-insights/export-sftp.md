---
title: Εξαγωγή δεδομένων Customer Insights σε κεντρικούς υπολογιστές SFTP
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής σε μια τοποθεσία SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976893"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="94d8f-103">Εξαγωγή λιστών τμημάτων και άλλων δεδομένων σε SFTP (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="94d8f-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="94d8f-104">Χρησιμοποιήστε τα δεδομένα πελατών σας σε εφαρμογές τρίτων, εξάγοντάς τα σε μια θέση πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP).</span><span class="sxs-lookup"><span data-stu-id="94d8f-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="94d8f-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="94d8f-105">Prerequisites for connection</span></span>

- <span data-ttu-id="94d8f-106">Διαθεσιμότητα κεντρικού υπολογιστή SFTP και των αντίστοιχων διαπιστευτηρίων.</span><span class="sxs-lookup"><span data-stu-id="94d8f-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94d8f-107">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="94d8f-107">Known limitations</span></span>

- <span data-ttu-id="94d8f-108">Ο χρόνος εκτέλεσης μιας εξαγωγής εξαρτάται από την απόδοση του συστήματός σας.</span><span class="sxs-lookup"><span data-stu-id="94d8f-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="94d8f-109">Συνιστούμε δύο πυρήνες CPU και 1 Gb μνήμης ως ελάχιστη διαμόρφωση του διακομιστή σας.</span><span class="sxs-lookup"><span data-stu-id="94d8f-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="94d8f-110">Η εξαγωγή οντοτήτων με έως 100 εκατομμύρια προφίλ πελατών μπορεί να διαρκέσει 90 λεπτά με τη χρήση της συνιστώμενης ελάχιστης διαμόρφωσης δύο πυρήνων CPU και 1 Gb μνήμης.</span><span class="sxs-lookup"><span data-stu-id="94d8f-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="94d8f-111">Ρύθμιση σύνδεσης σε SFTP</span><span class="sxs-lookup"><span data-stu-id="94d8f-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="94d8f-112">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="94d8f-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="94d8f-113">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **SFTP** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="94d8f-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="94d8f-114">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="94d8f-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="94d8f-115">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="94d8f-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="94d8f-116">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="94d8f-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="94d8f-117">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="94d8f-117">Choose who can use this connection.</span></span> <span data-ttu-id="94d8f-118">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="94d8f-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="94d8f-119">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="94d8f-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="94d8f-120">Παρέχετε ένα **Όνομα χρήστη**, έναν **Κωδικό πρόσβασης**, ένα **Όνομα κεντρικού υπολογιστή** και έναν **Φάκελο εξαγωγής** για τον λογαριασμό SFTP.</span><span class="sxs-lookup"><span data-stu-id="94d8f-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="94d8f-121">Επιλέξτε **Επαλήθευση** για να δοκιμάσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="94d8f-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="94d8f-122">Επιλέξτε εάν θέλετε να εξαγάγετε τα δεδομένα σας στο πεδίο **Gzipped** ή **Χωρίς συμπίεση** και τον **οριοθέτη πεδίων** για τα αρχεία που έχουν εξαχθεί.</span><span class="sxs-lookup"><span data-stu-id="94d8f-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="94d8f-123">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="94d8f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94d8f-124">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="94d8f-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="94d8f-125">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="94d8f-125">Configure an export</span></span>

<span data-ttu-id="94d8f-126">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="94d8f-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="94d8f-127">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="94d8f-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="94d8f-128">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="94d8f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="94d8f-129">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="94d8f-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="94d8f-130">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα SFTP.</span><span class="sxs-lookup"><span data-stu-id="94d8f-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="94d8f-131">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="94d8f-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="94d8f-132">Επιλέξτε τις οντότητες, για παράδειγμα τμήματα, που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="94d8f-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="94d8f-133">Κάθε επιλεγμένη οντότητα θα διαιρεθεί σε έως και πέντε αρχεία εξόδου κατά την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="94d8f-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="94d8f-134">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="94d8f-134">Select **Save**.</span></span>

<span data-ttu-id="94d8f-135">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="94d8f-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="94d8f-136">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="94d8f-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94d8f-137">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="94d8f-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94d8f-138">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="94d8f-138">Data privacy and compliance</span></span>

<span data-ttu-id="94d8f-139">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα μέσω SFTP, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="94d8f-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94d8f-140">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι ο προορισμός εξαγωγής πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="94d8f-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="94d8f-141">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="94d8f-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94d8f-142">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="94d8f-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
