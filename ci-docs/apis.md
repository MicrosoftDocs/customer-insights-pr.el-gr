---
title: Εργασία με API Customer Insights
description: Χρησιμοποιήστε API και κατανοήστε τους περιορισμούς.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387340"
---
# <a name="work-with-customer-insights-apis"></a>Εργασία με API Customer Insights

Το Dynamics 365 Customer Insights παρέχει API για τη δημιουργία των δικών σας εφαρμογών με βάση τα δεδομένα σας στο Customer Insights.

> [!IMPORTANT]
> Οι λεπτομέρειες αυτών των API παρατίθενται στην [αναφορά Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Περιλαμβάνουν πρόσθετες πληροφορίες σχετικά με τις λειτουργίες, τις παραμέτρους και τις αποκρίσεις.

Δοκιμάστε τα API του Customer Insights, δημιουργήστε μια καταχώρηση εφαρμογής Azure και ξεκινήστε με τις βιβλιοθήκες προγράμματος-πελάτη.

## <a name="get-started-trying-the-customer-insights-apis"></a>Έναρξη δοκιμής των API του Customer Insights

Ενεργοποιήστε τα API του Customer Insights και δοκιμάστε τα. Ένας διαχειριστής του Customer Insights πρέπει να ενεργοποιήσει την πρόσβαση μέσω API στο Customer Insights. Όταν ενεργοποιηθεί η πρόσβαση, κάθε χρήστης μπορεί να χρησιμοποιήσει το API με το κλειδί συνδρομής.

1. [Σύνδεση](https://home.ci.ai.dynamics.com) στο Customer Insights. Εάν δεν έχετε ακόμα συνδρομή, [εγγραφείτε για μια δοκιμαστική έκδοση του Customer Insights](https://aka.ms/tryci).

1. Μεταβείτε στα στοιχεία **Διαχειριστής** > **Ασφάλεια** > και επιλέξτε την καρτέλα **API**.

1. Εάν δεν έχει ρυθμιστεί η πρόσβαση μέσω API στο περιβάλλον, επιλέξτε **Ενεργοποίηση**.

   Η ενεργοποίηση των API δημιουργεί ένα πρωτεύον και δευτερεύον κλειδί συνδρομής για την παρουσία σας που χρησιμοποιείται στις αιτήσεις API. Για να ξαναδημιουργήσετε τα κλειδιά επιλέξτε **Ξαναδημιουργία πρωτεύοντος** ή **Ξαναδημιουργία δευτερεύοντος** στην καρτέλα **API**.

1. Επιλέξτε [**Εξερεύνηση των API μας**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) για να δοκιμάσετε τα API.

1. Αναζητήστε και επιλέξτε μια λειτουργία API και επιλέξτε **Δοκιμή**.

   :::image type="content" source="media/try-api.png" alt-text="Πώς να δοκιμάσετε τα API.":::

1. Στο πλαϊνό τμήμα παραθύρου, ορίστε την τιμή στο αναπτυσσόμενο μενού **Εξουσιοδότηση** σε **έμμεση**. Η κεφαλίδα `Authorization` προστίθεται με διακριτικό φορέα. Το κλειδί της συνδρομής σας θα συμπληρωθεί αυτόματα.
  
1. Προαιρετικά, προσθέστε όλες τις απαραίτητες παραμέτρους ερωτήματος.

1. Μεταβείτε στο κάτω μέρος του πλαϊνού τμήματος παραθύρου και επιλέξτε **Αποστολή**.

   Η απόκριση HTTP εμφανίζεται στο κάτω μέρος του τμήματος παραθύρου.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Δημιουργήστε μια νέα καταχώρησης εφαρμογής στην πύλη Azure

Δημιουργήστε μια νέα [καταχώριση εφαρμογής](/graph/auth-register-app-v2) για να χρησιμοποιήσετε τα API του Customer Insights σε μια εφαρμογή Azure χρησιμοποιώντας εξουσιοδοτημένα δικαιώματα.

1. Ολοκληρώστε την [ενότητα Έναρξη](#get-started-trying-the-customer-insights-apis).

1. Συνδεθείτε στην [Πύλη Azure](https://portal.azure.com) με τον λογαριασμό που μπορεί να έχει πρόσβαση στα δεδομένα του Customer Insights.

1. Αναζητήστε και, στη συνέχεια, επιλέξτε **Καταχωρίσεις εφαρμογών**.

1. Επιλέξτε **Νέα καταχώρηση**, δώστε ένα όνομα εφαρμογής και επιλέξτε τον τύπο λογαριασμού.

   Προαιρετικά, προσθέστε μια διεύθυνση URL ανακατεύθυνσης. Το http://localhost αρκεί για την ανάπτυξη μιας εφαρμογής στον τοπικό υπολογιστή σας.

1. Επιλέξτε **Καταχώρηση**.

1. Στη νέα καταχώρηση εφαρμογής, μεταβείτε στη διεύθυνση **Άδειες API**.

1. Επιλέξτε **Προσθήκη δικαιώματος** και επιλέξτε **Dynamics 365 AI για Customer Insights** στο πλαϊνό παράθυρο.

1. Για τον **Τύπο δικαιώματος**, επιλέξτε **Δικαιώματα με ανάθεση** και, στη συνέχεια, επιλέξτε το δικαίωμα **user_impersonation**.

1. Επιλέξτε **Προσθήκη δικαιωμάτων**.

1. Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.

1. Για να αποκτήσετε πρόσβαση στο API χωρίς να συνδεθεί ένας χρήστης, ανατρέξτε στην ενότητα [Δικαιώματα εφαρμογής διακομιστή σε διακομιστή](#server-to-server-application-permissions).

Μπορείτε να χρησιμοποιήσετε το Αναγνωριστικό εφαρμογής/πελάτη για αυτήν την καταχώρηση εφαρμογής στη [Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) για να αποκτήσετε ένα διακριτικό φορέα για αποστολή με το αίτημά σας στο API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Για πληροφορίες σχετικά με τη χρήση των API στις βιβλιοθήκες προγραμμάτων-πελατών μας, ανατρέξτε στις [βιβλιοθήκες προγραμμάτων Customer Insights](#customer-insights-client-libraries)Insights.

### <a name="server-to-server-application-permissions"></a>Δικαιώματα εφαρμογής διακομιστή σε διακομιστή

Δημιουργήστε μια καταχώρηση εφαρμογής που δεν χρειάζεται αλληλεπίδραση με το χρήστη και μπορεί να εκτελεστεί σε διακομιστή.

1. Στην καταχώρηση εφαρμογής στην πύλη Azure, μεταβείτε στο **Δικαιώματα API**.

1. Επιλέξτε **Προσθήκη δικαιώματος**.

1. Επιλέξτε τα **API τα οποία χρησιμοποιεί ο οργανισμός μου** και επιλέξτε από τη λίστα το **Dynamics 365 AI for Customer Insights**.

1. Για τον **Τύπο δικαιώματος**, επιλέξτε **Δικαιώματα εφαρμογής** και, στη συνέχεια, επιλέξτε το δικαίωμα **CustomerInsights.Api.All**.

1. Επιλέξτε **Προσθήκη δικαιωμάτων**.

1. Επιστρέψτε στα **Δικαιώματα API** για την καταχώρηση της εφαρμογής σας.

1. Επιλέξτε **Παραχώρηση συναίνεσης διαχειριστή για...** για να ολοκληρώσετε την καταχώρηση της εφαρμογής.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Προσθέστε το όνομα της καταχώρησης εφαρμογής ως χρήστης στο Customer Insights.

   1. Ανοίξτε το Customer Insights, μεταβείτε στο **Διαχειριστής** > **Ασφάλεια** και επιλέξτε **Προσθήκη χρηστών**.

   1. Αναζητήστε το όνομα της καταχώρησης εφαρμογής, επιλέξτε την από τα αποτελέσματα αναζήτησης και επιλέξτε **Αποθήκευση**.

## <a name="sample-queries"></a>Δείγματα ερωτημάτων

Για μια σύντομη λίστα δειγμάτων ερωτημάτων OData για εργασία με τα API δείτε [Παραδείγματα ερωτημάτων OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Βιβλιοθήκες πελατών Customer Insights

Ξεκινήστε να χρησιμοποιείτε τις βιβλιοθήκες πελατών που είναι διαθέσιμες για τα API Customer Insights. Μπορείτε να βρείτε ολόκληρο τον κώδικα προέλευσης βιβλιοθήκης και όλες τις εφαρμογές δειγμάτων στη σελίδα [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Χρησιμοποιήστε τις βιβλιοθήκες πελατών C# από το NuGet.org. Προς το παρόν, το πακέτο στοχεύει στα πλαίσια netstandard2.0 και netcoreapp2.0. Για περισσότερες πληροφορίες σχετικά με το πακέτο NuGet, δείτε [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Προσθέστε τη βιβλιοθήκη πελάτη C# σε ένα έργο C#

1. Στο Visual Studio, άνοιξε το **Διαχειριστής πακέτων NuGet** για το έργο σας.

1. Αναζητήστε **Microsoft.Dynamics.CustomerInsights.Api**.

1. Επιλέξτε **Εγκατάσταση** για να προσθέσετε το πακέτο στο έργο.

   Εναλλακτικά, εκτελέστε αυτήν την εντολή στην **Κονσόλα διαχειριστή πακέτων NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Χρησιμοποιήστε τη βιβλιοθήκη πελάτη C#

1. Χρησιμοποιήστε τη [Βιβλιοθήκη ελέγχου ταυτότητας της Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) για να λάβετε ένα `AccessToken` χρησιμοποιώντας την υπάροχυσα [Καταχώρηση εφαρμογής Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Αφού ολοκληρωθεί με επιτυχία ο έλεγχος ταυτότητας και η απόκτηση ενός διακριτικού, δόμησης ενός νέου ή της χρήσης ενός υπάρχοντος `HttpClient` με το **DefaultRequestHeaders "Εξουσιοδότηση"** να έχει οριστεί σε **Φορέας "διακριτικού πρόσβασης"** και **Ocp-Apim-Subscription-Key**, το οποίο έχει οριστεί στο [**κλειδί συνδρομής** από το περιβάλλον Customer Insights που έχετε](#get-started-trying-the-customer-insights-apis).   

   Επαναφέρετε την κεφαλίδα **Έλεγχος ταυτότητας** όταν χρειάζεται. Για παράδειγμα, όταν έληξε το διακριτικό.

1. Περάστε αυτό το `HttpClient` στην κατασκευή του πελάτη `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Πραγματοποιήστε κλήσεις με το πρόγραμμα-πελάτη στις «μεθόδους επέκτασης», για παράδειγμα, `GetAllInstancesAsync`. Εάν προτιμάτε την πρόσβαση στο υποκείμενο `Microsoft.Rest.HttpOperationResponse`, χρησιμοποιήστε τις «μεθόδους μηνυμάτων http», για παράδειγμα `GetAllInstancesWithHttpMessagesAsync`.

1. Η απάντηση πιθανότατα θα είναι του τύπου `object` επειδή η μέθοδος μπορεί να επιστρέψει πολλούς τύπους (για παράδειγμα, `IList<InstanceInfo>` και `ApiErrorResult`). Για να ελέγξετε τον τύπο επιστροφής, χρησιμοποιείτε τα αντικείμενα στους τύπους απάντησης που καθορίζονται στη [σελίδα λεπτομερειών API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) για αυτήν τη λειτουργία.

   Εάν χρειάζονται περισσότερες πληροφορίες σχετικά με την αίτηση, χρησιμοποιήστε τις **μεθόδους μηνυμάτων http** για πρόσβαση στο αντικείμενο ακατέργαστης απόκρισης.

### <a name="nodejs-package"></a>Πακέτο NodeJS

Χρησιμοποιήστε τις βιβλιοθήκες υπολογιστών-πελατών NodeJS που είναι διαθέσιμες μέσω NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Πακέτο Python

Χρησιμοποιήστε τις βιβλιοθήκες υπολογιστών-πελατών Python που είναι διαθέσιμες μέσω PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
