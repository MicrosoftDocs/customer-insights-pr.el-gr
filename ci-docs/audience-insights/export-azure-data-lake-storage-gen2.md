---
title: Εξαγωγή δεδομένων Customer Insights στο Azure Data Lake Storage Gen2
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596637"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Σύνδεση για Azure Data Lake Storage Gen2 (προεπισκόπηση)

Αποθηκεύστε τα δεδομένα του Customer Insights στο Azure Data Lake Storage Gen2 ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Ρύθμιση παραμέτρων του συνδέσμου για Azure Data Lake Storage Gen2

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στην περιοχή **Azure Data Lake Storage Gen2**, επιλέξτε **Set up**.

1. Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.

1. Καταχωρήστε τα **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Περιέκτης** για το δικό σας Azure Data Lake Storage Gen2.
    - Για να μάθετε πώς να δημιουργείτε ένα λογαριασμό χώρου αποθήκευσης για χρήση με το Azure Data Lake Storage Gen2, ανατρέξτε στο θέμα [Δημιουργία λογαριασμού χώρου αποθήκευσης](/azure/storage/blobs/create-data-lake-storage-account). 
    - Για να μάθετε περισσότερα σχετικά με τον τρόπο εύρεσης του ονόματος λογαριασμού αποθήκευσης Azure Data Lake Storage Gen2 και του κλειδιού λογαριασμού, ανατρέξτε στο θέμα [Διαχείριση ρυθμίσεων λογαριασμού χώρου αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.

1. Επιλέξτε **Αποθήκευση**.

## <a name="export-the-data"></a>Εξαγωγή δεδομένων

Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](export-destinations.md#export-data-on-demand). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).