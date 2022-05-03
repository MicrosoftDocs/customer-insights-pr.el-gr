---
title: Σύνδεσμος Power Apps
description: Συνδεθείτε με το Power Apps και το Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647471"
---
# <a name="microsoft-power-apps-connector-preview"></a>Σύνδεση Microsoft Power Apps (προεπισκόπηση)

Φέρτε τα ενοποιημένα προφίλ πελατών στις προσωπικές σας εφαρμογές με το Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Σύνδεση Power Apps και Dynamics 365 Customer Insights

Το Customer Insights είναι μία από τις πολλές [διαθέσιμες προελεύσεις για δεδομένα στο Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Ανατρέξτε στην Power Apps τεκμηρίωση για να μάθετε πώς μπορείτε να [προσθέσετε μια σύνδεση δεδομένων σε μια εφαρμογή](/powerapps/maker/canvas-apps/add-data-connection). Συνιστάται επίσης να εξετάσετε τον [τρόπο με τον οποίο το Power Apps χρησιμοποιεί την ανάθεση για τη διαχείριση μεγάλων συνόλων δεδομένων σε Εφαρμογές καμβά](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Διαθέσιμες οντότητες

Αφού προσθέσετε το Customer Insights ως σύνδεση δεδομένων, μπορείτε να επιλέξετε τις ακόλουθες οντότητες στο Power Apps:

- **Πελάτης**: για να χρησιμοποιήσετε δεδομένα από το [ενοποιημένο προφίλ πελάτη](customer-profiles.md).
- **UnifiedActivity**: για εμφάνιση του [χρονοδιαγράμματος δραστηριοτήτων](activities.md) στην εφαρμογή.
- **ContactProfile**: για εμφάνιση των επαφών ενός πελάτη. Αυτή η οντότητα είναι διαθέσιμη μόνο σε περιβάλλοντα Customer Insights για επιχειρηματικούς λογαριασμούς.

## <a name="limitations"></a>Περιορισμοί

### <a name="retrievable-entities"></a>Οντότητες με δυνατότητα ανάκτησης

Μπορείτε να ανακτήσετε μόνο τις οντότητες **Πελάτης**, **UnifiedActivity**, **Τμήματα** και **ContactProfile** μέσω της σύνδεσης Power Apps. Το ContactProfile είναι διαθέσιμο μόνο σε παρουσία Customer Insights για επιχειρηματικούς λογαριασμούς. Εμφανίζονται άλλες οντότητες επειδή τις υποστηρίζει η υποκείμενη σύνδεση μέσω εναυσμάτων στο Power Automate.

Μπορείτε να κάνετε το πολύ 100 κλήσεις ανά 60 δευτερόλεπτα. Μπορείτε να καλέσετε το τελικό σημείο api πολλές φορές χρησιμοποιώντας την $skip λογαριασμού. [Μάθετε περισσότερα σχετικά με την $skip επιλογής](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Ανάθεση

Η ανάθεση λειτουργεί για την οντότητα **Πελάτης** και την οντότητα **UnifiedActivity**. 

- Ανάθεση για την οντότητα **Πελάτης**: για να χρησιμοποιήσετε την ανάθεση για αυτήν την οντότητα, τα πεδία πρέπει να καταχωρούνται σε ευρετήριο στην [Αναζήτηση και ευρετήριο φίλτρων](search-filter-index.md).  
- Ανάθεση για **UnifiedActivity**: Η ανάθεση για αυτή την οντότητα λειτουργεί μόνο για τα πεδία **ActivityId** και **CustomerId**.  
- Ανάθεση για **ContactProfile**: Η ανάθεση για αυτήν την οντότητα λειτουργεί μόνο για τα πεδία **ContactId** και **CustomerId**. Το ContactProfile είναι διαθέσιμο μόνο σε περιβάλλοντα Customer Insights για επιχειρηματικούς λογαριασμούς.

Για περισσότερες πληροφορίες σχετικά με την ανάθεση, μεταβείτε σε [λειτουργίες με δυνατότητα ανάθεσης Power Apps και εργασίες](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Δείγμα στοιχείου ελέγχου συλλογής

Μπορείτε να προσθέσετε προφίλ πελατών σε ένα [στοιχείο ελέγχου συλλογής](/powerapps/maker/canvas-apps/add-gallery).

1. Προσθέστε ένα στοιχείο ελέγχου **συλλογή** σε μια εφαρμογή που δημιουργείτε.

    > [!div class="mx-imgBorder"]
    > ![Προσθήκη στοιχείου συλλογής.](media/connector-powerapps9.png "Προσθήκη στοιχείου συλλογής.")

2. Επιλέξτε **Πελάτης** ως προέλευση δεδομένων για τα στοιχεία.

    > [!div class="mx-imgBorder"]
    > ![Επιλογή μιας προέλευσης δεδομένων.](media/choose-datasource-powerapps.png "Επιλογή μιας προέλευσης δεδομένων.")

3. Μπορείτε να αλλάξετε τον πίνακα δεδομένων στα δεξιά για να επιλέξετε το πεδίο για την οντότητα Πελάτη που θα εμφανίζεται στη συλλογή.

4. Εάν θέλετε να εμφανίσετε οποιοδήποτε πεδίο από τον επιλεγμένο πελάτη στη συλλογή, συμπληρώστε την ιδιότητα **Κείμενο** μιας ετικέτας χρησιμοποιώντας το **{Name_of_the_gallery}.Selected.{property_name}**  
    - Για παράδειγμα: _Gallery1.Selected.address1_city_

5. Για να εμφανίσετε την ενοποιημένη λωρίδα χρόνου για έναν πελάτη, προσθέστε ένα στοιχείο συλλογής και προσθέστε την ιδιότητα **Στοιχεία** χρησιμοποιώντας το **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Για παράδειγμα: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
