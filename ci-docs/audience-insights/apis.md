---
title: Εργασία με API
description: Χρησιμοποιήστε API και κατανοήστε τους περιορισμούς.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267524"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="21d75-103">Εργασία με API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="21d75-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="21d75-104">Το Dynamics 365 Customer Insights παρέχει API για τη δημιουργία των δικών σας εφαρμογών με βάση τα δεδομένα σας στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21d75-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21d75-105">Οι λεπτομέρειες αυτών των API, περιλαμβάνονται στην [αναφορά API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="21d75-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="21d75-106">Περιλαμβάνουν πρόσθετες πληροφορίες σχετικά με τις λειτουργίες, τις παραμέτρους και τις αποκρίσεις.</span><span class="sxs-lookup"><span data-stu-id="21d75-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="21d75-107">Αυτό το άρθρο σάς καθοδηγεί για να αποκτήσετε πρόσβαση στα API Customer Insights, να δημιουργήσετε μια καταχώρηση εφαρμογής Azure και σας βοηθάει να ξεκινήσετε με τις διαθέσιμες βιβλιοθήκες προγραμμάτων-πελατών.</span><span class="sxs-lookup"><span data-stu-id="21d75-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="21d75-108">Έναρξη δοκιμής των API του Customer Insights</span><span class="sxs-lookup"><span data-stu-id="21d75-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="21d75-109">[Σύνδεση](https://home.ci.ai.dynamics.com) στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21d75-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="21d75-110">Εάν δεν έχετε ακόμα συνδρομή, [εγγραφείτε για μια δοκιμαστική έκδοση του Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="21d75-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="21d75-111">Για να ενεργοποιήσετε τα API στο περιβάλλον Customer Insights, μεταβείτε στην επιλογή **Διαχειριστής** > **Δικαιώματα**.</span><span class="sxs-lookup"><span data-stu-id="21d75-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="21d75-112">Για να το κάνετε αυτό, θα χρειαστείτε δικαιώματα διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="21d75-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="21d75-113">Μεταβείτε στην καρτέλα **API** και επιλέξτε το κουμπί **Ενεργοποίηση**.</span><span class="sxs-lookup"><span data-stu-id="21d75-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="21d75-114">Η ενεργοποίηση των API δημιουργεί ένα πρωτεύον και δευτερεύον κλειδί συνδρομής για την παρουσία σας που χρησιμοποιείται στις αιτήσεις API.</span><span class="sxs-lookup"><span data-stu-id="21d75-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="21d75-115">Μπορείτε να αναδημιουργήσετε τα κλειδιά επιλέγοντας την **Αναδημιουργία πρωτεύοντος** ή την **Αναδημιουργία δευτερευόντος** στα **Διαχειριστής** > **Δικαιώματα** > **API**.</span><span class="sxs-lookup"><span data-stu-id="21d75-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Ενεργοποίηση API Customer Insights":::

