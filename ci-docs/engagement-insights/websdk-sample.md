---
title: Εκτέλεση δείγματος SDK διαδικτύου
description: Μάθετε πώς να εξατομικεύσετε και να εκτελέσετε ένα δείγμα SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606213"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Εκτέλεση του δείγματος SDK web για τη δυνατότητα πληροφοριών δέσμευσης του Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Η βιβλιοθήκη SDK web της δυνατότητας πληροφοριών δέσμευσης είναι μια βιβλιοθήκη JavaScript με δείγμα κώδικα που μπορείτε να χρησιμοποιήσετε στην τοποθεσία Web σας.

## <a name="prerequisites"></a>Προϋποθέσεις

- Εγκατάσταση [Κώδικα Visual Studio](https://code.visualstudio.com/).
- [Εγκατάσταση της επέκτασης Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) σε Κώδικα Visual Studio και εξοικείωση με τον τρόπο εκτέλεσης του Live Server.
- Πρέπει να έχετε ένα [χώρο εργασίας πληροφοριών δέσμευσης](create-workspace.md).

## <a name="run-sample"></a>Εκτέλεση δείγματος

1. [Πραγματοποιήστε λήψη του δείγματος SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Αποσυμπιέστε το συμπιεσμένο αρχείο `ei_websdk_sample.zip`.

1. Ανοίξτε τον αποσυμπιεσμένο φάκελο στον Κώδικα Visual Studio.

1. Μεταβείτε στην πύλη πληροφοριών δέσμευσης για το χώρο εργασίας σας. Επιλέξτε **Διαχειριστή** > **χώρο εργασίας** και, στη συνέχεια, τον **οδηγό εγκατάστασης**. Ακολουθήστε την πρώτη επιλογή και επιλέξτε **Αντιγραφή κώδικα** για να αντιγράψετε το τμήμα κώδικα JavaScript .

1. Στο αρχείο `ei_websdk_sample.html`, επικολλήστε το αρχείο τμήμα κώδικα που μόλις αντιγράψατε κάτω από αυτήν τη γραμμή:

   - <-- ΕΠΙΚΟΛΛΗΣΤΕ ΤΟ ΤΜΗΜΑ ΚΩΔΙΚΑ JAVASCRIPT ΑΠΟ ΤΗΝ ΠΥΛΗ ΔΕΣΜΕΥΣΗΣ ΠΛΗΡΟΦΟΡΙΩΝ ΕΔΩ ΚΑΤΩ ΑΠΟ ΑΥΤΗΝ ΤΗ ΓΡΑΜΜΗ -->

1. Ανοίξτε το αρχείο `ei_websdk_sample.html` χρησιμοποιώντας το Live Server στον Κώδικα Visual Studio επιλέγοντας **Go Live** από τη γραμμή κατάστασης.

1. Κατά το άνοιγμα της σελίδας, θα πρέπει να αποσταλεί αυτόματα ένα συμβάν προβολής. Εάν κάνετε κλικ σε οποιοδήποτε από τα κουμπιά της σελίδας, θα σταλούν συμβάντα ενεργειών. Το κουμπί **Παρακολούθηση συμβάντων** θα στείλει επίσης προσαρμοσμένα συμβάντα. Εάν επιλέξετε το κουμπί **Μετάβαση στο Bing** θα σταλεί ένα συμβάν ενέργειας πριν την περιήγηση στην τοποθεσία Web του Bing.

1. Δείτε τη ροή συμβάντων κατά την περιήγηση στο χώρο εργασίας σας. Αυτός ο χώρος εργασίας συσχετίζεται με το κλειδί ενσωμάτωσης που καταχωρήθηκε στο Βήμα 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
