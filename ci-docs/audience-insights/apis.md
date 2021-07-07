---
title: Εργασία με API
description: Χρησιμοποιήστε API και κατανοήστε τους περιορισμούς.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304742"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="2539a-103">Εργασία με API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2539a-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="2539a-104">Το Dynamics 365 Customer Insights παρέχει API για τη δημιουργία των δικών σας εφαρμογών με βάση τα δεδομένα σας στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2539a-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2539a-105">Οι λεπτομέρειες αυτών των API παρατίθενται στην [αναφορά Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="2539a-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="2539a-106">Περιλαμβάνουν πρόσθετες πληροφορίες σχετικά με τις λειτουργίες, τις παραμέτρους και τις αποκρίσεις.</span><span class="sxs-lookup"><span data-stu-id="2539a-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="2539a-107">Σε αυτό το άρθρο περιγράφεται ο τρόπος με τον οποίο μπορείτε να αποκτήσετε πρόσβαση στα Customer Insights API, να δημιουργήσετε μια καταχώρηση εφαρμογής Azure και να ξεκινήσετε με τις διαθέσιμες βιβλιοθήκες προγραμμάτων-πελατών.</span><span class="sxs-lookup"><span data-stu-id="2539a-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="2539a-108">Έναρξη δοκιμής των API του Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2539a-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="2539a-109">[Σύνδεση](https://home.ci.ai.dynamics.com) στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2539a-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="2539a-110">Εάν δεν έχετε ακόμα συνδρομή, [εγγραφείτε για μια δοκιμαστική έκδοση του Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="2539a-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="2539a-111">Για να ενεργοποιήσετε τα API στο περιβάλλον Customer Insights, μεταβείτε στην επιλογή **Διαχειριστής** > **Δικαιώματα**.</span><span class="sxs-lookup"><span data-stu-id="2539a-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="2539a-112">Για να το κάνετε αυτό, θα χρειαστείτε δικαιώματα διαχειριστή.</span><span class="sxs-lookup"><span data-stu-id="2539a-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="2539a-113">Μεταβείτε στην καρτέλα **API** και επιλέξτε το κουμπί **Ενεργοποίηση**.</span><span class="sxs-lookup"><span data-stu-id="2539a-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="2539a-114">Η ενεργοποίηση των API δημιουργεί ένα πρωτεύον και δευτερεύον κλειδί συνδρομής για την παρουσία σας που χρησιμοποιείται στις αιτήσεις API.</span><span class="sxs-lookup"><span data-stu-id="2539a-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="2539a-115">Μπορείτε να αναδημιουργήσετε τα κλειδιά επιλέγοντας την **Αναδημιουργία πρωτεύοντος** ή την **Αναδημιουργία δευτερευόντος** στα **Διαχειριστής** > **Δικαιώματα** > **API**.</span><span class="sxs-lookup"><span data-stu-id="2539a-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Ενεργοποίηση API Customer Insights":::

1. <span data-ttu-id="2539a-117">Επιλέξτε **Εξερεύνηση των API μας** για να [δοκιμάσετε τα API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="2539a-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="2539a-118">Επιλέξτε μια λειτουργία API και επιλέξτε **Δοκιμή**.</span><span class="sxs-lookup"><span data-stu-id="2539a-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="2539a-119">Στο πλαϊνό τμήμα παραθύρου, ορίστε την τιμή στο αναπτυσσόμενο μενού **Εξουσιοδότηση** σε **έμμεση**.</span><span class="sxs-lookup"><span data-stu-id="2539a-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="2539a-120">Η κεφαλίδα `Authorization` προστίθεται με διακριτικό φορέα.</span><span class="sxs-lookup"><span data-stu-id="2539a-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="2539a-121">Το κλειδί της συνδρομής σας θα συμπληρωθεί αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="2539a-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="2539a-122">Προαιρετικά, προσθέστε όλες τις απαραίτητες παραμέτρους ερωτήματος.</span><span class="sxs-lookup"><span data-stu-id="2539a-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="2539a-123">Μεταβείτε στο κάτω μέρος του πλαϊνού τμήματος παραθύρου και επιλέξτε **Αποστολή**.</span><span class="sxs-lookup"><span data-stu-id="2539a-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="2539a-124">Η απόκριση HTTP θα εμφανιστεί σύντομα παρακάτω.</span><span class="sxs-lookup"><span data-stu-id="2539a-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Πώς να δοκιμάσετε τα API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="2539a-126">Δημιουργήστε μια νέα καταχώρησης εφαρμογής στην πύλη Azure</span><span class="sxs-lookup"><span data-stu-id="2539a-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="2539a-127">Αυτά τα βήματα σας βοηθούν να ξεκίνησετε με τη χρήση των Customer Insights API σε μια εφαρμογή Azure, χρησιμοποιώντας δικαιώματα με ανάθεση.</span><span class="sxs-lookup"><span data-stu-id="2539a-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="2539a-128">Βεβαιωθείτε ότι ολοκληρώνετε πρώτα την [ενότητα Έναρξη](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="2539a-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="2539a-129">Συνδεθείτε στην [Πύλη Azure](https://portal.azure.com) με τον λογαριασμό που μπορεί να έχει πρόσβαση στα δεδομένα του Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2539a-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="2539a-130">Στα αριστερά, επιλέξτε **Εγγραφές εφαρμογών**.</span><span class="sxs-lookup"><span data-stu-id="2539a-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="2539a-131">Επιλέξτε **Νέα καταχώρηση**, δώστε ένα όνομα εφαρμογής και επιλέξτε τον τύπο λογαριασμού.</span><span class="sxs-lookup"><span data-stu-id="2539a-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="2539a-132">Προαιρετικά, προσθέστε μια διεύθυνση URL ανακατεύθυνσης.</span><span class="sxs-lookup"><span data-stu-id="2539a-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="2539a-133">Το http://localhost αρκεί για την ανάπτυξη μιας εφαρμογής στον τοπικό υπολογιστή σας.</span><span class="sxs-lookup"><span data-stu-id="2539a-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="2539a-134">Στη νέα καταχώρηση εφαρμογής, μεταβείτε στη διεύθυνση **Άδειες API**.</span><span class="sxs-lookup"><span data-stu-id="2539a-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Πώς να ορίσετε δικαιώματα API σε μια καταχώρηση εφαρμογής.":::

1. <span data-ttu-id="2539a-136">Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Customer Insights** στο πλευρικό τμήμα παραθύρου.</span><span class="sxs-lookup"><span data-stu-id="2539a-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="2539a-137">Για τον **Τύπο δικαιώματος**, επιλέξτε **Δικαιώματα με ανάθεση** και, στη συνέχεια, επιλέξτε το δικαίωμα **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="2539a-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="2539a-138">Επιλέξτε **Προσθήκη δικαιωμάτων**.</span><span class="sxs-lookup"><span data-stu-id="2539a-138">Select **Add permissions**.</span></span> <span data-ttu-id="2539a-139">Εάν πρέπει να αποκτήσετε πρόσβαση στο API χωρίς να συνδεθεί ένας χρήστης, ανατρέξτε στην ενότητα [Δικαιώματα εφαρμογής διακομιστή σε διακομιστή](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="2539a-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="2539a-140">Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="2539a-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="2539a-141">Μπορείτε να χρησιμοποιήσετε το Αναγνωριστικό εφαρμογής/πελάτη για αυτήν την καταχώρηση εφαρμογής στη Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL) για να αποκτήσετε ένα διακριτικό φορέα για αποστολή με το αίτημά σας στο API.</span><span class="sxs-lookup"><span data-stu-id="2539a-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Πώς να εκχωρήσετε συγκατάθεση διαχειριστή.":::

<span data-ttu-id="2539a-143">Για περισσότερες πληροφορίες σχετικά με το MSAL, δείτε [Επισκόπηση της Βιβλιοθήκης ελέγχου ταυτότητας της Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="2539a-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="2539a-144">Για περισσότερες πληροφορίες σχετικά με την καταχώρηση εφαρμογής στο Azure, ανατρέξτε στο θέμα [Καταχώρηση μιας εφαρμογής](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="2539a-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="2539a-145">Για πληροφορίες σχετικά με τη χρήση των API στις βιβλιοθήκες προγραμμάτων-πελατών μας, ανατρέξτε στις [βιβλιοθήκες προγραμμάτων Customer Insights](#customer-insights-client-libraries)Insights.</span><span class="sxs-lookup"><span data-stu-id="2539a-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="2539a-146">Δικαιώματα εφαρμογής διακομιστή σε διακομιστή</span><span class="sxs-lookup"><span data-stu-id="2539a-146">Server-to-server application permissions</span></span>

<span data-ttu-id="2539a-147">Η [ενότητα καταχώρησης εφαρμογής](#create-a-new-app-registration-in-the-azure-portal) περιγράφει τον τρόπο καταχώρησης μιας εφαρμογής που απαιτεί από έναν χρήστη να συνδεθεί για έλεγχο ταυτότητας.</span><span class="sxs-lookup"><span data-stu-id="2539a-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="2539a-148">Μάθετε πώς να δημιουργήσετε μια καταχώρηση εφαρμογής που δεν χρειάζεται αλληλεπίδραση χρήστη και να εκτελεστεί σε διακομιστή.</span><span class="sxs-lookup"><span data-stu-id="2539a-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="2539a-149">Στην καταχώρηση εφαρμογής στην πύλη Azure, μεταβείτε στο **Δικαιώματα API**.</span><span class="sxs-lookup"><span data-stu-id="2539a-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="2539a-150">Επιλέξτε **Προσθήκη δικαιώματος**.</span><span class="sxs-lookup"><span data-stu-id="2539a-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="2539a-151">Επιλέξτε τα **API τα οποία χρησιμοποιεί ο οργανισμός μου** και επιλέξτε από τη λίστα το **Dynamics 365 AI for Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="2539a-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="2539a-152">Για τον **Τύπο δικαιώματος**, επιλέξτε **Δικαιώματα εφαρμογής** και, στη συνέχεια, επιλέξτε το δικαίωμα **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="2539a-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="2539a-153">Επιλέξτε **Προσθήκη δικαιωμάτων**.</span><span class="sxs-lookup"><span data-stu-id="2539a-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="2539a-154">Επιστρέψτε στα **Δικαιώματα API** για την καταχώρηση της εφαρμογής σας.</span><span class="sxs-lookup"><span data-stu-id="2539a-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="2539a-155">Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="2539a-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Πώς να εκχωρήσετε συγκατάθεση διαχειριστή.":::

1. <span data-ttu-id="2539a-157">Συμπερασματικά, πρέπει να προσθέσουμε το όνομα της καταχώρησης εφαρμογής ως χρήστης στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2539a-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="2539a-158">Ανοίξτε το Customer Insights, μεταβείτε στο **Διαχειριστής** > **Δικαιώματα** και επιλέξτε **Προσθήκη χρήστη**.</span><span class="sxs-lookup"><span data-stu-id="2539a-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="2539a-159">Αναζητήστε το όνομα της καταχώρησης εφαρμογής, επιλέξτε την από τα αποτελέσματα αναζήτησης και επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="2539a-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="2539a-160">Βιβλιοθήκες πελατών Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2539a-160">Customer Insights client libraries</span></span>

<span data-ttu-id="2539a-161">Αυτή η ενότητα σάς βοηθά να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών που είναι διαθέσιμες για τα API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2539a-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="2539a-162">Μπορείτε να βρείτε ολόκληρο τον κώδικα προέλευσης βιβλιοθήκης και όλες τις εφαρμογές δειγμάτων στη σελίδα [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="2539a-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="2539a-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="2539a-163">C# NuGet</span></span>

<span data-ttu-id="2539a-164">Μάθετε πώς να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών C# από το NuGet.org. Για περισσότερες πληροφορίες σχετικά με το πακέτο NuGet, δείτε [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="2539a-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="2539a-165">Προς το παρόν, αυτό το πακέτο στοχεύει στα πλαίσια netstandard2.0 και netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="2539a-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="2539a-166">Προσθέστε τη βιβλιοθήκη πελάτη C# σε ένα έργο C#</span><span class="sxs-lookup"><span data-stu-id="2539a-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="2539a-167">Στο Visual Studio, άνοιξε το **Διαχειριστής πακέτων NuGet** για το έργο σας.</span><span class="sxs-lookup"><span data-stu-id="2539a-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="2539a-168">Αναζητήστε **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="2539a-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="2539a-169">Επιλέξτε **Εγκατάσταση** για να προσθέσετε το πακέτο στο έργο.</span><span class="sxs-lookup"><span data-stu-id="2539a-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="2539a-170">Εναλλακτικά, εκτελέστε αυτήν την εντολή στην **Κονσόλα διαχειριστή πακέτων NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="2539a-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Προσθήκ πακέτου NuGet σε έργο Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="2539a-172">Χρησιμοποιήστε τη βιβλιοθήκη πελάτη C#</span><span class="sxs-lookup"><span data-stu-id="2539a-172">Use the C# client library</span></span>

1. <span data-ttu-id="2539a-173">Χρησιμοποιήστε τη [Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) για να λάβετε ένα `AccessToken` χρησιμοποιώντας την υπάροχυσα [Καταχώρηση εφαρμογής Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2539a-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="2539a-174">Αφού ελέγξετε με επιτυχία την ταυτότητα και αποκτήσετε ένα διακριτικό, δημιουργήστε ένα νέο ή χρησιμοποιήστε ένα υπάρχον `HttpClient` με τον πρόσθετο **Έλεγχο ταυτότητας DefaultRequestHeaders** ορισμένο σε **Φορέας <access token>** και το **Ocp-Apim-Subscription-Key** ορισμένο σε [**κλειδί συνδρομής** από το περιβάλλον του Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="2539a-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="2539a-175">Επαναφέρετε την κεφαλίδα **Έλεγχος ταυτότητας** όταν χρειάζεται.</span><span class="sxs-lookup"><span data-stu-id="2539a-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="2539a-176">Για παράδειγμα, όταν έληξε το διακριτικό.</span><span class="sxs-lookup"><span data-stu-id="2539a-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="2539a-177">Περάστε αυτό το `HttpClient` στην κατασκευή του πελάτη `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="2539a-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Δείγμα httpclient":::

1. <span data-ttu-id="2539a-179">Πραγματοποιήστε κλήσεις με το πρόγραμμα-πελάτη στις «μεθόδους επέκτασης», για παράδειγμα, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="2539a-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="2539a-180">Εάν προτιμάτε την πρόσβαση στο υποκείμενο `Microsoft.Rest.HttpOperationResponse`, χρησιμοποιήστε τις «μεθόδους μηνυμάτων http», για παράδειγμα `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="2539a-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="2539a-181">Η απάντηση πιθανότατα θα είναι του τύπου `object` επειδή η μέθοδος μπορεί να επιστρέψει πολλούς τύπους (για παράδειγμα, `IList<InstanceInfo>` και `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="2539a-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="2539a-182">Για να ελέγξετε τον τύπο επιστροφής, μπορείτε να ρίξετε με ασφάλεια τα αντικείμενα στους τύπους απόκρισης που καθορίζονται στη [σελίδα λεπτομερειών API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) για αυτή τη λειτουργία.</span><span class="sxs-lookup"><span data-stu-id="2539a-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="2539a-183">Εάν χρειάζονται περισσότερες πληροφορίες σχετικά με την αίτηση, χρησιμοποιήστε τις **μεθόδους μηνυμάτων http** για πρόσβαση στο αντικείμενο ακατέργαστης απόκρισης.</span><span class="sxs-lookup"><span data-stu-id="2539a-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="2539a-184">Πακέτο NodeJS</span><span class="sxs-lookup"><span data-stu-id="2539a-184">NodeJS package</span></span>

<span data-ttu-id="2539a-185">Χρησιμοποιήστε τις βιβλιοθήκες υπολογιστών-πελατών NodeJS που είναι διαθέσιμες μέσω NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="2539a-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="2539a-186">Πακέτο Python</span><span class="sxs-lookup"><span data-stu-id="2539a-186">Python package</span></span>

<span data-ttu-id="2539a-187">Χρησιμοποιήστε τις βιβλιοθήκες υπολογιστών-πελατών Python που είναι διαθέσιμες μέσω PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="2539a-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