1. <span data-ttu-id="21d75-117">Επιλέξτε **Εξερεύνηση των API μας** για να δοκιμάσετε τα API.</span><span class="sxs-lookup"><span data-stu-id="21d75-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="21d75-118">Επιλέξτε μια λειτουργία API και επιλέξτε **Δοκιμή**.</span><span class="sxs-lookup"><span data-stu-id="21d75-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="21d75-119">Στο πλευρικό τμήμα παραθύρου, ορίστε την τιμή στο αναπτυσσόμενο μενού **Εξουσιοδότηση** σε **σιωπηρή**.</span><span class="sxs-lookup"><span data-stu-id="21d75-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="21d75-120">Η κεφαλίδα `Authorization` αποκτάται με ένα διακριτικό κομιστή που προστίθεται.</span><span class="sxs-lookup"><span data-stu-id="21d75-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="21d75-121">Το κλειδί της συνδρομής σας θα συμπληρωθεί αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="21d75-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="21d75-122">Προαιρετικά, προσθέστε όλες τις απαραίτητες παραμέτρους ερωτήματος.</span><span class="sxs-lookup"><span data-stu-id="21d75-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="21d75-123">Μεταβείτε στο κάτω μέρος του πλαϊνού τμήματος παραθύρου και επιλέξτε **Αποστολή**.</span><span class="sxs-lookup"><span data-stu-id="21d75-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="21d75-124">Η απόκριση HTTP θα εμφανιστεί σύντομα παρακάτω.</span><span class="sxs-lookup"><span data-stu-id="21d75-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="21d75-125">Δημιουργήστε μια νέα καταχώρησης εφαρμογής στην πύλη Azure</span><span class="sxs-lookup"><span data-stu-id="21d75-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="21d75-126">Αυτά τα βήματα σάς βοηθούν να ξεκινήσετε τη χρήση των API Customer Insights σε μια εφαρμογή Azure χρησιμοποιώντας εξουσιοδοτημένα δικαιώματα.</span><span class="sxs-lookup"><span data-stu-id="21d75-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="21d75-127">Βεβαιωθείτε ότι έχετε ολοκληρώσει την [ενότητα Έναρξη](#get-started-trying-the-customer-insights-apis) πρώτα.</span><span class="sxs-lookup"><span data-stu-id="21d75-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="21d75-128">Συνδεθείτε στην [Πύλη Azure](https://portal.azure.com) με τον λογαριασμό που μπορεί να έχει πρόσβαση στα δεδομένα του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21d75-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="21d75-129">Στα αριστερά, επιλέξτε **Εγγραφές εφαρμογών**.</span><span class="sxs-lookup"><span data-stu-id="21d75-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="21d75-130">Επιλέξτε **Νέα καταχώρηση** δώστε ένα όνομα εφαρμογής και επιλέξτε τον τύπο λογαριασμού.</span><span class="sxs-lookup"><span data-stu-id="21d75-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="21d75-131">Προαιρετικά, προσθέστε μια διεύθυνση URL ανακατεύθυνσης.</span><span class="sxs-lookup"><span data-stu-id="21d75-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="21d75-132">Το http://localhost αρκεί για την ανάπτυξη μιας εφαρμογής στον τοπικό υπολογιστή σας.</span><span class="sxs-lookup"><span data-stu-id="21d75-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="21d75-133">Στη νέα καταχώρηση εφαρμογής, μεταβείτε στη διεύθυνση **Άδειες API**.</span><span class="sxs-lookup"><span data-stu-id="21d75-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="21d75-134">Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Customer Insights** στο πλευρικό τμήμα παραθύρου.</span><span class="sxs-lookup"><span data-stu-id="21d75-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="21d75-135">Για τον **Τύπο δικαιωμάτων**, επιλέξτε **Εκχωρημένα δικαιώματα** και επιλέξτε το δικαίωμα **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="21d75-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="21d75-136">Επιλέξτε **Προσθήκη δικαιωμάτων**.</span><span class="sxs-lookup"><span data-stu-id="21d75-136">Select **Add permissions**.</span></span> <span data-ttu-id="21d75-137">Εάν πρέπει να αποκτήσετε πρόσβαση στο API χωρίς να συνδεθεί ένας χρήστης, ανατρέξτε στην ενότητα [Δικαιώματα εφαρμογής διακομιστή σε διακομιστή](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="21d75-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="21d75-138">Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="21d75-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="21d75-139">Μπορείτε να χρησιμοποιήσετε το Αναγνωριστικό εφαρμογής/πελάτη για αυτήν την καταχώρηση εφαρμογής στη Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL) για να αποκτήσετε ένα διακριτικό φορέα για αποστολή με το αίτημά σας στο API.</span><span class="sxs-lookup"><span data-stu-id="21d75-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="21d75-140">Για περισσότερες πληροφορίες σχετικά με το MSAL, δείτε [Επισκόπηση της Βιβλιοθήκης ελέγχου ταυτότητας της Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="21d75-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="21d75-141">Για περισσότερες πληροφορίες σχετικά με την καταχώρηση εφαρμογών στο Azure, δείτε [Η νέα εμπειρία καταχώρησης εφαρμογών της πύλης Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="21d75-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="21d75-142">Για πληροφορίες σχετικά με τη χρήση των API των βιβλιοθηκών πελατών μας, δείτε [Βιβλιοθήκες πελατών Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="21d75-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="21d75-143">Δικαιώματα εφαρμογής διακομιστή σε διακομιστή</span><span class="sxs-lookup"><span data-stu-id="21d75-143">Server-to-server application permissions</span></span>

<span data-ttu-id="21d75-144">Η [ενότητα καταχώρησης εφαρμογής](#create-a-new-app-registration-in-the-azure-portal) περιγράφει τον τρόπο καταχώρησης μιας εφαρμογής που απαιτεί από έναν χρήστη να συνδεθεί για έλεγχο ταυτότητας.</span><span class="sxs-lookup"><span data-stu-id="21d75-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="21d75-145">Μάθετε πώς να δημιουργήσετε μια καταχώρηση εφαρμογής που δεν χρειάζεται αλληλεπίδραση χρήστη και να εκτελεστεί σε διακομιστή.</span><span class="sxs-lookup"><span data-stu-id="21d75-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="21d75-146">Στην καταχώρηση εφαρμογής στην πύλη Azure, μεταβείτε στο **Δικαιώματα API**.</span><span class="sxs-lookup"><span data-stu-id="21d75-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="21d75-147">Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Customer Insights** στο πλευρικό τμήμα παραθύρου.</span><span class="sxs-lookup"><span data-stu-id="21d75-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="21d75-148">Για τον **Τύπο δικαιωμάτων**, επιλέξτε **Δικαιώματα εφαρμογής** και επιλέξτε το δικαίωμα **CustomerInsights.Api.All** .</span><span class="sxs-lookup"><span data-stu-id="21d75-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="21d75-149">Επιλέξτε **Προσθήκη δικαιωμάτων**.</span><span class="sxs-lookup"><span data-stu-id="21d75-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="21d75-150">Για να δώσετε τη συγκατάθεση του διαχειριστή σε αυτό το δικαίωμα εφαρμογής, πρέπει να προσθέσετε έναν Διευθυντή εξυπηρέτησης.</span><span class="sxs-lookup"><span data-stu-id="21d75-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="21d75-151">Εγκαταστήστε τη μονάδα Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="21d75-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="21d75-152">Συνδεθείτε στον λογαριασμό AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="21d75-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="21d75-153">Μπορείτε να βρείτε το αναγνωριστικό μισθωτή σας στην **Επισκόπηση** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="21d75-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="21d75-154">Εκτελέστε την ακόλουθη εντολή για να προσθέσετε έναν Διευθυντής εξυπηρέτησης Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Η παράμετρος AppId σχετίζεται με την εφαρμογή Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="21d75-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Δείγμα διευθυντή εξυπηρέτησης":::

1. <span data-ttu-id="21d75-156">Επιστρέψτε στα **Δικαιώματα API** για την καταχώρηση της εφαρμογής σας.</span><span class="sxs-lookup"><span data-stu-id="21d75-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="21d75-157">Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="21d75-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="21d75-158">Συμπερασματικά, πρέπει να προσθέσουμε το όνομα της καταχώρησης εφαρμογής ως χρήστης στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21d75-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="21d75-159">Ανοίξτε το Customer Insights, μεταβείτε στο **Διαχειριστής** > **Δικαιώματα** και επιλέξτε **Προσθήκη χρήστη**.</span><span class="sxs-lookup"><span data-stu-id="21d75-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="21d75-160">Αναζητήστε το όνομα της καταχώρησης εφαρμογής, επιλέξτε την από τα αποτελέσματα αναζήτησης και επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="21d75-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="21d75-161">Βιβλιοθήκες πελατών Customer Insights</span><span class="sxs-lookup"><span data-stu-id="21d75-161">Customer Insights client libraries</span></span>

<span data-ttu-id="21d75-162">Αυτή η ενότητα σάς βοηθά να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών που είναι διαθέσιμες για τα API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21d75-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="21d75-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="21d75-163">C# NuGet</span></span>

<span data-ttu-id="21d75-164">Μάθετε πώς να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών C# από το NuGet.org. Για περισσότερες πληροφορίες σχετικά με το πακέτο NuGet, δείτε [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="21d75-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="21d75-165">Προς το παρόν, αυτό το πακέτο στοχεύει στα πλαίσια netstandard2.0 και netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="21d75-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="21d75-166">Προσθέστε τη βιβλιοθήκη πελάτη C# σε ένα έργο C#</span><span class="sxs-lookup"><span data-stu-id="21d75-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="21d75-167">Στο Visual Studio, άνοιξε το **Διαχειριστής πακέτων NuGet** για το έργο σας.</span><span class="sxs-lookup"><span data-stu-id="21d75-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="21d75-168">Αναζητήστε **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="21d75-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="21d75-169">Επιλέξτε **Εγκατάσταση** για να προσθέσετε το πακέτο στο έργο.</span><span class="sxs-lookup"><span data-stu-id="21d75-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="21d75-170">Εναλλακτικά, εκτελέστε αυτήν την εντολή στην **Κονσόλα διαχειριστή πακέτων NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="21d75-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Προσθήκ πακέτου NuGet σε έργο Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="21d75-172">Χρησιμοποιήστε τη βιβλιοθήκη πελάτη C#</span><span class="sxs-lookup"><span data-stu-id="21d75-172">Use the C# client library</span></span>

1. <span data-ttu-id="21d75-173">Χρησιμοποιήστε τη [Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) για να λάβετε ένα `AccessToken` χρησιμοποιώντας την υπάροχυσα [Καταχώρηση εφαρμογής Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="21d75-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="21d75-174">Αφού ελέγξετε με επιτυχία την ταυτότητα και αποκτήσετε ένα διακριτικό, δημιουργήστε ένα νέο ή χρησιμοποιήστε ένα υπάρχον `HttpClient` με τον πρόσθετο **Έλεγχο ταυτότητας DefaultRequestHeaders** ορισμένο σε **Φορέας <access token>** και το **Ocp-Apim-Subscription-Key** ορισμένο σε [**κλειδί συνδρομής** από το περιβάλλον του Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="21d75-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="21d75-175">Επαναφέρετε την κεφαλίδα **Έλεγχος ταυτότητας** όταν χρειάζεται.</span><span class="sxs-lookup"><span data-stu-id="21d75-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="21d75-176">Για παράδειγμα, όταν έληξε το διακριτικό.</span><span class="sxs-lookup"><span data-stu-id="21d75-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="21d75-177">Περάστε αυτό το `HttpClient` στην κατασκευή του πελάτη `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="21d75-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Δείγμα httpclient":::

1. <span data-ttu-id="21d75-179">Πραγματοποιήστε κλήσεις με το πρόγραμμα-πελάτη στις «μεθόδους επέκτασης», για παράδειγμα, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="21d75-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="21d75-180">Εάν προτιμάτε την πρόσβαση στο υποκείμενο `Microsoft.Rest.HttpOperationResponse`, χρησιμοποιήστε τις «μεθόδους μηνυμάτων http», για παράδειγμα `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="21d75-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="21d75-181">Η απάντηση πιθανότατα θα είναι του τύπου `object` επειδή η μέθοδος μπορεί να επιστρέψει πολλούς τύπους (για παράδειγμα, `IList<InstanceInfo>` και `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="21d75-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="21d75-182">Για να ελέγξετε τον τύπο επιστροφής, μπορείτε να ρίξετε με ασφάλεια τα αντικείμενα στους τύπους απόκρισης που καθορίζονται στη [σελίδα λεπτομερειών API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) για αυτή τη λειτουργία.</span><span class="sxs-lookup"><span data-stu-id="21d75-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="21d75-183">Εάν χρειάζονται περισσότερες πληροφορίες σχετικά με την αίτηση, χρησιμοποιήστε τις **μεθόδους μηνυμάτων http** για πρόσβαση στο αντικείμενο ακατέργαστης απόκρισης.</span><span class="sxs-lookup"><span data-stu-id="21d75-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]