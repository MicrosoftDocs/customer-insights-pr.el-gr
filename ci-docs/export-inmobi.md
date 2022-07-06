---
title: Εξαγωγή δεδομένων Customer Insights στο InMobi
description: Μάθετε πώς να ρυθμίσετε τη σύνδεση και την εξαγωγή στο InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056542"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Εξαγωγή λίστας τμήματος αγοράς και άλλων δεδομένων στο InMobi (έκδοση προεπισκόπησης)

Εξαγάγετε λίστες τμημάτων ή άλλα δεδομένα από την παρουσία του Customer Insights στο [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Προϋποθέσεις

1. Έχετε [λογαριασμό InMobi](https://www.inmobi.com/) και διαπιστευτήρια διαχειριστή.
1. Έχετε ένα όνομα λογαριασμού χώρου αποθήκευσης αντικειμένων blob Azure και το αντίστοιχο κλειδί λογαριασμού. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Διαχείριση των ρυθμίσεων λογαριασμών χώρου αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage). Υπάρχει ένα κοντέινερ στον λογαριασμό αποθήκευσης στον οποίο θα γίνει εξαγωγή των δεδομένων του inMobi. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία κοντέινερ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. Το InMobi θα δημιουργήσει μια άμεση σύνδεση στον χώρο αποθήκευσης αντικειμένων blob σας και θα ρυθμίσει τις παραμέτρους μιας αυτόματης εισαγωγής των δεδομένων σας στο InMobi. Επικοινωνήστε με τον αντιπρόσωπό σας στο InMobi για να ξεκινήσετε τη διαδικασία.

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

1. Για τον Χώρο αποθήκευσης Azure Blob μπορείτε να επιλέξετε μεταξύ [Βασικής απόδοσης και απόδοσης επιπέδου Premium](/azure/storage/blobs/storage-blob-performance-tiers). Εάν επιλέξετε το επίπεδο απόδοσης Premium, επιλέξτε τα [blob premium συνόλου ως τύπο λογαριασμού](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Ρύθμιση της σύνδεσης στον χώρο αποθήκευσης αντικειμένων blob Azure και ρύθμιση παραμέτρων μιας εξαγωγής

1. Ακολουθήστε τις οδηγίες για να [ρυθμίσετε μια σύνδεση στον χώρο αποθήκευσης Azure Blob.](export-azure-blob-storage.md)
2. Ακολουθήστε τις οδηγίες για να [ρυθμίσετε τις παραμέτρους μιας εξαγωγής](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
