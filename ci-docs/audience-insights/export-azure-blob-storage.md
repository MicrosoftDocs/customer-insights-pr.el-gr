---
title: Εξαγωγή δεδομένων Customer Insights σε ένα χώρο αποθήκευσης αντικειμένων BLOB Azure
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης με τον χώρο αποθήκευσης αντικειμένων blob Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667139"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Σύνδεση για χώρο αποθήκευσης αντικειμένων blob Azure (προεπισκόπηση)

Αποθηκεύστε τα δεδομένα του Customer Insights στον χώρο αποθήκευσης αντικειμένου blob Azure ή χρησιμοποιήστε το για τη μεταφορά των δεδομένων σας σε άλλες εφαρμογές.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Ρύθμιση σύνδεσης για χώρο αποθήκευσης αντικειμένων blob Azure

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στην περιοχή **Χώρος αποθήκευσης Azure Blob**, επιλέξτε **Ρύθμιση**.

1. Εισάγετε το **Όνομα λογαριασμού**, το **Κλειδί λογαριασμού** και το **Κοντέινερ** για το λογαριασμό χώρου αποθήκευσης Azure Blob.
    - Για να μάθετε περισσότερα σχετικά με το πώς μπορείτε να βρείτε το όνομα του λογαριασμού αποθήκευσηςAzure Blob και το κλειδί λογαριασμού, δείτε [Διαχείριση ρυθμίσεων λογαριασμού αποθήκευσης στην πύλη Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Για να μάθετε πώς να δημιουργείτε ένα κοντέινερ, δείτε [Δημιουργία κοντέινερ](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Δώστε στον προορισμό σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**.

1. Επιλέξτε **Επόμενο**.

1. Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.

1. Επιλέξτε **Αποθήκευση**.

Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ χώρου αποθήκευσης αντικειμένων blob Azure που ρυθμίσατε. Οι παρακάτω διαδρομές φακέλων δημιουργούνται αυτόματα στο κοντέινερ που διαθέτετε:

- Για τις οντότητες προέλευσης και τις οντότητες που δημιουργούνται από το σύστημα: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Παράδειγμα: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Το model.json για τις οντότητες που έχουν εξαχθεί θα βρίσκεται στο επίπεδο %ExportDestinationName%
  - Παράδειγμα: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Εξαγωγή δεδομένων

Μπορείτε να [εξαγάγετε δεδομένα κατόπιν απαίτησης](/export-destinations.md#export-data-on-demand). Η εξαγωγή θα εκτελεστεί επίσης με κάθε [προγραμματισμένη ανανέωση](system.md#schedule-tab).
