---
title: Εξαγωγή δεδομένων Customer Insights στο Azure Data Lake Storage Gen2
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477179"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Σύνδεση για Azure Data Lake Storage Gen2 (προεπισκόπηση)

Αποθηκεύστε τα δεδομένα του Customer Insights στο Azure Data Lake Storage Gen2 ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Ρύθμιση παραμέτρων του συνδέσμου για Azure Data Lake Storage Gen2

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στην περιοχή **Azure Data Lake Storage Gen2**, επιλέξτε **Set up**.

1. Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.

1. Καταχωρήστε τα **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Περιέκτης** για το δικό σας Azure Data Lake Storage Gen2.
    - Για να μάθετε πώς να δημιουργείτε ένα λογαριασμό χώρου αποθήκευσης για χρήση με το Azure Data Lake Storage Gen2, ανατρέξτε στο θέμα [Δημιουργία λογαριασμού χώρου αποθήκευσης](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Για να μάθετε περισσότερα σχετικά με τον τρόπο εύρεσης του ονόματος λογαριασμού αποθήκευσης Azure Data Lake Storage Gen2 και του κλειδιού λογαριασμού, ανατρέξτε στο θέμα [Διαχείριση ρυθμίσεων λογαριασμού χώρου αποθήκευσης στην πύλη Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.

1. Επιλέξτε **Αποθήκευση**.

## <a name="export-the-data"></a>Εξαγωγή δεδομένων

Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md#export-data-on-demand). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).
