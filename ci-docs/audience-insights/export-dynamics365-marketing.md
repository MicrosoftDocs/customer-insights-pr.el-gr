---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Marketing
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643773"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Σύνδεσμος για το Dynamics 365 Marketing (προεπισκόπηση)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Χρησιμοποιήστε τα [τμήματα](segments.md) για τη δημιουργία εκστρατειών και την επικοινωνία με συγκεκριμένες ομάδες πελατών με το Dynamics 365 Marketing. Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Χρήση τμημάτων από το Dynamics 365 Customer Insights με το Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Προαπαιτούμενα στοιχεία

Καρτέλες επαφών [από το Dynamics 365 Marketing που λαμβάνονται με χρήση του Common Data Service](connect-power-query.md).

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
