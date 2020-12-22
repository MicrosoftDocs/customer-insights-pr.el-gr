---
title: Εξαγωγή δεδομένων Customer Insights σε κεντρικούς υπολογιστές SFTP
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης σε έναν κεντρικό υπολογιστή SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643503"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="28065-103">Σύνδεση για SFTP (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="28065-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="28065-104">Χρησιμοποιήστε τα δεδομένα πελατών σας σε εφαρμογές τρίτων κατασκευαστών, εξάγοντάς σε έναν κεντρικό υπολογιστή πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP).</span><span class="sxs-lookup"><span data-stu-id="28065-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28065-105">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="28065-105">Prerequisites</span></span>

- <span data-ttu-id="28065-106">Διαθεσιμότητα ενός κεντρικού υπολογιστή SFTP και αντίστοιχα διαπιστευτήρια.</span><span class="sxs-lookup"><span data-stu-id="28065-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="28065-107">Σύνδεση στον SFTP</span><span class="sxs-lookup"><span data-stu-id="28065-107">Connect to SFTP</span></span>

1. <span data-ttu-id="28065-108">Μεταβείτε στα στοιχεία **Διαχειριστής** > **Εξαγωγή προορισμών**.</span><span class="sxs-lookup"><span data-stu-id="28065-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="28065-109">Στο μενού **SFTP**, επιλέξτε **Ρύθμιση**.</span><span class="sxs-lookup"><span data-stu-id="28065-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="28065-110">Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="28065-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="28065-111">Παρέχετε ένα **όνομα χρήστη**, έναν **κωδικό πρόσβασης** και ένα **όνομα κεντρικού υπολογιστή** για τον λογαριασμό SFTP.</span><span class="sxs-lookup"><span data-stu-id="28065-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="28065-112">Παράδειγμα: εάν ο ριζικός φάκελος του διακομιστή SFTP είναι /root/folder και θα θέλατε να γίνει εξαγωγή των δεδομένων στο /root/folder/ci_export_destination_folder, ο κεντρικός υπολογιστής θα πρέπει να είναι ftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="28065-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="28065-113">Επιλέξτε **Επαλήθευση** για να δοκιμάσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="28065-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="28065-114">Μετά την επιτυχή επαλήθευση, επιλέξτε εάν θέλετε να εξαγάγετε τα δεδομένα σας σε **συμπιεσμένο** ή **αποσυμπιεσμένο** αρχείο και επιλέξτε τον **οριοθέτη πεδίων** για τα αρχεία που έχουν εξαχθεί.</span><span class="sxs-lookup"><span data-stu-id="28065-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="28065-115">Επιλέξτε **Συμφωνώ** για να επιβεβαιώσετε το **Απόρρητο δεδομένων και συμμόρφωση**.</span><span class="sxs-lookup"><span data-stu-id="28065-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="28065-116">Επιλέξτε **Επόμενο** για να ξεκινήσετε τη ρύθμιση παραμέτρων της εξαγωγής.</span><span class="sxs-lookup"><span data-stu-id="28065-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="28065-117">Ρύθμιση παραμέτρων σύνδεσης</span><span class="sxs-lookup"><span data-stu-id="28065-117">Configure the connection</span></span>

1. <span data-ttu-id="28065-118">Επιλέξτε τα **χαρακτηριστικά πελάτη** που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="28065-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="28065-119">Μπορείτε να εξαγάγετε ένα ή περισσότερα χαρακτηριστικά.</span><span class="sxs-lookup"><span data-stu-id="28065-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="28065-120">Επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="28065-120">Select **Next**.</span></span>

1. <span data-ttu-id="28065-121">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="28065-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="28065-122">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="28065-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="28065-123">Εξαγωγή δεδομένων</span><span class="sxs-lookup"><span data-stu-id="28065-123">Export the data</span></span>

<span data-ttu-id="28065-124">Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="28065-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="28065-125">Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="28065-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="28065-126">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="28065-126">Data privacy and compliance</span></span>

<span data-ttu-id="28065-127">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα μέσω SFTP, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="28065-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="28065-128">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι ο προορισμός εξαγωγής πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="28065-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="28065-129">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="28065-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="28065-130">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="28065-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
