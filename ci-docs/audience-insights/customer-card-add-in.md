---
title: Εγκαταστήσετε και ρυθμίστε το Πρόσθετο κάρτας πελάτη
description: Εγκαταστήστε και ρυθμίστε τις παραμέτρους του πρόσθετου Κάρτας πελάτη για το Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268044"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="43e39-103">Πρόσθετο κάρτας πελάτη (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="43e39-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="43e39-104">Αποκτήστε μια προβολή 360 μοιρών των πελατών σας απευθείας στις εφαρμογές Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43e39-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="43e39-105">Προβάλετε τα δημογραφικά στοιχεία, τις πληροφορίες και τα χρονοδιαγράμματα δραστηριοτήτων με το πρόσθετο "κάρτα πελάτη".</span><span class="sxs-lookup"><span data-stu-id="43e39-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43e39-106">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="43e39-106">Prerequisites</span></span>

- <span data-ttu-id="43e39-107">Εφαρμογή Dynamics 365 (όπως το Κέντρο πωλήσεων ή το Κέντρο εξυπηρέτηση πελατών), η έκδοση 9.0 και η μεταγενέστερη έκδοση με ενεργοποιημένο το Ενοποιημένο περιβάλλον εργασίας.</span><span class="sxs-lookup"><span data-stu-id="43e39-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="43e39-108">Προφίλ πελατών [που έχουν ληφθεί από την εφαρμογή Dynamics 365 χρησιμοποιώντας το Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="43e39-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="43e39-109">Οι χρήστες του πρόσθετου «κάρτα πελάτη» θα πρέπει να [προστεθούν ως χρήστες](permissions.md) στις πληροφορίες κοινού.</span><span class="sxs-lookup"><span data-stu-id="43e39-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="43e39-110">[Ρυθμισμένες δυνατότητες αναζήτησης και φιλτραρίσματος](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="43e39-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="43e39-111">Στοιχείο ελέγχου δημογραφικών στοιχείων: Τα δημογραφικά πεδία (όπως η ηλικία ή το φύλο) είναι διαθέσιμα στο ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="43e39-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="43e39-112">Στοιχείο ελέγχου εμπλουτισμού: απαιτεί ενεργούς [εμπλουτισμούς](enrichment-hub.md) εφαρμοσμένους στα προφίλ πελατών.</span><span class="sxs-lookup"><span data-stu-id="43e39-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="43e39-113">Στοιχείο ελέγχου ευφυΐας: απαιτεί δεδομένα που έχουν δημιουργηθεί χρησιμοποιώντας την εκμάθηση μηχανής Azure ([Προγνωστικά](predictions.md) ή [προσαρμοσμένα μοντέλα](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="43e39-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="43e39-114">Στοιχείο ελέγχου μέτρησης: απαιτεί [ρυθμισμένα μέτρα](measures.md).</span><span class="sxs-lookup"><span data-stu-id="43e39-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="43e39-115">Στοιχείο ελέγχου λωρίδας χρόνου: απαιτεί [ρυθμισμένες δραστηριότητες](activities.md).</span><span class="sxs-lookup"><span data-stu-id="43e39-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="43e39-116">Εγκατάσταση του Πρόσθετου κάρτας πελάτη</span><span class="sxs-lookup"><span data-stu-id="43e39-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="43e39-117">Το πρόσθετο "Κάρτα πελάτη" είναι μια λύση για εφαρμογές δέσμευσης πελατών στο Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43e39-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="43e39-118">Για να εγκαταστήσετε τη λύση, μεταβείτε στην επιλογή AppSource και πραγματοποιήστε αναζήτηση για την **Κάρτα πελάτη Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="43e39-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="43e39-119">Επιλέξτε το [πρόσθετο κάρτας πελάτη στο AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) και επιλέξτε **Λήψη τώρα**.</span><span class="sxs-lookup"><span data-stu-id="43e39-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="43e39-120">Μπορεί να χρειαστεί να συνδεθείτε με τα διαπιστευτήρια διαχειριστή για να εγκαταστήσει η εφαρμογή Dynamics 365 τη λύση.</span><span class="sxs-lookup"><span data-stu-id="43e39-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="43e39-121">Μπορεί να χρειαστεί αρκετός χρόνος για την εγκατάσταση της λύσης στο περιβάλλον σας.</span><span class="sxs-lookup"><span data-stu-id="43e39-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="43e39-122">Ρύθμιση παραμέτρων του πρόσθετου κάρτας πελάτη</span><span class="sxs-lookup"><span data-stu-id="43e39-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="43e39-123">Ως διαχειριστής, μεταβείτε στην ενότητα **Ρυθμίσεις** στο Dynamics 365 και επιλέξτε **Λύσεις**.</span><span class="sxs-lookup"><span data-stu-id="43e39-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="43e39-124">Επιλέξτε τη σύνδεση **Εμφανιζόμενο όνομα** για τη λύση **Πρόσθετο κάρτας πελάτη Dynamics 365 Customer Insights (προεπισκόπηση)**.</span><span class="sxs-lookup"><span data-stu-id="43e39-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43e39-125">![Επιλέξτε εμφανιζόμενο όνομα](media/select-display-name.png "Επιλέξτε εμφανιζόμενο όνομα")</span><span class="sxs-lookup"><span data-stu-id="43e39-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="43e39-126">Επιλέξτε **Σύνδεση** και καταγράψτε τα διαπιστευτήρια για το λογαριασμό διαχειριστή που χρησιμοποιείτε για να ρυθμίσετε τις παραμέτρους του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43e39-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="43e39-127">Βεβαιωθείτε ότι ο αποκλεισμός αναδυόμενων παραθύρων του προγράμματος περιήγησης δεν αποκλείει το παράθυρο ελέγχου ταυτότητας όταν επιλέγετε το κουμπί **Σύνδεση**.</span><span class="sxs-lookup"><span data-stu-id="43e39-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="43e39-128">Επιλέξτε το περιβάλλον από το οποίο θέλετε να λάβετε δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="43e39-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="43e39-129">Καθορίστε ποια είναι η αντιστοίχιση πεδίων σε καρτέλες στην εφαρμογή Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43e39-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="43e39-130">Για να αντιστοιχίσετε μια επαφή, επιλέξτε το πεδίο στην οντότητα «Πελάτης» που ταιριάζει με το αναγνωριστικό της οντότητας «Επαφή».</span><span class="sxs-lookup"><span data-stu-id="43e39-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="43e39-131">Για να αντιστοιχίσετε με έναν λογαριασμό, επιλέξτε το πεδίο στην οντότητα «Πελάτης» που ταιριάζει με το αναγνωριστικό της οντότητας «Λογαριασμός».</span><span class="sxs-lookup"><span data-stu-id="43e39-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43e39-132">![Πεδίο αναγνωριστικού επαφής](media/contact-id-field.png "Πεδίο αναγνωριστικού επαφής")</span><span class="sxs-lookup"><span data-stu-id="43e39-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="43e39-133">Επιλέξτε **Αποθήκευση ρύθμισης παραμέτρων** για να αποθηκεύσετε τις ρυθμίσεις.</span><span class="sxs-lookup"><span data-stu-id="43e39-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="43e39-134">Στη συνέχεια, θα πρέπει να αναθέσετε ρόλους ασφαλείας στο Dynamics 365, ώστε οι χρήστες να μπορούν να προσαρμόσουν και να δουν την κάρτα του πελάτη.</span><span class="sxs-lookup"><span data-stu-id="43e39-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="43e39-135">Στο Dynamics 365, μεταβείτε στις **Ρυθμίσεις** > **Ασφάλεια** > **Χρήστες**.</span><span class="sxs-lookup"><span data-stu-id="43e39-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="43e39-136">Επιλέξτε τους χρήστες για επεξεργασία ρόλων χρήστη και επιλέξτε **Διαχείριση ρόλων**.</span><span class="sxs-lookup"><span data-stu-id="43e39-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="43e39-137">Αντιστοιχίστε τον ρόλο του **Υπεύθυνου προσαρμογής Customer Insights** σ ε χρήστες που θα προσαρμόσουν το περιεχόμενο που εμφανίζεται στην καρτέλα ολόκληρου του οργανισμού.</span><span class="sxs-lookup"><span data-stu-id="43e39-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="43e39-138">Προσθήκη στοιχείων ελέγχου «Κάρτα πελάτη» σε φόρμες</span><span class="sxs-lookup"><span data-stu-id="43e39-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="43e39-139">Για να προσθέσετε τα στοιχεία ελέγχου της κάρτας πελάτη στη φόρμα "επαφή", μεταβείτε στις **Ρυθμίσεις** > **Προσαρμογές** στο Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43e39-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="43e39-140">Επιλέξτε **Προσαρμογή του συστήματος**.</span><span class="sxs-lookup"><span data-stu-id="43e39-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="43e39-141">Μεταβείτε στην οντότητα **Επαφή**, αναπτύξτε το μενού της και στη συνέχεια, επιλέξτε **Φόρμες**.</span><span class="sxs-lookup"><span data-stu-id="43e39-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="43e39-142">Επιλέξτε τη φόρμα επαφής στην οποία θέλετε να προσθέσετε τα στοιχεία ελέγχου Κάρτας πελάτη.</span><span class="sxs-lookup"><span data-stu-id="43e39-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="43e39-143">![Επιλέξτε την φόρμα επαφής](media/contact-active-forms.png "Επιλέξτε την φόρμα επαφής")</span><span class="sxs-lookup"><span data-stu-id="43e39-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="43e39-144">Για να προσθέσετε το δημογραφικό στοιχείο ελέγχου, στο πρόγραμμα επεξεργασίας φορμών, σύρετε οποιοδήποτε πεδίο από την **Εξερεύνηση πεδίων** στο σημείο όπου θέλετε να εμφανιστεί το στοιχείο ελέγχου.</span><span class="sxs-lookup"><span data-stu-id="43e39-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="43e39-145">Επιλέξτε το πεδίο στη φόρμα που μόλις προσθέσατε και επιλέξτε **Αλλαγή ιδιοτήτων**.</span><span class="sxs-lookup"><span data-stu-id="43e39-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="43e39-146">Μεταβείτε στην καρτέλα **Στοιχεία ελέγχου** και επιλέξτε **Προσθήκη στοιχείου ελέγχου**.</span><span class="sxs-lookup"><span data-stu-id="43e39-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="43e39-147">Επιλέξτε ένα από τα διαθέσιμα προσαρμοσμένα στοιχεία ελέγχου και επιλέξτε **Προσθήκη**.</span><span class="sxs-lookup"><span data-stu-id="43e39-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="43e39-148">Στο παράθυρο διαλόγου **Ιδιότητες πεδίου**, αποεπιλέξτε το πλαίσιο ελέγχου **Εμφάνιση ετικέτας στη φόρμα**.</span><span class="sxs-lookup"><span data-stu-id="43e39-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="43e39-149">Επιλέξτε την επιλογή **Web** για το στοιχείο ελέγχου.</span><span class="sxs-lookup"><span data-stu-id="43e39-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="43e39-150">Για τον έλεγχο εμπλουτισμού, επιλέξτε τον τύπο εμπλουτισμού που θέλετε να εμφανίζεται ρυθμίζοντας τις παραμέτρους του πεδίου **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="43e39-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="43e39-151">Προσθέστε ένα ξεχωριστό χειριστήριο εμπλουτισμού για κάθε τύπο εμπλουτισμού.</span><span class="sxs-lookup"><span data-stu-id="43e39-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="43e39-152">Επιλέξτε **Αποθήκευση** και **Δημοσίευση** για να δημοσιεύσετε την ενημερωμένη φόρμα επαφής.</span><span class="sxs-lookup"><span data-stu-id="43e39-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="43e39-153">Μεταβείτε στη δημοσιευμένη φόρμα επαφής.</span><span class="sxs-lookup"><span data-stu-id="43e39-153">Go to the published contact form.</span></span> <span data-ttu-id="43e39-154">Θα δείτε το στοιχείο ελέγχου που μόλις προστέθηκε.</span><span class="sxs-lookup"><span data-stu-id="43e39-154">You'll see the newly added control.</span></span> <span data-ttu-id="43e39-155">Μπορεί να χρειαστεί να συνδεθείτε την πρώτη φορά που θα το χρησιμοποιήσετε.</span><span class="sxs-lookup"><span data-stu-id="43e39-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="43e39-156">Για να προσαρμόσετε αυτό που θέλετε να εμφανίζεται στο προσαρμοσμένο στοιχείο ελέγχου, επιλέξτε το κουμπί επεξεργασία στην επάνω δεξιά γωνία.</span><span class="sxs-lookup"><span data-stu-id="43e39-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="43e39-157">Πρόσθετο αναβάθμισης κάρτας πελάτη</span><span class="sxs-lookup"><span data-stu-id="43e39-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="43e39-158">Το Πρόσθετο κάρτας πελάτη δεν αναβαθμίζεται αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="43e39-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="43e39-159">Για να κάνετε αναβάθμιση στην πιο πρόσφατη έκδοση, ακολουθήστε αυτήν τη διαδικασία στην εφαρμογή Dynamics 365 στην οποία είναι εγκατεστημένο το πρόσθετο.</span><span class="sxs-lookup"><span data-stu-id="43e39-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="43e39-160">Στην εφαρμογή Dynamics 365, μεταβείτε στις **Ρυθμίσεις** > **Προσαρμογή** και επιλέξτε **Λύσεις**.</span><span class="sxs-lookup"><span data-stu-id="43e39-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="43e39-161">Στον πίνακα των προσθέτων αναζητήστε το **CustomerInsightsCustomerCard** και επιλέξτε τη γραμμή.</span><span class="sxs-lookup"><span data-stu-id="43e39-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="43e39-162">Επιλέξτε την **Αναβάθμιση λύσης εφαρμογής** στη γραμμή ενεργειών.</span><span class="sxs-lookup"><span data-stu-id="43e39-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Αναβάθμιση της λύσης στην περιοχή Προσαρμογής των εφαρμογών Dynamics 365":::

1. <span data-ttu-id="43e39-164">Μετά την έναρξη της διαδικασίας αναβάθμισης, θα δείτε μια ένδειξη φόρτωσης μέχρι να ολοκληρωθεί η αναβάθμιση.</span><span class="sxs-lookup"><span data-stu-id="43e39-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="43e39-165">Εάν δεν υπάρχει νεότερη έκδοση, η αναβάθμιση θα εμφανίσει ένα μήνυμα σφάλματος.</span><span class="sxs-lookup"><span data-stu-id="43e39-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]