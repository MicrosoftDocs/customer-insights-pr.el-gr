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
# <a name="work-with-customer-insights-apis"></a>Εργασία με API Customer Insights

Το Dynamics 365 Customer Insights παρέχει API για τη δημιουργία των δικών σας εφαρμογών με βάση τα δεδομένα σας στο Customer Insights.

> [!IMPORTANT]
> Οι λεπτομέρειες αυτών των API, περιλαμβάνονται στην [αναφορά API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Περιλαμβάνουν πρόσθετες πληροφορίες σχετικά με τις λειτουργίες, τις παραμέτρους και τις αποκρίσεις.

Αυτό το άρθρο σάς καθοδηγεί για να αποκτήσετε πρόσβαση στα API Customer Insights, να δημιουργήσετε μια καταχώρηση εφαρμογής Azure και σας βοηθάει να ξεκινήσετε με τις διαθέσιμες βιβλιοθήκες προγραμμάτων-πελατών.

## <a name="get-started-trying-the-customer-insights-apis"></a>Έναρξη δοκιμής των API του Customer Insights

1. [Σύνδεση](https://home.ci.ai.dynamics.com) στο Customer Insights. Εάν δεν έχετε ακόμα συνδρομή, [εγγραφείτε για μια δοκιμαστική έκδοση του Customer Insights](https://aka.ms/tryci).

1. Για να ενεργοποιήσετε τα API στο περιβάλλον Customer Insights, μεταβείτε στην επιλογή **Διαχειριστής** > **Δικαιώματα**. Για να το κάνετε αυτό, θα χρειαστείτε δικαιώματα διαχειριστή.

1. Μεταβείτε στην καρτέλα **API** και επιλέξτε το κουμπί **Ενεργοποίηση**.    
   Η ενεργοποίηση των API δημιουργεί ένα πρωτεύον και δευτερεύον κλειδί συνδρομής για την παρουσία σας που χρησιμοποιείται στις αιτήσεις API. Μπορείτε να αναδημιουργήσετε τα κλειδιά επιλέγοντας την **Αναδημιουργία πρωτεύοντος** ή την **Αναδημιουργία δευτερευόντος** στα **Διαχειριστής** > **Δικαιώματα** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Ενεργοποίηση API Customer Insights":::

1. Επιλέξτε **Εξερεύνηση των API μας** για να δοκιμάσετε τα API.

1. Επιλέξτε μια λειτουργία API και επιλέξτε **Δοκιμή**.

1. Στο πλευρικό τμήμα παραθύρου, ορίστε την τιμή στο αναπτυσσόμενο μενού **Εξουσιοδότηση** σε **σιωπηρή**. Η κεφαλίδα `Authorization` αποκτάται με ένα διακριτικό κομιστή που προστίθεται. Το κλειδί της συνδρομής σας θα συμπληρωθεί αυτόματα.
  
1. Προαιρετικά, προσθέστε όλες τις απαραίτητες παραμέτρους ερωτήματος.

1. Μεταβείτε στο κάτω μέρος του πλαϊνού τμήματος παραθύρου και επιλέξτε **Αποστολή**.

Η απόκριση HTTP θα εμφανιστεί σύντομα παρακάτω.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Δημιουργήστε μια νέα καταχώρησης εφαρμογής στην πύλη Azure

Αυτά τα βήματα σάς βοηθούν να ξεκινήσετε τη χρήση των API Customer Insights σε μια εφαρμογή Azure χρησιμοποιώντας εξουσιοδοτημένα δικαιώματα. Βεβαιωθείτε ότι έχετε ολοκληρώσει την [ενότητα Έναρξη](#get-started-trying-the-customer-insights-apis) πρώτα.

1. Συνδεθείτε στην [Πύλη Azure](https://portal.azure.com) με τον λογαριασμό που μπορεί να έχει πρόσβαση στα δεδομένα του Customer Insights.

1. Στα αριστερά, επιλέξτε **Εγγραφές εφαρμογών**.

1. Επιλέξτε **Νέα καταχώρηση** δώστε ένα όνομα εφαρμογής και επιλέξτε τον τύπο λογαριασμού.
   Προαιρετικά, προσθέστε μια διεύθυνση URL ανακατεύθυνσης. Το http://localhost αρκεί για την ανάπτυξη μιας εφαρμογής στον τοπικό υπολογιστή σας.

1. Στη νέα καταχώρηση εφαρμογής, μεταβείτε στη διεύθυνση **Άδειες API**.

1. Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Customer Insights** στο πλευρικό τμήμα παραθύρου.

1. Για τον **Τύπο δικαιωμάτων**, επιλέξτε **Εκχωρημένα δικαιώματα** και επιλέξτε το δικαίωμα **user_impersonation** .

1. Επιλέξτε **Προσθήκη δικαιωμάτων**. Εάν πρέπει να αποκτήσετε πρόσβαση στο API χωρίς να συνδεθεί ένας χρήστης, ανατρέξτε στην ενότητα [Δικαιώματα εφαρμογής διακομιστή σε διακομιστή](#server-to-server-application-permissions).

1. Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.

Μπορείτε να χρησιμοποιήσετε το Αναγνωριστικό εφαρμογής/πελάτη για αυτήν την καταχώρηση εφαρμογής στη Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL) για να αποκτήσετε ένα διακριτικό φορέα για αποστολή με το αίτημά σας στο API.

Για περισσότερες πληροφορίες σχετικά με το MSAL, δείτε [Επισκόπηση της Βιβλιοθήκης ελέγχου ταυτότητας της Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Για περισσότερες πληροφορίες σχετικά με την καταχώρηση εφαρμογών στο Azure, δείτε [Η νέα εμπειρία καταχώρησης εφαρμογών της πύλης Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Για πληροφορίες σχετικά με τη χρήση των API των βιβλιοθηκών πελατών μας, δείτε [Βιβλιοθήκες πελατών Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Δικαιώματα εφαρμογής διακομιστή σε διακομιστή

Η [ενότητα καταχώρησης εφαρμογής](#create-a-new-app-registration-in-the-azure-portal) περιγράφει τον τρόπο καταχώρησης μιας εφαρμογής που απαιτεί από έναν χρήστη να συνδεθεί για έλεγχο ταυτότητας. Μάθετε πώς να δημιουργήσετε μια καταχώρηση εφαρμογής που δεν χρειάζεται αλληλεπίδραση χρήστη και να εκτελεστεί σε διακομιστή.

1. Στην καταχώρηση εφαρμογής στην πύλη Azure, μεταβείτε στο **Δικαιώματα API**.

1. Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Customer Insights** στο πλευρικό τμήμα παραθύρου.

1. Για τον **Τύπο δικαιωμάτων**, επιλέξτε **Δικαιώματα εφαρμογής** και επιλέξτε το δικαίωμα **CustomerInsights.Api.All** .

1. Επιλέξτε **Προσθήκη δικαιωμάτων**.

1. Για να δώσετε τη συγκατάθεση του διαχειριστή σε αυτό το δικαίωμα εφαρμογής, πρέπει να προσθέσετε έναν Διευθυντή εξυπηρέτησης.

   1. Εγκαταστήστε τη μονάδα Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Συνδεθείτε στον λογαριασμό AD: `Connect-AzureAD -TenantId <your tenant id>`. Μπορείτε να βρείτε το αναγνωριστικό μισθωτή σας στην **Επισκόπηση** > **Azure Active Directory**.
   1. Εκτελέστε την ακόλουθη εντολή για να προσθέσετε έναν Διευθυντής εξυπηρέτησης Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Η παράμετρος AppId σχετίζεται με την εφαρμογή Customer Insights API.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Δείγμα διευθυντή εξυπηρέτησης":::

1. Επιστρέψτε στα **Δικαιώματα API** για την καταχώρηση της εφαρμογής σας.

1. Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.

1. Συμπερασματικά, πρέπει να προσθέσουμε το όνομα της καταχώρησης εφαρμογής ως χρήστης στο Customer Insights.    
   Ανοίξτε το Customer Insights, μεταβείτε στο **Διαχειριστής** > **Δικαιώματα** και επιλέξτε **Προσθήκη χρήστη**.

1. Αναζητήστε το όνομα της καταχώρησης εφαρμογής, επιλέξτε την από τα αποτελέσματα αναζήτησης και επιλέξτε **Αποθήκευση**.

## <a name="customer-insights-client-libraries"></a>Βιβλιοθήκες πελατών Customer Insights

Αυτή η ενότητα σάς βοηθά να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών που είναι διαθέσιμες για τα API Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Μάθετε πώς να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών C# από το NuGet.org. Για περισσότερες πληροφορίες σχετικά με το πακέτο NuGet, δείτε [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Προς το παρόν, αυτό το πακέτο στοχεύει στα πλαίσια netstandard2.0 και netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Προσθέστε τη βιβλιοθήκη πελάτη C# σε ένα έργο C#

1. Στο Visual Studio, άνοιξε το **Διαχειριστής πακέτων NuGet** για το έργο σας.

1. Αναζητήστε **Microsoft.Dynamics.CustomerInsights.Api**.

1. Επιλέξτε **Εγκατάσταση** για να προσθέσετε το πακέτο στο έργο.
   Εναλλακτικά, εκτελέστε αυτήν την εντολή στην **Κονσόλα διαχειριστή πακέτων NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Προσθήκ πακέτου NuGet σε έργο Visual Studio":::

#### <a name="use-the-c-client-library"></a>Χρησιμοποιήστε τη βιβλιοθήκη πελάτη C#

1. Χρησιμοποιήστε τη [Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) για να λάβετε ένα `AccessToken` χρησιμοποιώντας την υπάροχυσα [Καταχώρηση εφαρμογής Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Αφού ελέγξετε με επιτυχία την ταυτότητα και αποκτήσετε ένα διακριτικό, δημιουργήστε ένα νέο ή χρησιμοποιήστε ένα υπάρχον `HttpClient` με τον πρόσθετο **Έλεγχο ταυτότητας DefaultRequestHeaders** ορισμένο σε **Φορέας <access token>** και το **Ocp-Apim-Subscription-Key** ορισμένο σε [**κλειδί συνδρομής** από το περιβάλλον του Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Επαναφέρετε την κεφαλίδα **Έλεγχος ταυτότητας** όταν χρειάζεται. Για παράδειγμα, όταν έληξε το διακριτικό.

1. Περάστε αυτό το `HttpClient` στην κατασκευή του πελάτη `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Δείγμα httpclient":::

1. Πραγματοποιήστε κλήσεις με το πρόγραμμα-πελάτη στις «μεθόδους επέκτασης», για παράδειγμα, `GetAllInstancesAsync`. Εάν προτιμάτε την πρόσβαση στο υποκείμενο `Microsoft.Rest.HttpOperationResponse`, χρησιμοποιήστε τις «μεθόδους μηνυμάτων http», για παράδειγμα `GetAllInstancesWithHttpMessagesAsync`.

1. Η απάντηση πιθανότατα θα είναι του τύπου `object` επειδή η μέθοδος μπορεί να επιστρέψει πολλούς τύπους (για παράδειγμα, `IList<InstanceInfo>` και `ApiErrorResult`). Για να ελέγξετε τον τύπο επιστροφής, μπορείτε να ρίξετε με ασφάλεια τα αντικείμενα στους τύπους απόκρισης που καθορίζονται στη [σελίδα λεπτομερειών API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) για αυτή τη λειτουργία.    
   Εάν χρειάζονται περισσότερες πληροφορίες σχετικά με την αίτηση, χρησιμοποιήστε τις **μεθόδους μηνυμάτων http** για πρόσβαση στο αντικείμενο ακατέργαστης απόκρισης.


[!INCLUDE[footer-include](../includes/footer-banner.md)]