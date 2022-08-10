---
title: Εξαγωγή τμημάτων στο Dynamics 365 Marketing (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής στο Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196624"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Εξαγωγή τμημάτων στο Dynamics 365 Marketing (έκδοση προεπισκόπησης)

Χρησιμοποιήστε [τμήματα](segments.md) για να δημιουργήσετε καμπάνιες και να επικοινωνήσετε με συγκεκριμένες ομάδες πελατών [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Εάν χρησιμοποιείτε τις νέες δυνατότητες του Dynamics 365 Marketing για ενορχήστρωση διαδρομής πελάτη σε πραγματικό σε έναν οργανισμό Dataverse, δεν χρειάζεται να δημιουργήσετε μια τυπική εξαγωγή στο Dynamics 365 Marketing. Οι επαφές και τα τμήματα από το Customer Insights είναι διαθέσιμα απευθείας στο Dynamics 365 Marketing μετά τη σύνδεση του Μάρκετινγκ και του Customer Insights. Πριν διαγράψετε τις υπάρχουσες εξαγωγές, [εξετάστε την τεκμηρίωση σχετικά με τον τρόπο σύνδεσης του Customer Insights και της ενορχήστρωσης διαδρομής πελάτη Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Προαπαιτούμενα στοιχεία

Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Marketing για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στο Marketing. Διαβάστε περισσότερα σχετικά με το πώς μπορείτε να ενσωματώσετε τις επαφές στο [Dynamics 365 Marketing χρησιμοποιώντας το Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Η εξαγωγή τμημάτων της αγοράς από το Customer Insights στο Μάρκετινγκ δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες Μάρκετινγκ. Οι καρτέλες επαφών από το Μάρκετινγκ πρέπει να συγκεντρωθούν στο Customer Insights και να χρησιμοποιηθούν ως προέλευση δεδομένων. Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.

## <a name="set-up-connection-to-marketing"></a>Ρύθμιση σύνδεσης στο Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Dynamics 365 Marketing**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Καταγράψτε τη διεύθυνση URL του Marketing στο πεδίο **Αποθήκευση διεύθυνσης**.

1. Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Marketing.

1. Αντιστοιχστε το πεδίο "Αναγνωριστικό επαφής" στην οντότητα "Πελάτης" με το αναγνωριστικό επαφής του Dynamics 365.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Dynamics 365 Marketing. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Επιλέξτε το πεδίο Αναγνωριστικό επαφής στην οντότητα πελάτη που αντιστοιχεί στο Αναγνωριστικό επαφής Dynamics 365.

1. Επιλέξτε τα τμήματα που θέλετε να εξαγάγετε.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
