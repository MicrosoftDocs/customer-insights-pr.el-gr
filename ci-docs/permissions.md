---
title: Ανάθεση δικαιωμάτων χρήστη
description: Μάθετε σχετικά με τα δικαιώματα και τους ρόλους χρήστη.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245419"
---
# <a name="assign-user-permissions"></a>Ανάθεση δικαιωμάτων χρήστη

Η πρόσβαση στο Customer Insights περιορίζεται σε χρήστες του οργανισμού σας που προστέθηκαν στην εφαρμογή από έναν διαχειριστή. Ένας διαχειριστής μπορεί να προσθέσει, να επεξεργαστεί ή να καταργήσει χρήστες. Ένας χρήστης μπορεί να είναι μεμονωμένος χρήστης, ομάδα ή εφαρμογή. Υπάρχουν τρεις τύποι ρόλων που μπορεί να έχει ένας χρήστης:

## <a name="viewer"></a>Θεατής

- Εξερευνήστε τις ιδέες και τα τμήματα εντός των σελίδων **Αρχική** και **Τμήματα**.
- Αναζητήστε και φιλτράρετε τα προφίλ πελατών χρησιμοποιώντας τη σελίδα **Πελάτες**. Τα πεδία πρέπει να είναι αναζητήσιμα.
- Δείτε και εξερευνήστε τη σελίδα **Εμπλουτισμός**.
- Εξερευνήστε και εξαγάγετε οντότητες που χρησιμοποιούν τη σελίδα **Οντότητες**.
- Προβάλετε την κατάσταση των διεργασιών συστήματος χρησιμοποιώντας τη σελίδα **Σύστημα**.
- Προβολή εξαγωγής στη σελίδα **Εξαγωγές**.
- Εγκαταστήστε και χρησιμοποιήστε τον πίνακα εργαλείων **Power BI Customer Insights**.

## <a name="contributor"></a>Συμβάλλων

