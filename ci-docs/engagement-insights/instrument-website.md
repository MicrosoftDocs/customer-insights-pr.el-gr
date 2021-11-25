---
title: Προσθήκη κώδικα στην τοποθεσία web σας
description: Πώς να προσθέσετε ένα τμήμα κώδικα για την καταγραφή συμβάντων Dynamics 365 Customer Insights στην τοποθεσία Web σας.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558857"
---
# <a name="install-the-web-sdk-on-a-website"></a>Εγκατάσταση του SDK web σε μια τοποθεσία Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Αυτό το άρθρο περιγράφει πώς ένας διαχειριστής εγκαθιστά το κιτ εργαλείων ανάπτυξης λογισμικού Web (SDK) σε μια τοποθεσία Web. Θα αρχίσετε να βλέπετε συμβάντα στο χώρο εργασίας σας λίγο αφού κάνετε κλικ στην τοποθεσία Web σας. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Διαχείριση χώρων εργασίας και περιβάλλοντος](manage-environments-workspaces.md). Για να αποτυπώσετε συμβάντα σε εφαρμογές για κινητές συσκευές, ανατρέξτε στην [Επισκόπηση πόρων για προγραμματιστές](developer-resources.md).


### <a name="prerequisites"></a>Προϋποθέσεις

* Πρέπει να έχετε δικαιώματα διαχειριστής για την αποθήκευση δεδομένων στον χώρο εργασίας.
* Η τοποθεσία Web ή το έργο σας πρέπει να φιλοξενούνται ηλεκτρονικά για την αποστολή δεδομένων δραστηριότητας. Τα δεδομένα που αποστέλλονται από τοπικό αρχείο δεν γίνται αποδεκτά από τον διακομιστή.


## <a name="add-web-sdk-to-your-website"></a>Προσθήκη SDK web στην τοποθεσία web σας

Μεταβείτε στην περιοχή **Διαχειριστής** > **Χώρος εργασίας** και, στη συνέχεια, επιλέξτε **Οδηγός εγκατάστασης**. Υπάρχουν δύο επιλογές για εγκατάσταση του SDK web. Ο πρώτος είναι να χρησιμοποιήσετε μια σύνδεση λήψης και ο δεύτερος είναι να εγκαταστήσετε ένα πακέτο διαχείρισης πακέτων κόμβων (NPM).

### <a name="option-1-using-the-download-link"></a>Επιλογή 1: Χρήση της σύνδεσης λήψης

1. Επιλέξτε **Αντιγραφή κώδικα** για να αντιγράψετε το τμήμα κώδικα. Ως προεπιλογή, το κλειδί ενσωμάτωσης για τον χώρο εργασίας σας είναι ενσωματωμένο στο τμήμα κώδικα.
  :::image type="content" source="media/copy-code.png" alt-text="Στιγμιότυπο οθόνης της σελίδας τμήματος κώδικα.":::

1. Προσθήκη του αντιγραμμένου κώδικα στην τοποθεσία Web σας, κοντά στο <head> ετικέτα και πριν από οποιαδήποτε άλλη δέσμη ενεργειών ή ετικέτα CSS.
1. Δημοσιεύστε την ενημερωμένη τοποθεσία Web και περιμένετε μερικά λεπτά για να αποτυπώσετε την εισερχόμενη κυκλοφορία στο Web.
1. Για να δείτε τα δεδομένα σας, επιλέξτε τον χώρο εργασίας σας από την εναλλαγή χώρου εργασίας στο τμήμα παραθύρου περιήγησης. Στη συνέχεια, επιλέξτε μία από τις αναφορές στην ενότητα **Εξερεύνηση**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Επιλογή 2: Χρήση του πακέτου NPM (συνιστάται για εφαρμογές web βασισμένες σε JavaScript)

1. Μεταβείτε στην [ιστοσελίδα μας NPM](https://www.npmjs.com/package/engagementinsights-web) και ακολουθήστε τις οδηγίες για την εγκατάσταση και ρύθμιση του πακέτου SDK NPM web.
1. Δημοσιεύστε την ενημερωμένη τοποθεσία Web και περιμένετε μερικά λεπτά για να αποτυπώσετε την εισερχόμενη κυκλοφορία στο Web.
1. Για να δείτε τα δεδομένα σας, επιλέξτε τον χώρο εργασίας σας από την εναλλαγή χώρου εργασίας στο τμήμα παραθύρου περιήγησης. Στη συνέχεια, επιλέξτε μία από τις αναφορές στην ενότητα **Εξερεύνηση**.

## <a name="configuration-options"></a>Επιλογές ρύθμισης παραμέτρων

Μπορείτε να αλλάξετε τις παρακάτω επιλογές ρύθμισης παραμέτρων στο τμήμα κώδικα:

- **ingestionKey**: Το κλειδί ενσωμάτωσης που θα χρησιμοποιηθεί για την αποστολή συμβάντων στον χώρο εργασίας. Μπορείτε να αλλάξετε το κλειδί πρόσληψης για την αποστολή συμβάντων σε διαφορετικό χώρο εργασίας. Ένα κλειδί πρόσληψης είναι μοναδικό για κάθε χώρο εργασίας.
- **autoCapture**: Καθορίζει εάν καταγράφονται οι προβολές σελίδας και οι αλληλεπιδράσεις με την τοποθεσία Web. Διαθέτει δύο επιλογές:
    - **view**: Ρυθμίστε σε *true* για την αποτύπωση των προβολών σελίδας. Οι προβολές σελίδας καταγράφονται ως *Προβολή* [συμβάντα](glossary.md#event) ένας τύπος [συμβάντος βάσης](glossary.md#base-event).
    - **click**: Ορίστε την τιμή *true* για την αποτύπωση των αλληλεπιδράσεων των επισκεπτών στην τοποθεσία Web. Οι αλληλεπιδράσεις καταγράφονται ως *Ενέργεια* [συμβάντα](glossary.md#event) ένας τύπος [συμβάντος βάσης](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]