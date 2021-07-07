---
title: Εξαγωγή δεδομένων του Customer Insights στο Salesforce Marketing Cloud
description: Μάθετε πώς να ρυθμίζετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314615"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="46e8a-103">Εξαγωγή τμημάτων και άλλων δεδομένων στο Salesforce Marketing Cloud (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="46e8a-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="46e8a-104">Χρησιμοποιήστε τα δεδομένα πελατών σας στο Salesforce Marketing Cloud εξαγάγοντάς τα μέσω μιας θέσης πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP).</span><span class="sxs-lookup"><span data-stu-id="46e8a-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="46e8a-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="46e8a-105">Prerequisites for connection</span></span>

- <span data-ttu-id="46e8a-106">Διαθεσιμότητα κεντρικού υπολογιστή SFTP και των αντίστοιχων διαπιστευτηρίων διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="46e8a-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="46e8a-107">Πώς να ρυθμίσετε θέσεις SFTP για το Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="46e8a-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="46e8a-108">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="46e8a-108">Known limitations</span></span>

- <span data-ttu-id="46e8a-109">Ο χρόνος εκτέλεσης μιας εξαγωγής εξαρτάται από την απόδοση του συστήματός σας.</span><span class="sxs-lookup"><span data-stu-id="46e8a-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="46e8a-110">Συνιστούμε δύο πυρήνες CPU και 1 Gb μνήμης ως ελάχιστη διαμόρφωση του διακομιστή σας.</span><span class="sxs-lookup"><span data-stu-id="46e8a-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="46e8a-111">Η εξαγωγή οντοτήτων με έως 100 εκατομμύρια προφίλ πελατών μπορεί να διαρκέσει 90 λεπτά όταν χρησιμοποιείται η συνιστώμενη ελάχιστη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="46e8a-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="46e8a-112">Ρύθμιση της σύνδεσης στο Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="46e8a-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="46e8a-113">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="46e8a-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="46e8a-114">Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Salesforce Marketing Cloud**, για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="46e8a-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="46e8a-115">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="46e8a-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="46e8a-116">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46e8a-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="46e8a-117">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="46e8a-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="46e8a-118">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46e8a-118">Choose who can use this connection.</span></span> <span data-ttu-id="46e8a-119">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι Διαχειριστές.</span><span class="sxs-lookup"><span data-stu-id="46e8a-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="46e8a-120">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="46e8a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="46e8a-121">Παρέχετε ένα **Όνομα χρήστη**, έναν **Κωδικό πρόσβασης**, ένα **Όνομα κεντρικού υπολογιστή** και έναν **Φάκελο εξαγωγής** για τον λογαριασμό SFTP.</span><span class="sxs-lookup"><span data-stu-id="46e8a-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="46e8a-122">Επιλέξτε **Επαλήθευση** για να δοκιμάσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46e8a-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="46e8a-123">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="46e8a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46e8a-124">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="46e8a-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="46e8a-125">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="46e8a-125">Configure an export</span></span>

<span data-ttu-id="46e8a-126">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="46e8a-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="46e8a-127">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="46e8a-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="46e8a-128">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="46e8a-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="46e8a-129">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="46e8a-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="46e8a-130">Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα SFTP.</span><span class="sxs-lookup"><span data-stu-id="46e8a-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="46e8a-131">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="46e8a-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="46e8a-132">Επιλέξτε εάν θέλετε να εξαγάγετε τα δεδομένα σας στο πεδίο **Gzipped** ή **Χωρίς συμπίεση** και τον **οριοθέτη πεδίων** για τα αρχεία που έχουν εξαχθεί.</span><span class="sxs-lookup"><span data-stu-id="46e8a-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="46e8a-133">Επιλέξτε τις οντότητες, για παράδειγμα τμήματα, που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="46e8a-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46e8a-134">Κάθε επιλεγμένη οντότητα θα διαιρεθεί σε έως και πέντε αρχεία εξόδου κατά την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="46e8a-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="46e8a-135">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="46e8a-135">Select **Save**.</span></span>

<span data-ttu-id="46e8a-136">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="46e8a-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="46e8a-137">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="46e8a-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="46e8a-138">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="46e8a-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="46e8a-139">Εισαγωγή δεδομένων του Customer Insights από τη θέση SFTP στο Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="46e8a-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="46e8a-140">Δημιουργήστε [επεκτάσεις δεδομένων στο Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) για να εισαγάγετε το αρχείο δεδομένων Customer Insights από τη θέση SFTP.</span><span class="sxs-lookup"><span data-stu-id="46e8a-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="46e8a-141">[Εισαγάγετε τα δεδομένα από τη θέση SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) στην επέκταση δεδομένων του Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="46e8a-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="46e8a-142">Ρυθμίστε την αυτοματοποίηση, ώστε να εισαγάγετε τα δεδομένα στις επεκτάσεις δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="46e8a-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="46e8a-143">Μάθετε περισσότερα σχετικά με [τις αυτοματοποιήσεις απόθεσης αρχείων και τις προγραμματισμένες αυτοματοποιήσεις](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="46e8a-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="46e8a-144">Καθορίστε [μια αυτοματοποίηση απόθεσης αρχείων](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)ή μια [προγραμματισμένη αυτοματοποίηση](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="46e8a-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="46e8a-145">Ακολουθεί ένα παράδειγμα [αυτοματοποίησης με SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="46e8a-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46e8a-146">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="46e8a-146">Data privacy and compliance</span></span>

<span data-ttu-id="46e8a-147">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα μέσω SFTP, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="46e8a-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46e8a-148">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι ο προορισμός εξαγωγής πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="46e8a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="46e8a-149">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="46e8a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="46e8a-150">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="46e8a-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
