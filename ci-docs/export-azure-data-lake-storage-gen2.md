---
title: Εξαγωγή δεδομένων στο Azure Data Lake Storage Gen2 (έκδοση προεπισκόπησης)
description: Μάθετε πώς μπορείτε να ρυθμίσετε τις παραμέτρους της σύνδεσης στο Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196440"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Εξαγωγή δεδομένων στο Azure Data Lake Storage Gen2 (έκδοση προεπισκόπησης)

Αποθηκεύστε τα δεδομένα του Customer Insights σε λογαριασμό Azure Data Lake Storage Gen2 ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένας [λογαριασμός αποθήκευσης για χρήση με το Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Για να βρείτε το όνομα και το κλειδί του λογαριασμού αποθήκευσης, βλ [Διαχειριστείτε τις ρυθμίσεις λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).
- Ένα [Κοντέινερ Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Για Azure Data Lake Storage Gen2, επιλέξτε μεταξύ [Τυπική απόδοση και επίπεδο απόδοσης Premium](/azure/storage/blobs/create-data-lake-storage-account). Εάν επιλέξετε το επίπεδο απόδοσης Premium, επιλέξτε τα [blob premium συνόλου ως τύπο λογαριασμού](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Ρύθμιση σύνδεσης σε Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Azure Data Lake Gen 2**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Καταχωρήστε τα **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Περιέκτης** για το δικό σας Azure Data Lake Storage Gen2.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα Azure Data Lake. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Εισαγάγετε το όνομα φακέλου για το αποθήκευση Azure Data Lake Storage Gen2.

1. Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ χώρου αποθήκευσης Azure Data Lake Gen 2 που ρυθμίσατε.

> [!TIP]
> Η εξαγωγή οντοτήτων που περιέχουν μεγάλη ποσότητα δεδομένων μπορεί να οδηγήσει σε πολλά αρχεία CSV στον ίδιο φάκελο για κάθε εξαγωγή. Ο διαχωρισμός των εξαγωγής συμβαίνει για λόγους επιδόσεων ώστε να ελαχιστοποιηθεί ο χρόνος που απαιτείται για την ολοκλήρωση μιας εξαγωγής.

[!INCLUDE [footer-include](includes/footer-banner.md)]
