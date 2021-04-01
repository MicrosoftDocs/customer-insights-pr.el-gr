---
title: Εξαγωγή δεδομένων Customer Insights σε κεντρικούς υπολογιστές SFTP
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης σε έναν κεντρικό υπολογιστή SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598385"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="aa94d-103">Σύνδεση για SFTP (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="aa94d-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="aa94d-104">Χρησιμοποιήστε τα δεδομένα πελατών σας σε εφαρμογές τρίτων κατασκευαστών, εξάγοντάς σε έναν κεντρικό υπολογιστή πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP).</span><span class="sxs-lookup"><span data-stu-id="aa94d-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa94d-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="aa94d-105">Prerequisites</span></span>

- <span data-ttu-id="aa94d-106">Διαθεσιμότητα κεντρικού υπολογιστή SFTP και των αντίστοιχων διαπιστευτηρίων.</span><span class="sxs-lookup"><span data-stu-id="aa94d-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="aa94d-107">Σύνδεση στο SFTP</span><span class="sxs-lookup"><span data-stu-id="aa94d-107">Connect to SFTP</span></span>

1. <span data-ttu-id="aa94d-108">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="aa94d-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="aa94d-109">Στο μενού **SFTP**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="aa94d-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="aa94d-110">Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="aa94d-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="aa94d-111">Παρέχετε ένα **Όνομα χρήστη**, έναν **Κωδικό πρόσβασης**, ένα **Όνομα κεντρικού υπολογιστή** και έναν **Φάκελο εξαγωγής** για τον λογαριασμό SFTP.</span><span class="sxs-lookup"><span data-stu-id="aa94d-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="aa94d-112">Επιλέξτε **Επαλήθευση** για να δοκιμάσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="aa94d-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="aa94d-113">Μετά από την επιτυχή επαλήθευση, επιλέξτε εάν θέλετε να εξαγάγετε τα δεδομένα σας **συμπιεσμένα σε Gzip** ή **ασυμπίεστα** και επιλέξτε τον **οριοθέτη πεδίων** για τα αρχεία που έχουν εξαχθεί.</span><span class="sxs-lookup"><span data-stu-id="aa94d-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="aa94d-114">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="aa94d-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="aa94d-115">Επιλέξτε **Επόμενο** για να ξεκινήσετε τη ρύθμιση παραμέτρων της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="aa94d-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="aa94d-116">Ρύθμιση παραμέτρων της εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="aa94d-116">Configure the export</span></span>

1. <span data-ttu-id="aa94d-117">Επιλέξτε τις οντότητες, για παράδειγμα τμήματα, που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="aa94d-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="aa94d-118">Κάθε επιλεγμένη οντότητα θα είναι έως και πέντε αρχεία εξόδου κατά την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="aa94d-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="aa94d-119">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="aa94d-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="aa94d-120">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="aa94d-120">Export the data</span></span>

<span data-ttu-id="aa94d-121">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aa94d-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="aa94d-122">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aa94d-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="aa94d-123">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="aa94d-123">Known limitations</span></span>

- <span data-ttu-id="aa94d-124">Ο χρόνος εκτέλεσης μιας εξαγωγής εξαρτάται από την απόδοση του συστήματός σας.</span><span class="sxs-lookup"><span data-stu-id="aa94d-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="aa94d-125">Συνιστούμε δύο πυρήνες CPU και 1 Gb μνήμης ως ελάχιστη διαμόρφωση του διακομιστή σας.</span><span class="sxs-lookup"><span data-stu-id="aa94d-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="aa94d-126">Η εξαγωγή οντοτήτων με έως 100 εκατομμύρια προφίλ πελατών μπορεί να διαρκέσει 90 λεπτά με τη χρήση της συνιστώμενης ελάχιστης διαμόρφωσης δύο πυρήνων CPU και 1 Gb μνήμης.</span><span class="sxs-lookup"><span data-stu-id="aa94d-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aa94d-127">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="aa94d-127">Data privacy and compliance</span></span>

<span data-ttu-id="aa94d-128">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα μέσω SFTP, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="aa94d-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aa94d-129">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι ο προορισμός εξαγωγής πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="aa94d-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="aa94d-130">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="aa94d-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="aa94d-131">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="aa94d-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]