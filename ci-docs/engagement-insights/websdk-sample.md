---
title: Εκτέλεση δείγματος SDK διαδικτύου
description: Μάθετε πώς να εξατομικεύσετε και να εκτελέσετε ένα δείγμα SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036603"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Εκτέλεση του δείγματος SDK web για τη δυνατότητα πληροφοριών δέσμευσης του Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Η βιβλιοθήκη SDK web της δυνατότητας πληροφοριών δέσμευσης είναι μια βιβλιοθήκη JavaScript με δείγμα κώδικα που μπορείτε να χρησιμοποιήσετε στην τοποθεσία Web σας.

## <a name="prerequisites"></a>Προϋποθέσεις

- Εγκατάσταση [Κώδικα Visual Studio](https://code.visualstudio.com/).
- [Εγκατάσταση της επέκτασης Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) σε Κώδικα Visual Studio και εξοικείωση με τον τρόπο εκτέλεσης του Live Server.
- Πρέπει να διαθέτετε το [κλειδί ενσωμάτωσης](instrument-website.md).

## <a name="run-sample"></a>Εκτέλεση δείγματος

1. [Πραγματοποιήστε λήψη του δείγματος SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Αποσυμπιέστε το συμπιεσμένο αρχείο `ei_websdk_sample.zip`.

1. Ανοίξτε τον αποσυμπιεσμένο φάκελο στον Κώδικα Visual Studio.

1. Στο αρχείο `ei_websdk_sample.html`, αντικαταστήστε το στοιχείο “INGESTION_KEY” με το κλειδί ενσωμάτωσής σας από την πύλη της δυνατότητας πληροφοριών δέσμευσης και τη συμβολοσειρά “NAME” με το καθολικό όνομα στο οποίο θέλετε να δημιουργηθεί η παρουσία του SDK. Βεβαιωθείτε ότι αντικαθιστάτε όλες τις εμφανίσεις.

1. Ανοίξτε το αρχείο `ei_websdk_sample.html` χρησιμοποιώντας το Live Server στον Κώδικα Visual Studio επιλέγοντας **Go Live** από τη γραμμή κατάστασης.

1. Κατά το άνοιγμα της σελίδας, θα πρέπει να αποσταλεί αυτόματα ένα συμβάν προβολής. Εάν κάνετε κλικ σε οποιοδήποτε από τα κουμπιά της σελίδας, θα σταλούν συμβάντα ενεργειών. Το κουμπί **Παρακολούθηση συμβάντων** θα στείλει επίσης προσαρμοσμένα συμβάντα. Εάν επιλέξετε το κουμπί **Μετάβαση στο Bing** θα σταλεί ένα συμβάν ενέργειας πριν την περιήγηση στην τοποθεσία Web του Bing.

1. Δείτε τη ροή συμβάντων κατά την περιήγηση στο χώρο εργασίας σας. Αυτός ο χώρος εργασίας συσχετίζεται με το κλειδί ενσωμάτωσης που καταχωρήθηκε στο Βήμα 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]