---
title: Εμπλουτισμός προφίλ πελατών με προσαρμοσμένη εισαγωγή SFTP (έκδοση προεπισκόπησης)
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό προσαρμοσμένων εισαγωγών SFTP.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237766"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Εμπλουτισμός προφίλ πελατών με προσαρμοσμένη εισαγωγή SFTP (έκδοση προεπισκόπησης)

Η προσαρμοσμένη εισαγωγή πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP) σάς δίνει τη δυνατότητα να εισαγάγετε δεδομένα τα οποία δεν χρειάζεται να περάσουν από τη διεργασία ενοποίησης δεδομένων. Πρόκειται για έναν ευέλικτο, ασφαλή και εύκολο τρόπο για να μεταφέρετε τα δεδομένα σας. Η προσαρμοσμένη εισαγωγή SFTP μπορεί να χρησιμοποιηθεί σε συνδυασμό με την [εξαγωγή SFTP](export-sftp.md) που σας δίνει τη δυνατότητα να εξαγάγετε τα δεδομένα προφίλ πελατών που απαιτούνται για τον εμπλουτισμό. Στη συνέχεια, είναι δυνατό να γίνει επεξεργασία και εμπλουτισμός των δεδομένων και η προσαρμοσμένη εισαγωγή SFTP μπορεί να χρησιμοποιηθεί για την επιστροφή των εμπλουτισμένων δεδομένων στο Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Προϋποθέσεις

- Το όνομα αρχείου και η θέση (διαδρομή) του αρχείου που θα εισαχθεί στον κεντρικό υπολογιστή SFTP είναι γνωστά.

- Είναι διαθέσιμο ένα αρχείο *model.json* που καθορίζει το σχήμα του Common Data Model για τα δεδομένα που θα εισαχθούν. Αυτό το αρχείο πρέπει να βρίσκεται στον ίδιο κατάλογο με το αρχείο προς εισαγωγή.

- Μια [σύνδεση](connections.md) SFTP έχει [ρυθμιστεί ](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Παράδειγμα σχήματος αρχείου

Ο κατάλογος που περιέχει το αρχείο που πρόκειται να εισαχθεί στον διακομιστή SFTP πρέπει επίσης να περιέχει ένα αρχείο *model.json*. Αυτό το αρχείο καθορίζει το σχήμα που θα χρησιμοποιηθεί για την εισαγωγή των δεδομένων. Το σχήμα πρέπει να χρησιμοποιήσει το [Κοινό μοντέλο δεδομένων](/common-data-model/) για να καθορίσει την αντιστοίχιση των πεδίων. Ένα απλό παράδειγμα ενός αρχείου model.json μοιάζει με αυτό:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>Ρύθμιση παραμέτρων της σύνδεσης για προσαρμοσμένη εισαγωγή SFTP

Θα πρέπει να είστε [Διαχειριστής](permissions.md#admin) στο Customer Insights και να έχετε τα διαπιστευτήρια, τη διεύθυνση URL και τον αριθμό θύρας χρήστη για τη θέση SFTP από την οποία θέλετε να εισαγάγετε δεδομένα.

1. Επιλέξτε **Προσθήκη σύνδεσης** κατά τη ρύθμιση παραμέτρων ενός εμπλουτισμού ή μεταβείτε στο **Διαχειριστής** > **Συνδέσεις** και επιλέξτε **Ρύθμιση** στο πλακίδιο προσαρμοσμένης εισαγωγής.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Σελίδα ρύθμισης παραμέτρων σύνδεσης για Προσαρμοσμένη εισαγωγή.":::

1. Πληκτρολογήστε ένα όνομα για τη σύνδεση.

1. Εισαγάγετε ένα έγκυρο όνομα χρήστη, κωδικό πρόσβασης και διεύθυνση URL κεντρικού υπολογιστή για τοn διακομιστή SFTP στον οποίο βρίσκονται τα δεδομένα προς εισαγωγή.

1. Εξετάστε το [απόρρητο και συμμόρφωση δεδομένων](connections.md#data-privacy-and-compliance) και επιλέξτε **συμφωνώ**.

1. Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων και, στη συνέχεια, επιλέξτε **Αποθήκευση**.

## <a name="configure-the-import"></a>Ρύθμιση παραμέτρων της εισαγωγής

1. Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.

1. Επιλέξτε **Εμπλουτίστε τα δεδομένα μου** στο πλακίδιο **Προσαρμοσμένη εισαγωγή SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Πλακίδιο προσαρμοσμένης εισαγωγής SFTP.":::

1. Επισκοπήστε τη σύνοψη και έπειτα επιλέξτε **Επόμενο**.

1. Επιλέξτε τη σύνδεση. Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.

1. Επιλέξτε το **σύνολο δεδομένων πελάτη** και επιλέξτε το προφίλ ή το τμήμα που θέλετε να εμπλουτίσετε. Η οντότητα *Πελάτης* εμπλουτίζει όλα τα προφίλ πελατών σας ενώ ένα τμήμα εμπλουτίζει μόνο τα προφίλ πελατών που περιέχονται σε αυτό το τμήμα.

1. Επιλέξτε **Επόμενο**.

1. Εισαγάγετε τη **διαδρομή** και το **όνομα αρχείου** του αρχείου δεδομένων που θέλετε να εισαγάγετε.

1. Επιλέξτε **Επόμενο**.

1. Δώστε ένα **όνομα** για τον εμπλουτισμό και για την **Όνομα οντότητας εξόδου**.

1. Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.

1. Επιλέξτε **Εκτέλεση** για να ξεκινήσει η διεργασία εμπλουτισμού ή κλείσιμο για επιστροφή στη σελίδα **Εμπλουτισμός**.

## <a name="view-enrichment-results"></a>Προβολή αποτελεσμάτων εμπλουτισμού

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Επόμενα βήματα

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]