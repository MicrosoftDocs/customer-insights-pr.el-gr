---
title: Εξαγωγή δεδομένων Customer Insights στο Dynamics 365 Sales
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με το Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643818"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Σύνδεσμος για το Dynamics 365 Sales (προεπισκόπηση)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Χρησιμοποιήστε τα δεδομένα πελατών σας για να δημιουργήσετε λίστες μάρκετινγκ, ροές εργασιών παρακολούθησης και να στείλετε προσφορές με το Dynamics 365 Sales.

## <a name="prerequisite"></a>Προαπαιτούμενα στοιχεία

Καρτέλες επαφών [από το Dynamics 365 Sales που λαμβάνονται με χρήση του Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Ρύθμιση παραμέτρων του συνδέσμου για το Sales

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στην περιοχή **Dynamics 365 Sales**, επιλέξτε **Ρύθμιση παραμέτρων**.

1. Δώστε στον προορισμό εξαγωγής σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.

1. Καταγράψτε τη διεύθυνση URL του οργανισμού Sales σας στο πεδίο **Αποθήκευση διεύθυνσης**.

1. Στην ενότητα **Λογαριασμός διαχειριστή διακομιστή**, επιλέξτε **Σύνδεση** και επιλέξτε ένα λογαριασμό Dynamics 365 Sales.

1. Αντιστοιχίστε ένα πεδίο αναγνωριστικού πελάτη με το αναγνωριστικό επαφής Dynamics 365.

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε ένα ή περισσότερα τμήματα.

1. Επιλέξτε **Αποθήκευση**.

## <a name="export-the-data"></a>Εξαγωγή δεδομένων

Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).
