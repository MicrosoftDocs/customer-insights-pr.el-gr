---
title: Εξαγωγή δεδομένων σε χώρο αποθήκευσης αντικειμένων blob Azure (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους της σύνδεσης και της εξαγωγής σε χώρο αποθήκευσης blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195704"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Εξαγωγή δεδομένων σε χώρο αποθήκευσης αντικειμένων blob Azure (έκδοση προεπισκόπησης)

Αποθηκεύστε τα δεδομένα του Customer Insights σε έναν χώρο αποθήκευσης αντικειμένου blob ή χρησιμοποιήστε τα για να μεταφέρετε τα δεδομένα σας σε άλλες εφαρμογές.

## <a name="prerequisites"></a>Προϋποθέσεις

- Ένα όνομα [Λογαριασμού Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) και κλειδί λογαριασμού. Για να βρείτε το όνομα και το κλειδί, βλ [Διαχειριστείτε τις ρυθμίσεις λογαριασμού αποθήκευσης στην πύλη Azure](/azure/storage/common/storage-account-manage).
- Ένα [Κοντέινερ Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Για το Azure Blob Storage, επιλέξτε μεταξύ [Τυπική απόδοση και επίπεδο απόδοσης Premium](/azure/storage/blobs/storage-blob-performance-tiers). Εάν επιλέξετε το επίπεδο απόδοσης Premium, επιλέξτε τα [blob premium συνόλου ως τύπο λογαριασμού](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Ρυθμίστε τη σύνδεση στο Αποθήκευση Blob

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Επιλέξτε **Προσθήκη σύνδεσης** και επιλέξτε **Αποθήκευση Azure Blob**.

1. Δώστε στη σύνδεσή σας ένα αναγνωρίσιμο όνομα στο πεδίο **Εμφανιζόμενο όνομα**. Το όνομα και ο τύπος της σύνδεσης περιγράφουν αυην τη σύνδεση. Συνιστούμε να επιλέξετε ένα όνομα που να εξηγεί τον σκοπό και τον προορισμό της σύνδεσης.

1. Επιλέξτε κάποιον που μπορεί να χρησιμοποιήσει αυτήν τη σύνδεση. Ως προεπιλογή, είναι μόνο διαχειριστές. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Να επιτρέπεται στους συμβαλλόντων η χρήση σύνδεσης για εξαγωγές](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Εισαγάγετε το **Όνομα λογαριασμού**, **Κλειδί λογαριασμού** και **Κοντέινερ** για τον λογαριασμό του χώρου αποθήκευσης αντικειμένων Blob.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη σύνδεση.

## <a name="configure-an-export"></a>Ρύθμιση παραμέτρων εξαγωγής

Για να ρυθμίσετε αυτήν την εξαγωγή, πρέπει να έχετε [άδεια](export-destinations.md#set-up-a-new-export) για αυτόν τον τύπο σύνδεσης.

> [!IMPORTANT]
> Αν ενεργοποιήσατε το [ρύθμιση διαγραφής μέσω λογισμικού](/azure/storage/blobs/soft-delete-blob-enable) για τον λογαριασμό Azure Blob Storage, οι εξαγωγές θα αποτύχουν. Απενεργοποιήστε τη διαγραφή για να εξαγάγετε δεδομένα στα blob.

1. Μεταβείτε στα **Δεδομένα** > **Εξαγωγές**.

1. Επιλέξτε **Προσθήκη εξαγωγής**.

1. Στο πεδίο **Σύνδεση για εξαγωγή**, επιλέξτε μια σύνδεση από την ενότητα χώρος αποθήκευσης αντικειμένων blob Azure. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Εισαγάγετε ένα όνομα για την εξαγωγή.

1. Εισαγάγετε το όνομα του φακέλου για το χώρο αποθήκευσης Blob.

1. Επιλέξτε το πλαίσιο δίπλα σε κάθε μία από τις οντότητες που θέλετε να εξαγάγετε σε αυτόν τον προορισμό.

1. Επιλέξτε **Αποθήκευση**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Τα δεδομένα που έχουν εξαχθεί αποθηκεύονται στο κοντέινερ του χώρου αποθήκευσης αντικειμένων Blob που διαμορφώσατε. Οι παρακάτω διαδρομές φακέλων δημιουργούνται αυτόματα στο κοντέινερ που διαθέτετε:

- Για τις οντότητες προέλευσης και τις οντότητες που δημιουργούνται από το σύστημα:  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Η εξαγωγή οντοτήτων που περιέχουν μεγάλη ποσότητα δεδομένων μπορεί να οδηγήσει σε πολλά αρχεία CSV στον ίδιο φάκελο για κάθε εξαγωγή. Ο διαχωρισμός των εξαγωγής συμβαίνει για λόγους επιδόσεων ώστε να ελαχιστοποιηθεί ο χρόνος που απαιτείται για την ολοκλήρωση μιας εξαγωγής.

- Το model.json για τις εξαγόμενες οντότητες βρίσκεται στο επίπεδο *%ExportDestinationName%*.  
  
  Παράδειγμα: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
