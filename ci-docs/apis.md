---
title: Εργασία με API
description: Χρησιμοποιήστε API και κατανοήστε τους περιορισμούς.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: ecc8bb3dbec1d4583c4bf2a58058145343945299
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646796"
---
# <a name="work-with-customer-insights-apis"></a>Εργασία με API Customer Insights

Το Dynamics 365 Customer Insights παρέχει API για τη δημιουργία των δικών σας εφαρμογών με βάση τα δεδομένα σας στο Customer Insights.

> [!IMPORTANT]
> Οι λεπτομέρειες αυτών των API παρατίθενται στην [αναφορά Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Περιλαμβάνουν πρόσθετες πληροφορίες σχετικά με τις λειτουργίες, τις παραμέτρους και τις αποκρίσεις.

Σε αυτό το άρθρο περιγράφεται ο τρόπος με τον οποίο μπορείτε να αποκτήσετε πρόσβαση στα Customer Insights API, να δημιουργήσετε μια καταχώρηση εφαρμογής Azure και να ξεκινήσετε με τις διαθέσιμες βιβλιοθήκες προγραμμάτων-πελατών.

## <a name="get-started-trying-the-customer-insights-apis"></a>Έναρξη δοκιμής των API του Customer Insights

1. [Σύνδεση](https://home.ci.ai.dynamics.com) στο Customer Insights. Εάν δεν έχετε ακόμα συνδρομή, [εγγραφείτε για μια δοκιμαστική έκδοση του Customer Insights](https://aka.ms/tryci).

1. Για να ενεργοποιήσετε τα API στο περιβάλλον Customer Insights, μεταβείτε στην επιλογή **Διαχειριστής** > **Δικαιώματα**. Για να το κάνετε αυτό, θα χρειαστείτε δικαιώματα διαχειριστή.

1. Μεταβείτε στην καρτέλα **API** και επιλέξτε το κουμπί **Ενεργοποίηση**.    
 
   Η ενεργοποίηση των API δημιουργεί ένα πρωτεύον και δευτερεύον κλειδί συνδρομής για την παρουσία σας που χρησιμοποιείται στις αιτήσεις API. Μπορείτε να αναδημιουργήσετε τα κλειδιά επιλέγοντας την **Αναδημιουργία πρωτεύοντος** ή την **Αναδημιουργία δευτερευόντος** στα **Διαχειριστής** > **Δικαιώματα** > **API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Επιλέξτε **Εξερεύνηση των API μας** για να [δοκιμάσετε τα API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Επιλέξτε μια λειτουργία API και επιλέξτε **Δοκιμή**.

1. Στο πλαϊνό τμήμα παραθύρου, ορίστε την τιμή στο αναπτυσσόμενο μενού **Εξουσιοδότηση** σε **έμμεση**. Η κεφαλίδα `Authorization` προστίθεται με διακριτικό φορέα. Το κλειδί της συνδρομής σας θα συμπληρωθεί αυτόματα.
  
1. Προαιρετικά, προσθέστε όλες τις απαραίτητες παραμέτρους ερωτήματος.

1. Μεταβείτε στο κάτω μέρος του πλαϊνού τμήματος παραθύρου και επιλέξτε **Αποστολή**.

Η απόκριση HTTP θα εμφανιστεί σύντομα παρακάτω.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Δημιουργήστε μια νέα καταχώρησης εφαρμογής στην πύλη Azure

Αυτά τα βήματα σας βοηθούν να ξεκίνησετε με τη χρήση των Customer Insights API σε μια εφαρμογή Azure, χρησιμοποιώντας δικαιώματα με ανάθεση. Βεβαιωθείτε ότι ολοκληρώνετε πρώτα την [ενότητα Έναρξη](#get-started-trying-the-customer-insights-apis).

1. Συνδεθείτε στην [Πύλη Azure](https://portal.azure.com) με τον λογαριασμό που μπορεί να έχει πρόσβαση στα δεδομένα του Customer Insights.

1. Στα αριστερά, επιλέξτε **Εγγραφές εφαρμογών**.

1. Επιλέξτε **Νέα καταχώρηση**, δώστε ένα όνομα εφαρμογής και επιλέξτε τον τύπο λογαριασμού.
 
   Προαιρετικά, προσθέστε μια διεύθυνση URL ανακατεύθυνσης. Το http://localhost αρκεί για την ανάπτυξη μιας εφαρμογής στον τοπικό υπολογιστή σας.

1. Στη νέα καταχώρηση εφαρμογής, μεταβείτε στη διεύθυνση **Άδειες API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Customer Insights** στο πλευρικό τμήμα παραθύρου.

1. Για τον **Τύπο δικαιώματος**, επιλέξτε **Δικαιώματα με ανάθεση** και, στη συνέχεια, επιλέξτε το δικαίωμα **user_impersonation**.

1. Επιλέξτε **Προσθήκη δικαιωμάτων**. Εάν πρέπει να αποκτήσετε πρόσβαση στο API χωρίς να συνδεθεί ένας χρήστης, ανατρέξτε στην ενότητα [Δικαιώματα εφαρμογής διακομιστή σε διακομιστή](#server-to-server-application-permissions).

1. Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.

Μπορείτε να χρησιμοποιήσετε το Αναγνωριστικό εφαρμογής/πελάτη για αυτήν την καταχώρηση εφαρμογής στη Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL) για να αποκτήσετε ένα διακριτικό φορέα για αποστολή με το αίτημά σας στο API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Για περισσότερες πληροφορίες σχετικά με το MSAL, δείτε [Επισκόπηση της Βιβλιοθήκης ελέγχου ταυτότητας της Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Για περισσότερες πληροφορίες σχετικά με την καταχώρηση εφαρμογής στο Azure, ανατρέξτε στο θέμα [Καταχώρηση μιας εφαρμογής](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Για πληροφορίες σχετικά με τη χρήση των API στις βιβλιοθήκες προγραμμάτων-πελατών μας, ανατρέξτε στις [βιβλιοθήκες προγραμμάτων Customer Insights](#customer-insights-client-libraries)Insights.

### <a name="server-to-server-application-permissions"></a>Δικαιώματα εφαρμογής διακομιστή σε διακομιστή

Η [ενότητα καταχώρησης εφαρμογής](#create-a-new-app-registration-in-the-azure-portal) περιγράφει τον τρόπο καταχώρησης μιας εφαρμογής που απαιτεί από έναν χρήστη να συνδεθεί για έλεγχο ταυτότητας. Μάθετε πώς να δημιουργήσετε μια καταχώρηση εφαρμογής που δεν χρειάζεται αλληλεπίδραση χρήστη και να εκτελεστεί σε διακομιστή.

1. Στην καταχώρηση εφαρμογής στην πύλη Azure, μεταβείτε στο **Δικαιώματα API**.

1. Επιλέξτε **Προσθήκη δικαιώματος**. 

1. Επιλέξτε τα **API τα οποία χρησιμοποιεί ο οργανισμός μου** και επιλέξτε από τη λίστα το **Dynamics 365 AI for Customer Insights**. 

1. Για τον **Τύπο δικαιώματος**, επιλέξτε **Δικαιώματα εφαρμογής** και, στη συνέχεια, επιλέξτε το δικαίωμα **CustomerInsights.Api.All**.

1. Επιλέξτε **Προσθήκη δικαιωμάτων**.

1. Επιστρέψτε στα **Δικαιώματα API** για την καταχώρηση της εφαρμογής σας.

1. Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Συμπερασματικά, πρέπει να προσθέσουμε το όνομα της καταχώρησης εφαρμογής ως χρήστης στο Customer Insights.  
   
   Ανοίξτε το Customer Insights, μεταβείτε στο **Διαχειριστής** > **Δικαιώματα** και επιλέξτε **Προσθήκη χρήστη**.

1. Αναζητήστε το όνομα της καταχώρησης εφαρμογής, επιλέξτε την από τα αποτελέσματα αναζήτησης και επιλέξτε **Αποθήκευση**.

## <a name="customer-insights-client-libraries"></a>Βιβλιοθήκες πελατών Customer Insights

Αυτή η ενότητα σάς βοηθά να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών που είναι διαθέσιμες για τα API Customer Insights. Μπορείτε να βρείτε ολόκληρο τον κώδικα προέλευσης βιβλιοθήκης και όλες τις εφαρμογές δειγμάτων στη σελίδα [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Μάθετε πώς να ξεκινήσετε να χρησιμοποιείτε τις βιβλιοθήκες πελατών C# από το NuGet.org. Για περισσότερες πληροφορίες σχετικά με το πακέτο NuGet, δείτε [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Προς το παρόν, αυτό το πακέτο στοχεύει στα πλαίσια netstandard2.0 και netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Προσθέστε τη βιβλιοθήκη πελάτη C# σε ένα έργο C#

1. Στο Visual Studio, άνοιξε το **Διαχειριστής πακέτων NuGet** για το έργο σας.

1. Αναζητήστε **Microsoft.Dynamics.CustomerInsights.Api**.

1. Επιλέξτε **Εγκατάσταση** για να προσθέσετε το πακέτο στο έργο.
 
   Εναλλακτικά, εκτελέστε αυτήν την εντολή στην **Κονσόλα διαχειριστή πακέτων NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Χρησιμοποιήστε τη βιβλιοθήκη πελάτη C#

1. Χρησιμοποιήστε τη [Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) για να λάβετε ένα `AccessToken` χρησιμοποιώντας την υπάροχυσα [Καταχώρηση εφαρμογής Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Αφού ολοκληρωθεί με επιτυχία ο έλεγχος ταυτότητας και η απόκτηση ενός διακριτικού, δόμησης ενός νέου ή της χρήσης ενός υπάρχοντος `HttpClient` με το πρόσθετο **DefaultRequestHeaders "Εξουσιοδότηση"** να έχει οριστεί σε **Φορέας "διακριτικού πρόσβασης"** και **Ocp-Apim-Subscription-Key**, το οποίο έχει οριστεί στο [**κλειδί συνδρομής** από το περιβάλλον Customer Insights που έχετε](#get-started-trying-the-customer-insights-apis).   
 
   Επαναφέρετε την κεφαλίδα **Έλεγχος ταυτότητας** όταν χρειάζεται. Για παράδειγμα, όταν έληξε το διακριτικό.

1. Περάστε αυτό το `HttpClient` στην κατασκευή του πελάτη `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Πραγματοποιήστε κλήσεις με το πρόγραμμα-πελάτη στις «μεθόδους επέκτασης», για παράδειγμα, `GetAllInstancesAsync`. Εάν προτιμάτε την πρόσβαση στο υποκείμενο `Microsoft.Rest.HttpOperationResponse`, χρησιμοποιήστε τις «μεθόδους μηνυμάτων http», για παράδειγμα `GetAllInstancesWithHttpMessagesAsync`.

1. Η απάντηση πιθανότατα θα είναι του τύπου `object` επειδή η μέθοδος μπορεί να επιστρέψει πολλούς τύπους (για παράδειγμα, `IList<InstanceInfo>` και `ApiErrorResult`). Για να ελέγξετε τον τύπο επιστροφής, μπορείτε να ρίξετε με ασφάλεια τα αντικείμενα στους τύπους απόκρισης που καθορίζονται στη [σελίδα λεπτομερειών API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) για αυτή τη λειτουργία.    
   
   Εάν χρειάζονται περισσότερες πληροφορίες σχετικά με την αίτηση, χρησιμοποιήστε τις **μεθόδους μηνυμάτων http** για πρόσβαση στο αντικείμενο ακατέργαστης απόκρισης.

### <a name="nodejs-package"></a>Πακέτο NodeJS

Χρησιμοποιήστε τις βιβλιοθήκες υπολογιστών-πελατών NodeJS που είναι διαθέσιμες μέσω NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Πακέτο Python

Χρησιμοποιήστε τις βιβλιοθήκες υπολογιστών-πελατών Python που είναι διαθέσιμες μέσω PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
