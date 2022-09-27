---
title: Εξαγωγή τμημάτων στο Dynamics 365 Sales (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195981"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Εξαγωγή τμημάτων στο Dynamics 365 Sales (έκδοση προεπισκόπησης)

Χρησιμοποιήστε τα δεδομένα πελατών σας για να δημιουργήσετε λίστες μάρκετινγκ, ροές εργασιών παρακολούθησης και να στείλετε προσφορές με το Dynamics 365 Sales.

## <a name="prerequisites"></a>Προϋποθέσεις

Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Sales για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στις Πωλήσεις. Μάθετε περισσότερα για το πώς μπορείτε να χρησιμοποιήσετε τις επαφές που προέρχονται από το [Dynamics 365 Sales χρησιμοποιώντας το Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Η εξαγωγή τμημάτων της αγοράς από το Customer Insights στις Πωλήσεις δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες Πωλήσεων. Οι καρτέλες επαφών από τις Πωλήσεις πρέπει να συγκεντρωθούν στο Customer Insights και να χρησιμοποιηθούν ως προέλευση δεδομένων. Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

Οι εξαγωγές στο Dynamics 365 Sales περιορίζονται σε 100.000 ανά τμήμα, οι οποίες μπορεί να διαρκέσουν έως και 3 ώρες για να ολοκληρωθούν.

## <a name="set-up-connection-to-sales"></a>Ρυθμίστε τη σύνδεση με το Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Dynamics 365 Sales**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Καταγράψτε τη διεύθυνση URL του οργανισμού Sales σας στο πεδίο **Αποθήκευση διεύθυνσης**.

1. Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Sales.

1. Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Dynamics 365 Sales. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Επιλέξτε το πεδίο Αναγνωριστικό επαφής στην οντότητα πελάτη που αντιστοιχεί στο Αναγνωριστικό επαφής Dynamics 365.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.

1. `Επιλέξτε **Αποθήκευση**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]