- Όλα τα δικαιώματα που είναι διαθέσιμα στο Θεατή.
- Φορτώστε και μεταμορφώστε δεδομένα χρησιμοποιώντας τη σελίδα **Προελεύσεις δεδομένων**.
- Ολοκληρώστε την **Ενοποίηση δεδομένων** που θα έχει ως αποτέλεσμα την οντότητα ενοποιημένου προφίλ πελάτη.
- Ορίστε **Σχέσεις** και **Δραστηριότητες**.
- Δημιουργήστε τμήματα χρησιμοποιώντας τη σελίδα **Τμήματα**.
- Δημιουργήστε μετρήσεις χρησιμοποιώντας τη σελίδα **Μετρήσεις**.
- Διαχειριστείτε τη ρύθμιση παραμέτρων και εμπλουτίστε τα προφίλ πελατών από τη σελίδα **Εμπλουτισμός** (μόνο για εμπλουτισμούς πρώτων μερών).
- Διαχειριστείτε και δημιουργήστε εξαγωγές με βάση [συνδέσεις που είναι κοινόχρηστες με συμβάλλοντες](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Διαχείριση

- Όλα τα δικαιώματα που είναι διαθέσιμα στο Συμβάλλοντα.
- Αλλάξτε τις ρυθμίσεις στη σελίδα **Σύστημα** συμπεριλαμβανομένης της γλώσσας εργασίας, ανανεώστε χρονοδιαγράμματα για τις διεργασίες του συστήματός σας και εξαγάγετε αρχεία καταγραφής διαγνωστικών.
- Αλλάξτε ρυθμίσεις στη σελίδα **Ασφάλεια**, συμπεριλαμβανομένων χρηστών, κλειδιών API, ιδιωτικών συνδέσεων και Key Vault.
- Δημιουργήστε ορισμούς Αναζήτησης και Φίλτρων για τη σελίδα Πελάτες χρησιμοποιώντας τη σελίδα **Ευρετήριο αναζήτησης και φιλτραρίσματος** (προσβάσιμη μέσω της σελίδας **Πελάτες**).
- Διαχειριστείτε τις συνδέσεις και επιτρέψτε τους άλλους ρόλους χρηστών στη σελίδα **Συνδέσεις**.
- Διαχειριστείτε τη ρύθμιση παραμέτρων και εμπλουτίστε τα προφίλ πελατών από τη σελίδα **Εμπλουτισμός** (για όλους τους εμπλουτισμούς).
- Διαχείριση και δημιουργία εξαγωγών στη σελίδα **Εξαγωγές**.
- Εγκαταστήσετε και χρησιμοποιήστε το **Πρόσθετο κάρτας πελάτη**.
- Προσθέστε και χρησιμοποιήστε τη **Σύνδεση Power Apps**.
- Ενεργοποίηση χρήσης [API Customer Insights](apis.md).
- [Ανάθεση κυριότητας περιβάλλοντος](manage-environments.md#change-the-owner-of-an-environment) σε άλλο διαχειριστή.

## <a name="admin-owner"></a>Διαχειριστής (κάτοχος)

- Όλα τα δικαιώματα που είναι διαθέσιμα στο διαχειριστή.
- [Επαναφορά και διαγραφή](manage-environments.md#reset-an-existing-environment-preview) του περιβάλλοντος.

## <a name="add-users"></a>Προσθήκη χρηστών

1. Μεταβείτε στα στοιχεία **Διαχειριστής** > **Ασφάλεια** και επιλέξτε την καρτέλα **Χρήστες**.

1. Επιλέξτε **Προσθήκη χρηστών** για να ανοίξετε το τμήμα παραθύρου **Προσθήκη/επεξεργασία δικαιωμάτων**.

1. Χρησιμοποιήστε το πεδίο **Αναζήτηση** για να βρείτε τον χρήστη ή την ομάδα του Azure Active Directory που θέλετε να προσθέσετε. Επιλέξτε **Ρόλο** που θα αναθέσετε σε αυτόν τον χρήστη ή την ομάδα.

1. Επιλέξτε **Αποθήκευση**. Το τρέχον περιβάλλον θα μοιράζεται αυτόματα με τον χρήστη ή τα μέλη της ομάδας των οποίων τα δικαιώματα έχετε αλλάξει. Οι χρήστες μπορούν να έχουν πρόσβαση στην εφαρμογή Customer Insights και να εργάζονται σύμφωνα με τον καθορισμένο ρόλο τους.

## <a name="view-current-permissions"></a>Προβολή τρεχόντων δικαιωμάτων

Μεταβείτε στη **Διαχείριση** > **Ασφάλεια** και επιλέξτε την καρτέλα **Χρήστες** για να προβάλετε τη λίστα των ενεργών χρηστών και τις αναθέσεις ρόλων τους. Μπορείτε να ταξινομήσετε τη λίστα χρηστών με οποιαδήποτε στήλη ή να χρησιμοποιήσετε το πλαίσιο αναζήτησης για να βρείτε έναν συγκεκριμένο χρήστη.

## <a name="manage-current-users"></a>Διαχείριση υφιστάμενων χρηστών

Μεταβείτε στη **Διαχείριση** > **Ασφάλεια** και επιλέξτε την καρτέλα **Χρήστες**. Μπορείτε να ταξινομήσετε τη λίστα των χρηστών με οποιαδήποτε στήλη ή να χρησιμοποιήσετε το πλαίσιο αναζήτησης για να βρείτε τον χρήστη που θέλετε να διαχειριστείτε.

Επιλέξτε έναν χρήστη για προβολή των διαθέσιμων ενεργειών.

- Επιλέξτε **Επεξεργασία** για επεξεργασία του ρόλου του χρήστη στο Customer Insights. Επιλέξτε **Αποθήκευση** για να επιβεβαιώσετε την αλλαγή.
- Επιλέξτε **Κατάργηση** για να καταργήσετε τον χρήστη από το να έχει πρόσβαση στο Customer Insights. Επιλέξτε **Διαγραφή**, για να επιβεβαιώσετε τη διαγραφή.

[!INCLUDE [footer-include](includes/footer-banner.md)]