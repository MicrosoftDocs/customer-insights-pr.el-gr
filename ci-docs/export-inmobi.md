---
title: Εξαγωγή δεδομένων Customer Insights στο InMobi
description: Μάθετε πώς να ρυθμίσετε τη σύνδεση και την εξαγωγή στο InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195888"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Εξαγωγή δεδομένων Customer Insights στο InMobi (προεπισκόπηση)

Εξαγάγετε λίστες τμημάτων ή άλλα δεδομένα από την παρουσία του Customer Insights στο [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [λογαριασμός InMobi](https://www.inmobi.com/) και διαπιστευτήρια διαχειριστή.
- Ένα όνομα [Λογαριασμού Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) και κλειδί λογαριασμού. Για να βρείτε το όνομα και το κλειδί, βλ [Διαχειριστείτε τις ρυθμίσεις λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).
- Ένα [Δοχείο αποθήκευσης Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) για εξαγωγή δεδομένων InMobi σε.
- Το InMobi θα δημιουργήσει μια άμεση σύνδεση στον χώρο αποθήκευσης αντικειμένων blob σας και θα ρυθμίσει τις παραμέτρους μιας αυτόματης εισαγωγής των δεδομένων σας στο InMobi. Επικοινωνήστε με τον αντιπρόσωπό σας στο InMobi για να ξεκινήσετε τη διαδικασία.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Για το Azure Blob Storage, επιλέξτε μεταξύ [Τυπική απόδοση και επίπεδο απόδοσης Premium](/azure/storage/blobs/storage-blob-performance-tiers). Εάν επιλέξετε το επίπεδο απόδοσης Premium, επιλέξτε τα [blob premium συνόλου ως τύπο λογαριασμού](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Ρυθμίστε τη σύνδεση στο Azure Blob Storage

[Ρυθμίστε μια σύνδεση με το Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[Διαμόρφωση εξαγωγής](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
