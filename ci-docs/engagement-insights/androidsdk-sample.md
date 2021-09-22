---
title: Δείγμα Android SDK
description: Δείγμα έργου για να μάθετε σχετικά με το SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035826"
---
# <a name="run-the-android-sdk-sample"></a>Εκτέλεση του δείγματος SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Αυτό το δείγμα έργου Android σάς βοηθά να κατανοήσετε τον τρόπο με τον οποίο λειτουργεί το SDK σε μια εφαρμογή. Δεν χρειάζετε να συντάξετε κώδικα. Απλά προσθέστε το κλειδί πρόσληψης και μπορείτε να δείτε τα συμβάντα στον χώρο εργασίας σας αμέσως.

## <a name="prerequisites"></a>Προϋποθέσεις

- [Android Studio](https://developer.android.com/studio)
- [Κλειδί πρόσληψης](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Λήψη του δείγματος SDK Android

1. [Λήψη του δείγματος SDK Android στατιστικών στοιχείων αφοσίωσης](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Αποσυμπιέστε το συμπιεσμένο αρχείο `ei-android-sample.zip`.
1. Ανοίξτε το φάκελο που δεν έχει ανοίξει στο Android Studio.
1. Στο αρχείο `AndroidManifest.xml`, αντικαταστήστε τη συμβολοσειρά `"Your-Ingestion-Key"` με το κλειδί πρόσληψης του χώρου εργασίας σας από τα στατιστικά στοιχεία αφοσίωσης στην ενότητα **Διαχείριση** > **Χώρος εργασίας** > **Οδηγός εγκατάστασης**. 

   > [!NOTE]
   > Δεν χρειάζεται να αντικαταστήσετε την ενότητα `${applicationId}`. Συμπληρώνεται αυτόματα.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Επιλέξτε **Εκτέλεση**, για να ξεκινήσετε το δείγμα έργου.
1. Προβάλετε τα συμβάντα στον χώρο εργασίας σας.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
