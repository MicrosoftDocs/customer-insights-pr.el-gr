---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Marketing
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597603"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Σύνδεσμος για το Dynamics 365 Marketing (προεπισκόπηση)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Χρησιμοποιήστε τα [τμήματα](segments.md) για τη δημιουργία εκστρατειών και την επικοινωνία με συγκεκριμένες ομάδες πελατών με το Dynamics 365 Marketing. Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Χρήση τμημάτων από το Dynamics 365 Customer Insights με το Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Προαπαιτούμενα στοιχεία

- Οι καρτέλες επαφών πρέπει να υπάρχουν στο Dynamics 365 Marketing για να μπορείτε να εξαγάγετε ένα τμήμα από το Customer Insights στο Marketing. Διαβάστε περισσότερα σχετικά με το πώς μπορείτε να ενσωματώσετε τις επαφές στο [Dynamics 365 Marketing χρησιμοποιώντας το Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Η εξαγωγή τμημάτων από τις πληροφορίες κοινού στο Marketing δεν θα δημιουργήσει νέες καρτέλες επαφών στις παρουσίες του Marketing. Οι καρτέλες επαφών από το Marketing πρέπει να ενοποιηθούν με τις πληροφορίες κοινού και να χρησιμοποιούνται ως προέλευση δεδομένων. Πρέπει επίσης να συμπεριληφθούν στην ενοποιημένη οντότητα πελάτη για να αντιστοιχίσετε τα αναγνωριστικά των πελατών σε αναγνωριστικά επαφών πριν είναι δυνατή η εξαγωγή τμημάτων.

## <a name="configure-the-connector-for-marketing"></a>Ρύθμιση παραμέτρων του συνδέσμου για το Marketing

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στην περιοχή **Dynamics 365 Marketing**, επιλέξτε **Ρύθμιση παραμέτρων**.

1. Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.

1. Καταγράψτε τη διεύθυνση URL του Marketing στο πεδίο **Αποθήκευση διεύθυνσης**.

1. Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Marketing.

1. Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε ένα ή περισσότερα τμήματα.

1. Επιλέξτε **Αποθήκευση**.

## <a name="export-the-data"></a>Εξαγωγή δεδομένων

Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]