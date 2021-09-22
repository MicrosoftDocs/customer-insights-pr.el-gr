---
title: Ξεκινήστε με το iOS SDK
description: Μάθετε πως να εξατομικεύετε και να εκτελείτε το iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036873"
---
# <a name="get-started-with-the-ios-sdk"></a>Ξεκινήστε με το iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Αυτό το πρόγραμμα εκμάθησης σας καθοδηγεί στη διαδικασία των οργάνων της iOS εφαρμογής σας με τα στατιστικά στοιχεία αφοσίωσης SDK του Dynamics 365 Customer Insights. Θα αρχίσετε να βλέπετε συμβάντα στην πύλη σας σε πέντε λεπτά ή πιο γρήγορα.

## <a name="configuration-options"></a>Επιλογές ρύθμισης παραμέτρων

Οι παρακάτω επιλογές ρύθμισης παραμέτρων μπορούν να περάσουν στο SDK μέσω του παρεχόμενου αρχείου `EIConfig.plist`:

- **ingestionKey**: Το κλειδί πρόσληψης χρησιμοποιείται για την αποστολή συμβάντων στο έργο σας.
- **autocollectAction**: Μια τιμή δυαδικής τιμής για ενεργοποίηση ή απενεργοποίηση της αυτόματης ενοργάνωσης του συμβάντος ενέργειας.
- **autocollectView**: Μια τιμή δυαδικής τιμής για ενεργοποίηση ή απενεργοποίηση της αυτόματης ενοργάνωσης του συμβάντος προβολής.
- **endpointUrl**: Η διεύθυνση URL τελικού σημείου όπου θα κατευθύνονται τα συμβάντα.

## <a name="prerequisites"></a>Προϋποθέσεις

- Xcode έκδοση 9+
- iOS έκδοση 8.2+
- Κλειδί πρόσληψης (δείτε παρακάτω για οδηγίες σχετικά με τον τρόπο λήψης)

## <a name="integrate-the-sdk-into-your-application"></a>Ενσωμάτωση του SDK στην εφαρμογή σας

Ξεκινήστε τη διαδικασία επιλέγοντας έναν χώρο εργασίας όπου θα εργαστείτε, επιλέγοντας την κινητή πλατφόρμα iOS και πραγματοποιώντας λήψη του SDK.

- Χρησιμοποιήστε την εναλλαγή χώρου εργασίας στο αριστερό τμήμα παραθύρου περιήγησης, για να επιλέξετε τον χώρο εργασίας σας.

- Εάν δεν έχετε έναν υπάρχοντα χώρο εργασίας, επιλέξτε **Νέος χώρος εργασίας** και ακολουθήστε τα βήματα για τη δημιουργία ενός [νέου χώρου εργασίας](create-workspace.md).

## <a name="configure-the-sdk"></a>Ρύθμιση παραμέτρων του SDK

Αφού κάνετε λήψη του SDK, μπορείτε να εργαστείτε με αυτό στο Xcode για να ενεργοποιήσετε και να καθορίσετε συμβάντα.

1. Αφού δημιουργήσετε έναν χώρο εργασίας, μεταβείτε στο μενού **Διαχείριση** > **Χώρος εργασίας** και, έπειτα, επιλέξτε **Οδηγός εγκατάστασης**.

1. Πραγματοποιήστε λήψη των [iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) και τοποθετήστε το αρχείο `EIObjC.xcframework` στον φάκελο `Frameworks`.

1. Εάν δεν υπάρχει φάκελος `Frameworks`, δημιουργήστε έναν στο φάκελο έργου.

## <a name="enable-auto-instrumentation"></a>Ενεργοποίηση αυτόματης ενοργάνωσης
 
Μπορείτε εύκολα να ενεργοποιήσετε την αυτόματη ενοργάνωση χωρίς κωδικοποίηση. Όταν εκτελείται το έργο, θα παρακολουθεί αυτόματα τα συμβάντα `view` και `action` χρησιμοποιώντας το διαμορφωμένο κλειδί πρόσληψης. 

1. Ενημερώστε και συμπεριλάβετε το παρεχόμενο αρχείο `EIConfig.plist` στον φάκελο καταλόγου έργου για τα ακόλουθα πεδία:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ΝΑΙ
    - autocollectAction = ΝΑΙ

2. Στη συνέχεια, προσθέστε το αρχείο `EIConfig.plist` στο έργο σας στο Xcode. 



Για να απενεργοποιήσετε την αυτόματη ενοργάνωση, ενημερώστε τα παρακάτω πεδία στον συμπεριλαμβανόμενο αρχείο `EIConfig.plist` στον φάκελο καταλόγου έργου. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Υλοποίηση προσαρμοσμένων συμβάντων

1. Ανοίξτε το έργο σε Xcode και μεταβείτε στις ρυθμίσεις **Γενικά**. 
1. Προσθέστε το έργο `EIObjC.xcframework` στην ενότητα "Πλαίσια, βιβλιοθήκες και ενσωματωμένο περιεχόμενο".

1. Εισαγάγετε το αρχείο κεφαλίδας πλαισίου στο AppDelegate.m με το ακόλουθο τμήμα:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Αρχικοποίηση των στατιστικών στοιχείων αφοσίωσης του SDK από το application: didFinishLaunchingWithOptions.
1. Αντιγράψτε το τμήμα κώδικα XML από τον **Οδηγό εγκατάστασης**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Παρακολούθηση συμβάντος:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Καθορισμός λεπτομερειών χρήστη για το συμβάν σας

Το SDK σάς επιτρέπει να ορίζετε πληροφορίες χρήστη που μπορούν να αποστέλλονται με κάθε συμβάν. Μπορείτε να καθορίσετε τις πληροφορίες χρήστη καλώντας το `setUser:(nonnull EIUser *)user` API στο SDK.

Ο καθορισμός των λεπτομερειών χρήστη στο επίπεδο `Analytics` σημαίνει ότι όλες οι τηλεμετρίας θα έχουν αυτές τις πληροφορίες. Ωστόσο, εάν καθορίσετε στο επίπεδο συμβάντος καλώντας το `setUser:(nonnull EIUser *)user` API στο αντικείμενο EIEvent, μόνο το συγκεκριμένο συμβάν θα περιέχει τις πληροφορίες.

Η κλάση δεδομένων `EIUser` περιέχει τις ακόλουθες ιδιότητες NSString:

- **localId**: Το τοπικό αναγνωριστικό του χρήστη.
- **authId**: Το αναγνωριστικό χρήστη που έχει υποβληθεί σε έλεγχο ταυτότητας.
- **authType**: Ο τύπος ελέγχου ταυτότητας που χρησιμοποιείται για τη λήψη του αναγνωριστικού χρήστη που έχει υποβληθεί σε έλεγχο ταυτότητας.
- **name**: Το όνομα του χρήστη.
- **email**: Η διεύθυνση ηλεκτρονικού ταχυδρομείου του χρήστη.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
