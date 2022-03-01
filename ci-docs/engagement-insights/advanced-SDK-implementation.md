---
title: Σενάρια web SDK για προχωρημένους
description: Σύνθετα σενάρια που πρέπει να ληφθούν υπόψη κατά την προσθήκη εργαλείων SDK στην τοποθεσία Web σας.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036328"
---
# <a name="advanced-web-sdk-instrumentation"></a>Σύνθετα εργαλεία SDK web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Αυτό το άρθρο σας καθοδηγεί στα σύνθετα σενάρια που θα πρέπει να λάβετε υπόψη κατά την [προσθήκη εργαλείων SDK στην τοποθεσία web σας](instrument-website.md) με SDK πληροφοριών δέσμευσης Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Ρύθμιση λεπτομερειών χρήστη για το συμβάν σας

Το SDK σάς επιτρέπει να ορίζετε πληροφορίες χρήστη που μπορούν να αποστέλλονται με κάθε συμβάν. Μπορείτε να καθορίσετε τις λεπτομέρειες χρήστη σε μια ιδιότητα που καλείται `user` (τα αναμενόμενα δεδομένα για αυτήν την ιδιότητα είναι το αντικείμενο `IUser`), παρόμοιο με τα `src`, `name` και `cfg` στη ρύθμιση παραμέτρων τμήματος κώδικα.

Το αντικείμενο `IUser` περιέχει τις ακόλουθες ιδιότητες συμβολοσειράς:

- **localId**: Το τοπικό αναγνωριστικό του χρήστη.
- **authId**: Το αναγνωριστικό χρήστη που έχει υποβληθεί σε έλεγχο ταυτότητας.
- **authType**: Ο τύπος ελέγχου ταυτότητας που χρησιμοποιείται για τη λήψη του αναγνωριστικού χρήστη που έχει υποβληθεί σε έλεγχο ταυτότητας.
- **name**: Το όνομα του χρήστη.
- **email**: Η διεύθυνση ηλεκτρονικού ταχυδρομείου του χρήστη.
    
Το παρακάτω παράδειγμα παρουσιάζει ένα τμήμα κώδικα που στέλνει πληροφορίες χρήστη. Όπου βλέπετε λειτουργίες που επισημαίνονται με *, αντικαταστήστε τις με κλήση αυτών των τιμών:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Μπορείτε επίσης να καθορίσετε πληροφορίες χρήστη καλώντας το `setUser(user: IUser)` API στο SDK. Η τηλεμετρία που αποστέλλεται μετά την κλήση του `setUser API` θα περιέχει τις πληροφορίες χρήστη.

## <a name="adding-custom-properties-for-each-event"></a>Προσθήκη προσαρμοσμένων ιδιοτήτων για κάθε συμβάν

Το SDK σάς επιτρέπει να προσδιορίσετε προσαρμοσμένες ιδιότητες που μπορούν να αποστέλλονται με κάθε συμβάν. Μπορείτε να καθορίσετε τις προσαρμοσμένες ιδιότητες ως αντικείμενο που περιέχει ζεύγη τιμών-κλειδιών (η τιμή μπορεί να είναι τύπου `string | number | boolean`). Το αντικείμενο μπορεί να προστεθεί σε μια ιδιότητα που ονομάζεται `props`, παρόμοια με τα `src`, `name` και `cfg` στη ρύθμιση παραμέτρων τμήματος κώδικα. 

Το παρακάτω παράδειγμα παρουσιάζει ένα τμήμα κώδικα που στέλνει προσαρμοσμένες ιδιότητες:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Μπορείτε επίσης να καθορίσετε προσαρμοσμένες ιδιότητες μεμονωμένα καλώντας το `setProperty(name: string, value: string | number | boolean)` στο SDK.

## <a name="sending-custom-events"></a>Αποστολή προσαρμοσμένων συμβάντων

Μπορείτε να χρησιμοποιήσετε το SDK για να στείλετε προσαρμοσμένα συμβάντα. Πρέπει να προσδιορίσετε ένα όνομα για το συμβάν και τις ιδιότητες που θα αποσταλούν μαζί με το συμβάν.

Το παρακάτω παράδειγμα παρουσιάζει ένα τμήμα κώδικα που παρακολουθεί ένα προσαρμοσμένο συμβάν. Το στοιχείο "NAME" είναι η τιμή του κλειδιού `name` στη ρύθμιση παραμέτρων τμήματος κώδικα. Είναι επίσης το όνομα της μεταβλητής στο αντικείμενο παραθύρου όπου φορτώνεται το SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]