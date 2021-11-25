---
title: Ξεκινήστε με το Android SDK
description: Μάθετε πως να εξατομικεύετε και να εκτελείτε το Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655342"
---
# <a name="get-started-with-the-android-sdk"></a>Ξεκινήστε με το Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Αυτό το πρόγραμμα εκμάθησης σας καθοδηγεί στη διαδικασία των οργάνων της Android εφαρμογής σας με τις πληροφορίες αφοσίωσης SDK του Dynamics 365 Customer Insights. Θα αρχίσετε να βλέπετε συμβάντα στην πύλη σας σε πέντε λεπτά ή πιο γρήγορα.

## <a name="configuration-options"></a>Επιλογές ρύθμισης παραμέτρων
Μπορείτε να διαβιβάσετε τις ακόλουθες επιλογές ρύθμισης παραμέτρων στο SDK:

- **ingestionKey**: Το κλειδί πρόσληψης χρησιμοποιείται για την αποστολή συμβάντων στον χώρο εργασίας σας.

## <a name="prerequisites"></a>Προϋποθέσεις

- Android Studio

- Ελάχιστο επίπεδο Android API: 16 (Jelly Bean)

- Κλειδί πρόσληψης (δείτε παρακάτω για οδηγίες σχετικά με τον τρόπο λήψης)

## <a name="integrate-the-sdk-into-your-application"></a>Ενσωμάτωση του SDK στην εφαρμογή σας
Ξεκινήστε τη διαδικασία επιλέγοντας έναν χώρο εργασίας, επιλέγοντας την κινητή πλατφόρμα Android και πραγματοποιώντας λήψη του Android SDK.

- Χρησιμοποιήστε την εναλλαγή χώρου εργασίας στο αριστερό τμήμα παραθύρου περιήγησης, για να επιλέξετε τον χώρο εργασίας σας.

- Εάν δεν έχετε έναν υπάρχοντα χώρο εργασίας, επιλέξτε **Νέος χώρος εργασίας** και ακολουθήστε τα βήματα για τη δημιουργία ενός [νέου χώρου εργασίας](create-workspace.md).

- Αφού δημιουργήσετε έναν χώρο εργασίας, μεταβείτε στο μενού **Διαχείριση** > **Χώρος εργασίας** και, έπειτα, επιλέξτε **Οδηγός εγκατάστασης**.

## <a name="configure-the-sdk"></a>Ρύθμιση παραμέτρων του SDK

Αφού κάνετε λήψη του SDK, μπορείτε να εργαστείτε με αυτό στο Android Studio για να ενεργοποιήσετε και να καθορίσετε συμβάντα. Υπάρχουν δύο τρόποι για να το κάνετε αυτό:
### <a name="option-1-use-jitpack-recommended"></a>Επιλογή 1: Χρήση JitPack (συνιστάται)
1. Προσθέστε την αποθήκη JitPack στη ρίζα `build.gradle` σας:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Προσθέστε την εξάρτηση:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Επιλογή 2. Χρήση σύνδεσης λήψης
1. Πραγματοποιήστε λήψη [των στατιστικών αφοσίωσης του Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) και τοποθετήστε το αρχείο στο `eiandroidsdk-debug.aar` στον φάκελο `libs`.

1. Ανοίξτε το αρχείο `build.gradle` σε επίπεδο έργου και προσθέστε τα ακόλουθα τμήματα:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Ενεργοποίηση αυτόματης ενοργάνωσης

1. Προσθέστε δικαιώματα για το δίκτυο και το internet στο αρχείο `AndroidManifest.xml` σας που βρίσκεται κάτω από τον φάκελο `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Διαμορφώστε τη ρύθμιση παραμέτρων στατιστικών αφοσίωσης SDK μέσω του αρχείου `AndroidManifest.xml` σας.

1. Αντιγράψτε το τμήμα κώδικα XML από τον **Οδηγό εγκατάστασης**. Το `Your-Ingestion-Key` πρέπει να συμπληρωθεί αυτόματα.

   > [!NOTE]
   > Δεν χρειάζεται να αντικαταστήσετε την ενότητα `${applicationId}`. Συμπληρώνεται αυτόματα.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Ενεργοποιήστε ή απενεργοποιήστε την αυτόματη καταγραφή των συμβάντων `View` ορίζοντας το παραπάνω πεδίο `autoCapture` σε `true` ή `false`. 

   >[!NOTE]
   >Τα συμβάντα `Action` πρέπει να προστεθούν με μη αυτόματο τρόπο.

1. (Προαιρετικό) Άλλες ρυθμίσεις παραμέτρων περιλαμβάνουν τη ρύθμιση της διεύθυνσης URL τελικού σημείου. Μπορούν να προστεθούν στα μεταδεδομένα κλειδιών πρόσληψης στην ενότητα `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Υλοποίηση προσαρμοσμένων συμβάντων

Μετά την αρχικοποίηση του SDK, μπορείτε να εργαστείτε με συμβάντα και τις ιδιότητές τους στο περιβάλλον `MainActivity`.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Ορισμός ιδιότητας για όλα τα συμβάντα (προαιρετικό)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Οι παρακάτω τύποι υποστηρίζονται για τις ιδιότητες συμβάντος περιβάλλοντος:
- String
- Ημερομηνία
- Διπλή
- Μεγάλου μήκους
- Δυαδική τιμή
- UUID

### <a name="track-an-event"></a>Παρακολούθηση συμβάντος

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Καθορισμός λεπτομερειών χρήστη για το συμβάν σας (προαιρετικό)

Το SDK σάς επιτρέπει να ορίζετε πληροφορίες χρήστη που μπορούν να αποστέλλονται με κάθε συμβάν. Μπορείτε να καθορίσετε τις πληροφορίες χρήστη καλώντας το `setUser(user: User)` API στο επίπεδο `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Η κλάση δεδομένων `User` περιέχει τις ακόλουθες ιδιότητες συμβολοσειράς:

- **localId**: Το τοπικό αναγνωριστικό του χρήστη.
- **authId**: Το αναγνωριστικό χρήστη που έχει υποβληθεί σε έλεγχο ταυτότητας.
- **authType**: Ο τύπος ελέγχου ταυτότητας που χρησιμοποιείται για τη λήψη του αναγνωριστικού χρήστη με έλεγχο ταυτότητας.
- **name**: Το όνομα του χρήστη.
- **email**: Η διεύθυνση ηλεκτρονικού ταχυδρομείου του χρήστη.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
