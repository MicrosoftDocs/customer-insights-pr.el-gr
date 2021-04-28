---
title: Εξαγωγή δεδομένων Customer Insights στο Facebook Ads Manager
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906810"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="fb897-103">Εξαγωγή λίστας τμημάτων στο Facebook Ads Manager (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="fb897-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="fb897-104">Εξαγάγετε τμήματα ενοποιημένων προφίλ πελατών στο Facebook Ads Manager για τη δημιουργία εκστρατειών στο Facebook και το Instagram.</span><span class="sxs-lookup"><span data-stu-id="fb897-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="fb897-105">Προϋποθέσεις για σύνδεση</span><span class="sxs-lookup"><span data-stu-id="fb897-105">Prerequisites for connection</span></span>

- <span data-ttu-id="fb897-106">Πρέπει να έχετε έναν [**Διαφημιστικό λογαριασμό Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) που περιλαμβάνει έναν [**Επιχειρηματικό λογαριασμό Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="fb897-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="fb897-107">Πρέπει να είστε διαχειριστής του [**Λογαριασμού Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="fb897-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fb897-108">Γνωστοί περιορισμοί</span><span class="sxs-lookup"><span data-stu-id="fb897-108">Known limitations</span></span>

- <span data-ttu-id="fb897-109">Έως και 10 εκατομμύρια προφίλ πελατών ανά εξαγωγή στο Ads Manager του Facebook.</span><span class="sxs-lookup"><span data-stu-id="fb897-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="fb897-110">Η εξαγωγή στο Ads Manager του Facebook περιορίζεται σε τμήματα.</span><span class="sxs-lookup"><span data-stu-id="fb897-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="fb897-111">Δημιουργήστε ή ενημερώστε προσαρμοσμένα κοινά μόνο στο Facebook του τύπου *λίστα πελατών*.</span><span class="sxs-lookup"><span data-stu-id="fb897-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="fb897-112">Η εξαγωγή τμημάτων με σύνολο 10 εκατομμυρίων προφίλ μπορεί να χρειαστεί έως και 90 λεπτά για να ολοκληρωθεί.</span><span class="sxs-lookup"><span data-stu-id="fb897-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="fb897-113">Ρύθμιση σύνδεσης στο Ads Manager του Facebook</span><span class="sxs-lookup"><span data-stu-id="fb897-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="fb897-114">Για να μπορούν οι χρήστες να δημιουργήσουν μια εξαγωγή, ο διαχειριστής πρέπει να ρυθμίσει τη σύνδεση στην υπηρεσία και να επιτρέψει στους συμβάλλοντες να χρησιμοποιήσουν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fb897-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="fb897-115">Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.</span><span class="sxs-lookup"><span data-stu-id="fb897-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fb897-116">Επιλέξτε **Προσθήκη σύνδεσης** κι επιλέξτε **Facebook Ads Manager** για να ρυθμίσετε τις παραμέτρους της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="fb897-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="fb897-117">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="fb897-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fb897-118">Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fb897-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fb897-119">Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="fb897-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fb897-120">Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fb897-120">Choose who can use this connection.</span></span> <span data-ttu-id="fb897-121">Εάν δεν κάνετε καμία ενέργεια, η προεπιλογή θα είναι οι **Διαχειριστές**.</span><span class="sxs-lookup"><span data-stu-id="fb897-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="fb897-122">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fb897-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fb897-123">Έλεγχος ταυτότητας με το Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="fb897-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="fb897-124">Επιλέξτε **Συνέχεια με το Facebook** για να συνδεθείτε στον λογαριασμό Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="fb897-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="fb897-125">Επιτρέψτε το δικαίωμα **ads_management** μετά τον έλεγχο ταυτότητας με το Facebook.</span><span class="sxs-lookup"><span data-stu-id="fb897-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="fb897-126">Επιλέξτε τον **Λογαριασμό Facebook Ads** με τον οποίο θέλετε να εργαστείτε.</span><span class="sxs-lookup"><span data-stu-id="fb897-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="fb897-127">Επιλέξτε ένα **Υπάρχον προσαρμοσμένο κοινό** από την αναπτυσσόμενη λίστα ή δημιουργήστε ένα **Νέο προσαρμοσμένο κοινό**.</span><span class="sxs-lookup"><span data-stu-id="fb897-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="fb897-128">Για περισσότερες πληροφορίες, ανατρέξτε στο άρθρο [**Ακροατήρια στο Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="fb897-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="fb897-129">Μπορείτε να δημιουργήσετε ή να ενημερώσετε προσαρμοσμένα κοινά μόνο στο Facebook του τύπου *λίστα πελατών* με αυτήν την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="fb897-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="fb897-130">Σε ορισμένες περιπτώσεις, στην αναπτυσσόμενη λίστα εμφανίζονται προσαρμοσμένα κοινά διαφορετικών τύπων.</span><span class="sxs-lookup"><span data-stu-id="fb897-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="fb897-131">Εάν επιλέξετε διαφορετικό τύπο από τη *λίστα πελατών*, η εξαγωγή θα αποτύχει.</span><span class="sxs-lookup"><span data-stu-id="fb897-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="fb897-132">Ελέγξτε την **Προστασία προσωπικών δεδομένων και τη συμμόρφωση** και επιλέξτε **Συμφωνώ**.</span><span class="sxs-lookup"><span data-stu-id="fb897-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="fb897-133">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="fb897-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fb897-134">Ρύθμιση παραμέτρων εξαγωγής</span><span class="sxs-lookup"><span data-stu-id="fb897-134">Configure an export</span></span>

<span data-ttu-id="fb897-135">Μπορείτε να ρυθμίσετε τις παραμέτρους αυτής της εξαγωγής, εάν έχετε πρόσβαση σε μια σύνδεση αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="fb897-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fb897-136">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δικαιώματα που απαιτούνται για τη ρύθμιση των παραμέτρων μιας εξαγωγής](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fb897-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fb897-137">Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.</span><span class="sxs-lookup"><span data-stu-id="fb897-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fb897-138">Για να δημιουργήσετε μια νέα εξαγωγή, επιλέξτε **Προσθήκη προορισμού**.</span><span class="sxs-lookup"><span data-stu-id="fb897-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="fb897-139">Στη **Σύνδεση για εξαγωγή** επιλέξτε μια σύνδεση από την ενότητα **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="fb897-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="fb897-140">Εάν δεν βλέπετε αυτό το όνομα ενότητας, δεν υπάρχουν διαθέσιμες συνδέσεις αυτού του τύπου.</span><span class="sxs-lookup"><span data-stu-id="fb897-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fb897-141">Στο **πεδίο επιλογής βασικού αναγνωριστικού**, επιλέξτε **Email**, **Όνομα και διεύθυνση** ή **Τηλέφωνο** για αποστολή στο Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="fb897-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="fb897-142">Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="fb897-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fb897-143">Αντιστοιχίστε τα αντίστοιχα χαρακτηριστικά από την οντότητα του ενοποιημένου πελάτη σας για το επιλεγμένο αναγνωριστικό κλειδιού.</span><span class="sxs-lookup"><span data-stu-id="fb897-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="fb897-144">[ΣΥΜΒΟΥΛΗ] Οι μεγαλύτερες πιθανότητες αντιστοίχισης προκύπτουν αν επιλέξετε το **Email** ως βασικό αναγνωριστικό.</span><span class="sxs-lookup"><span data-stu-id="fb897-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="fb897-145">Η προσθήκη επιπλέον αναγνωριστικών μπορεί να βελτιώσει την αντιστοίχιση.</span><span class="sxs-lookup"><span data-stu-id="fb897-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="fb897-146">Επιλέξτε **Προσθήκη χαρακτηριστικού** για να αντιστοιχίσετε περισσότερα χαρακτηριστικά για αποστολή στο Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="fb897-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="fb897-147">Χαρακτηριστικά από το Facebook Ads Manager αντιστοιχίζονται με τα ακόλουθα φιλικά προς τον χρήστη ονόματα: **FN** = **Όνομα**, **LN** = **Επώνυμο**, **FI** = **Πρώτο αρχικό**, **PHONE** = **Τηλέφωνο**, **GEN** = **Φύλο**, **DOB** = **Ημερομηνία γέννησης**, **ST** = **Πολιτεία**, **CT** = **Πόλη**, **ZIP** = **Ταχυδρομικός κώδικας**, **COUNTRY** = **Χώρα/περιοχή**</span><span class="sxs-lookup"><span data-stu-id="fb897-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="fb897-148">Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="fb897-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="fb897-149">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="fb897-149">Select **Save**.</span></span>

<span data-ttu-id="fb897-150">Η αποθήκευση μιας εξαγωγής δεν εκτελεί αμέσως την εξαγωγή.</span><span class="sxs-lookup"><span data-stu-id="fb897-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fb897-151">Η εξαγωγή εκτελείται με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fb897-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fb897-152">Μπορείτε επίσης να [εξαγάγετε δεδομένα κατ' απαίτηση](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fb897-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fb897-153">Απόρρητο δεδομένων και συμμόρφωση</span><span class="sxs-lookup"><span data-stu-id="fb897-153">Data privacy and compliance</span></span>

<span data-ttu-id="fb897-154">Όταν ενεργοποιείτε το Dynamics 365 Customer Insights για να μεταδίδετε δεδομένα στο Facebook Ads Manager, επιτρέπετε τη μεταφορά δεδομένων εκτός του ορίου συμμόρφωσης για το Dynamics 365 Customer Insights, συμπεριλαμβανομένων των δυνητικά ευαίσθητων δεδομένων, όπως τα προσωπικά δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="fb897-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fb897-155">Η Microsoft θα μεταβιβάσει τα εν λόγω δεδομένα με τη δική σας οδηγία, αλλά εσείς είστε υπεύθυνοι για να διασφαλίσετε ότι το Facebook πληροί τυχόν υποχρεώσεις προστασίας προσωπικών δεδομένων ή ασφάλειας που ενδεχομένως διαθέτετε.</span><span class="sxs-lookup"><span data-stu-id="fb897-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fb897-156">Για περισσότερες πληροφορίες, ανατρέξτε στη [Δήλωση προστασίας προσωπικών δεδομένων της Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fb897-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fb897-157">Ο διαχειριστής του Dynamics 365 Customer Insights μπορεί να καταργήσει αυτόν τον προορισμό εξαγωγής οποιαδήποτε στιγμή, για να διακόψετε τη χρήση αυτής της λειτουργίας.</span><span class="sxs-lookup"><span data-stu-id="fb897-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
