---
title: Πρόσθετο κάρτας πελάτη για εφαρμογές Dynamics 365
description: Εμφάνιση δεδομένων από πληροφορίες κοινού στις εφαρμογές Dynamics 365 με αυτό το πρόσθετο.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059588"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="38463-103">Πρόσθετο κάρτας πελάτη (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="38463-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="38463-104">Αποκτήστε μια προβολή 360 μοιρών των πελατών σας απευθείας στις εφαρμογές Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38463-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="38463-105">Με το πρόσθετο Customer Card εγκατεστημένο σε μια υποστηριζόμενη εφαρμογή Dynamics 365, μπορείτε να επιλέξετε να εμφανίζονται δημογραφικά στοιχεία, πληροφορίες και χρονοδιαγράμματα δραστηριοτήτων.</span><span class="sxs-lookup"><span data-stu-id="38463-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="38463-106">Το πρόσθετο θα ανακτήσει δεδομένα από το Customer Insights χωρίς να επηρεάζονται τα δεδομένα στην συνδεδεμένη εφαρμογή Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38463-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="38463-107">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="38463-107">Prerequisites</span></span>

- <span data-ttu-id="38463-108">Το πρόσθετο λειτουργεί μόνο με εφαρμογές που καθορίζονται από μοντέλα του Dynamics 365, όπως οι εφαρμογές Sales ή Customer Service, έκδοση 9.0 και μεταγενέστερες.</span><span class="sxs-lookup"><span data-stu-id="38463-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="38463-109">Προκειμένου τα δεδομένα του Dynamics 365 να αντιστοιχιστούν στα προφίλ πελατών γνώσεων κοινού που πρέπει να [χρησιμοποιηθούν από την εφαρμογή Dynamics 365 χρησιμοποιώντας τον σύνδεσμο Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="38463-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="38463-110">Όλοι οι χρήστες του Dynamics 365 του Πρόσθετου Customer Card πρέπει να [προστεθούν ως χρήστες](permissions.md) στις πληροφορίες κοινού για να δουν τα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="38463-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="38463-111">Απαιτούνται οι [Ρυθμισμένες δυνατότητες αναζήτησης και φίλτρου](search-filter-index.md) στις πληροφορίες κοινού προκειμένου να λειτουργήσει η αναζήτηση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="38463-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="38463-112">Κάθε στοιχείο ελέγχου προσθέτου μπορεί να βασίζεται σε συγκεκριμένα δεδομένα στις πληροφορίες κοινού:</span><span class="sxs-lookup"><span data-stu-id="38463-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="38463-113">Στοιχείο ελέγχου μέτρησης: απαιτεί [ρυθμισμένα μέτρα](measures.md).</span><span class="sxs-lookup"><span data-stu-id="38463-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="38463-114">Στοιχείο ελέγχου ευφυΐας: Απαιτεί δεδομένα που δημιουργούνται χρησιμοποιώντας [προβλέψεις](predictions.md) ή [προσαρμοσμένα μοντέλα](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="38463-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="38463-115">Στοιχείο ελέγχου δημογραφικών στοιχείων: Τα δημογραφικά πεδία (όπως η ηλικία ή το φύλο) είναι διαθέσιμα στο ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="38463-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="38463-116">Στοιχείο ελέγχου εμπλουτισμού: απαιτεί ενεργούς [εμπλουτισμούς](enrichment-hub.md) εφαρμοσμένους στα προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="38463-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="38463-117">Στοιχείο ελέγχου λωρίδας χρόνου: απαιτεί [ρυθμισμένες δραστηριότητες](activities.md).</span><span class="sxs-lookup"><span data-stu-id="38463-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="38463-118">Εγκατάσταση του Πρόσθετου κάρτας πελάτη</span><span class="sxs-lookup"><span data-stu-id="38463-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="38463-119">Το πρόσθετο "Κάρτα πελάτη" είναι μια λύση για εφαρμογές δέσμευσης πελατών στο Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38463-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="38463-120">Για να εγκαταστήσετε τη λύση, μεταβείτε στην επιλογή AppSource και πραγματοποιήστε αναζήτηση για την **Κάρτα πελάτη Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="38463-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="38463-121">Επιλέξτε το [πρόσθετο κάρτας πελάτη στο AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) και επιλέξτε **Λήψη τώρα**.</span><span class="sxs-lookup"><span data-stu-id="38463-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="38463-122">Μπορεί να χρειαστεί να συνδεθείτε με τα διαπιστευτήρια διαχειριστή για να εγκαταστήσει η εφαρμογή Dynamics 365 τη λύση.</span><span class="sxs-lookup"><span data-stu-id="38463-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="38463-123">Μπορεί να χρειαστεί αρκετός χρόνος για την εγκατάσταση της λύσης στο περιβάλλον σας.</span><span class="sxs-lookup"><span data-stu-id="38463-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="38463-124">Ρύθμιση παραμέτρων του πρόσθετου κάρτας πελάτη</span><span class="sxs-lookup"><span data-stu-id="38463-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="38463-125">Ως διαχειριστής, μεταβείτε στην ενότητα **Ρυθμίσεις** στο Dynamics 365 και επιλέξτε **Λύσεις**.</span><span class="sxs-lookup"><span data-stu-id="38463-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="38463-126">Επιλέξτε τη σύνδεση **Εμφανιζόμενο όνομα** για τη λύση **Πρόσθετο κάρτας πελάτη Dynamics 365 Customer Insights (προεπισκόπηση)**.</span><span class="sxs-lookup"><span data-stu-id="38463-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38463-127">![Επιλέξτε εμφανιζόμενο όνομα](media/select-display-name.png "Επιλέξτε εμφανιζόμενο όνομα")</span><span class="sxs-lookup"><span data-stu-id="38463-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="38463-128">Επιλέξτε **Σύνδεση** και καταγράψτε τα διαπιστευτήρια για το λογαριασμό διαχειριστή που χρησιμοποιείτε για να ρυθμίσετε τις παραμέτρους του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38463-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38463-129">Βεβαιωθείτε ότι ο αποκλεισμός αναδυόμενων παραθύρων του προγράμματος περιήγησης δεν αποκλείει το παράθυρο ελέγχου ταυτότητας όταν επιλέγετε το κουμπί **Σύνδεση**.</span><span class="sxs-lookup"><span data-stu-id="38463-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="38463-130">Επιλέξτε το περιβάλλον του Customer Insights από την οποία θέλετε να λάβετε δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="38463-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="38463-131">Ορίστε την αντιστοίχιση πεδίου σε καρτέλες στην εφαρμογή Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38463-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="38463-132">Ανάλογα με τα δεδομένα σας στο Customer Insights, μπορείτε να επιλέξετε να αντιστοιχίσετε τις ακόλουθες επιλογές:</span><span class="sxs-lookup"><span data-stu-id="38463-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="38463-133">Για να αντιστοιχίσετε μια επαφή, επιλέξτε το πεδίο στην οντότητα «Πελάτης» που ταιριάζει με το αναγνωριστικό της οντότητας «Επαφή».</span><span class="sxs-lookup"><span data-stu-id="38463-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="38463-134">Για να αντιστοιχίσετε με έναν λογαριασμό, επιλέξτε το πεδίο στην οντότητα «Πελάτης» που ταιριάζει με το αναγνωριστικό της οντότητας «Λογαριασμός».</span><span class="sxs-lookup"><span data-stu-id="38463-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38463-135">![Πεδίο αναγνωριστικού επαφής](media/contact-id-field.png "Πεδίο αναγνωριστικού επαφής")</span><span class="sxs-lookup"><span data-stu-id="38463-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="38463-136">Επιλέξτε **Αποθήκευση ρύθμισης παραμέτρων** για να αποθηκεύσετε τις ρυθμίσεις.</span><span class="sxs-lookup"><span data-stu-id="38463-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="38463-137">Στη συνέχεια, θα πρέπει να αναθέσετε ρόλους ασφαλείας στο Dynamics 365, ώστε οι χρήστες να μπορούν να προσαρμόσουν και να δουν την κάρτα του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="38463-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="38463-138">Στο Dynamics 365, μεταβείτε στις **Ρυθμίσεις** > **Ασφάλεια** > **Χρήστες**.</span><span class="sxs-lookup"><span data-stu-id="38463-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="38463-139">Επιλέξτε τους χρήστες για επεξεργασία ρόλων χρήστη και επιλέξτε **Διαχείριση ρόλων**.</span><span class="sxs-lookup"><span data-stu-id="38463-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="38463-140">Αντιστοιχίστε τον ρόλο του **Υπεύθυνου προσαρμογής Customer Insights** σ ε χρήστες που θα προσαρμόσουν το περιεχόμενο που εμφανίζεται στην καρτέλα ολόκληρου του οργανισμού.</span><span class="sxs-lookup"><span data-stu-id="38463-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="38463-141">Προσθήκη στοιχείων ελέγχου «Κάρτα πελάτη» σε φόρμες</span><span class="sxs-lookup"><span data-stu-id="38463-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="38463-142">Για να προσθέσετε τα στοιχεία ελέγχου της κάρτας πελάτη στη φόρμα "επαφή", μεταβείτε στις **Ρυθμίσεις** > **Προσαρμογές** στο Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38463-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="38463-143">Επιλέξτε **Προσαρμογή του συστήματος**.</span><span class="sxs-lookup"><span data-stu-id="38463-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="38463-144">Μεταβείτε στην οντότητα **Επαφή**, αναπτύξτε το μενού της και στη συνέχεια, επιλέξτε **Φόρμες**.</span><span class="sxs-lookup"><span data-stu-id="38463-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="38463-145">Επιλέξτε τη φόρμα επαφής στην οποία θέλετε να προσθέσετε τα στοιχεία ελέγχου Κάρτας πελάτη.</span><span class="sxs-lookup"><span data-stu-id="38463-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38463-146">![Επιλέξτε την φόρμα επαφής](media/contact-active-forms.png "Επιλέξτε την φόρμα επαφής")</span><span class="sxs-lookup"><span data-stu-id="38463-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="38463-147">Για να προσθέσετε το δημογραφικό στοιχείο ελέγχου, στο πρόγραμμα επεξεργασίας φορμών, σύρετε οποιοδήποτε πεδίο από την **Εξερεύνηση πεδίων** στο σημείο όπου θέλετε να εμφανιστεί το στοιχείο ελέγχου.</span><span class="sxs-lookup"><span data-stu-id="38463-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="38463-148">Επιλέξτε το πεδίο στη φόρμα που μόλις προσθέσατε και επιλέξτε **Αλλαγή ιδιοτήτων**.</span><span class="sxs-lookup"><span data-stu-id="38463-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="38463-149">Μεταβείτε στην καρτέλα **Στοιχεία ελέγχου** και επιλέξτε **Προσθήκη στοιχείου ελέγχου**.</span><span class="sxs-lookup"><span data-stu-id="38463-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="38463-150">Επιλέξτε ένα από τα διαθέσιμα προσαρμοσμένα στοιχεία ελέγχου και επιλέξτε **Προσθήκη**.</span><span class="sxs-lookup"><span data-stu-id="38463-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="38463-151">Στο παράθυρο διαλόγου **Ιδιότητες πεδίου**, αποεπιλέξτε το πλαίσιο ελέγχου **Εμφάνιση ετικέτας στη φόρμα**.</span><span class="sxs-lookup"><span data-stu-id="38463-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="38463-152">Επιλέξτε την επιλογή **Web** για το στοιχείο ελέγχου.</span><span class="sxs-lookup"><span data-stu-id="38463-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="38463-153">Για τον έλεγχο εμπλουτισμού, επιλέξτε τον τύπο εμπλουτισμού που θέλετε να εμφανίζεται ρυθμίζοντας τις παραμέτρους του πεδίου **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="38463-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="38463-154">Προσθέστε ένα ξεχωριστό χειριστήριο εμπλουτισμού για κάθε τύπο εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="38463-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="38463-155">Επιλέξτε **Αποθήκευση** και **Δημοσίευση** για να δημοσιεύσετε την ενημερωμένη φόρμα επαφής.</span><span class="sxs-lookup"><span data-stu-id="38463-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="38463-156">Μεταβείτε στη δημοσιευμένη φόρμα επαφής.</span><span class="sxs-lookup"><span data-stu-id="38463-156">Go to the published contact form.</span></span> <span data-ttu-id="38463-157">Θα δείτε το στοιχείο ελέγχου που μόλις προστέθηκε.</span><span class="sxs-lookup"><span data-stu-id="38463-157">You'll see the newly added control.</span></span> <span data-ttu-id="38463-158">Μπορεί να χρειαστεί να συνδεθείτε την πρώτη φορά που θα το χρησιμοποιήσετε.</span><span class="sxs-lookup"><span data-stu-id="38463-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="38463-159">Για να προσαρμόσετε αυτό που θέλετε να εμφανίζεται στο προσαρμοσμένο στοιχείο ελέγχου, επιλέξτε το κουμπί επεξεργασία στην επάνω δεξιά γωνία.</span><span class="sxs-lookup"><span data-stu-id="38463-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="38463-160">Πρόσθετο αναβάθμισης κάρτας πελάτη</span><span class="sxs-lookup"><span data-stu-id="38463-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="38463-161">Το Πρόσθετο κάρτας πελάτη δεν αναβαθμίζεται αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="38463-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="38463-162">Για να κάνετε αναβάθμιση στην πιο πρόσφατη έκδοση, ακολουθήστε αυτήν τη διαδικασία στην εφαρμογή Dynamics 365 στην οποία είναι εγκατεστημένο το πρόσθετο.</span><span class="sxs-lookup"><span data-stu-id="38463-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="38463-163">Στην εφαρμογή Dynamics 365, μεταβείτε στις **Ρυθμίσεις** > **Προσαρμογή** και επιλέξτε **Λύσεις**.</span><span class="sxs-lookup"><span data-stu-id="38463-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="38463-164">Στον πίνακα των προσθέτων αναζητήστε το **CustomerInsightsCustomerCard** και επιλέξτε τη γραμμή.</span><span class="sxs-lookup"><span data-stu-id="38463-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="38463-165">Επιλέξτε την **Αναβάθμιση λύσης εφαρμογής** στη γραμμή ενεργειών.</span><span class="sxs-lookup"><span data-stu-id="38463-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Αναβάθμιση της λύσης στην περιοχή Προσαρμογής των εφαρμογών Dynamics 365":::

1. <span data-ttu-id="38463-167">Μετά την έναρξη της διαδικασίας αναβάθμισης, θα δείτε μια ένδειξη φόρτωσης μέχρι να ολοκληρωθεί η αναβάθμιση.</span><span class="sxs-lookup"><span data-stu-id="38463-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="38463-168">Εάν δεν υπάρχει νεότερη έκδοση, η αναβάθμιση θα εμφανίσει ένα μήνυμα σφάλματος.</span><span class="sxs-lookup"><span data-stu-id="38463-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
