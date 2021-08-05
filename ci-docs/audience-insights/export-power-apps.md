---
title: Σύνδεσμος Power Apps
description: Συνδεθείτε με το Power Apps και το Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554113"
---
# <a name="microsoft-power-apps-connector-preview"></a>Σύνδεση Microsoft Power Apps (προεπισκόπηση)

Φέρτε τα ενοποιημένα προφίλ πελατών στις προσωπικές σας εφαρμογές με το Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Σύνδεση Power Apps και Dynamics 365 Customer Insights

Το Customer Insights είναι μία από τις πολλές [διαθέσιμες προελεύσεις για δεδομένα στο Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Ανατρέξτε στην Power Apps τεκμηρίωση για να μάθετε πώς μπορείτε να [προσθέσετε μια σύνδεση δεδομένων σε μια εφαρμογή](/powerapps/maker/canvas-apps/add-data-connection). Συνιστάται επίσης να εξετάσετε τον [τρόπο με τον οποίο το Power Apps χρησιμοποιεί την ανάθεση για τη διαχείριση μεγάλων συνόλων δεδομένων σε Εφαρμογές καμβά](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Διαθέσιμες οντότητες

Αφού προσθέσετε το Customer Insights ως σύνδεση δεδομένων, μπορείτε να επιλέξετε τις ακόλουθες οντότητες στο Power Apps:

- Πελάτης: για να χρησιμοποιήσετε δεδομένα από το [ενοποιημένο προφίλ πελάτη](customer-profiles.md).
- UnifiedActivity: για την εμφάνιση της [λωρίδας χρόνου δραστηριότητας](activities.md) στην εφαρμογή.

## <a name="limitations"></a>Περιορισμοί

### <a name="retrievable-entities"></a>Οντότητες με δυνατότητα ανάκτησης

Μπορείτε να ανακτήσετε μόνο τις οντότητες **Πελάτης**, **UnivifedActivity** και **Τμήματα** μέσω της σύνδεσης Power Apps. Εμφανίζονται άλλες οντότητες επειδή τις υποστηρίζει η υποκείμενη σύνδεση μέσω εναυσμάτων στο Power Automate.  

### <a name="delegation"></a>Ανάθεση

Η ανάθεση λειτουργεί για την οντότητα Πελάτης και την οντότητα UnifiedActivity. 

- Ανάθεση για την οντότητα **Πελάτης**: για να χρησιμοποιήσετε την ανάθεση για αυτήν την οντότητα, τα πεδία πρέπει να καταχωρούνται σε ευρετήριο στην [Αναζήτηση και ευρετήριο φίλτρων](search-filter-index.md).  

- Ανάθεση για **UnifiedActivity**: Η ανάθεση για αυτή την οντότητα λειτουργεί μόνο για τα πεδία **ActivityId** και **CustomerId**.  

- Για περισσότερες πληροφορίες σχετικά με την ανάθεση, ανατρέξτε στο θέμα [Λειτουργίες με δυνατότητα ανάθεσης στο Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Δείγμα στοιχείου ελέγχου συλλογής

Για παράδειγμα, μπορείτε να προσθέσετε προφίλ πελατών σε ένα [στοιχείο ελέγχου συλλογής](/powerapps/maker/canvas-apps/add-gallery).

1. Προσθέστε ένα στοιχείο ελέγχου **Συλλογή** σε μια εφαρμογή που δημιουργείτε.

> [!div class="mx-imgBorder"]
> ![Προσθήκη στοιχείου συλλογής.](media/connector-powerapps9.png "Προσθήκη στοιχείου συλλογής")

1. Επιλέξτε **Πελάτης** ως προέλευση δεδομένων για τα στοιχεία.

    > [!div class="mx-imgBorder"]
    > ![Επιλογή μιας προέλευσης δεδομένων.](media/choose-datasource-powerapps.png "Επιλογή μιας προέλευσης δεδομένων")

1. Μπορείτε να αλλάξετε τον πίνακα δεδομένων στα δεξιά για να επιλέξετε το πεδίο για την οντότητα Πελάτη που θα εμφανίζεται στη συλλογή.

1. Εάν θέλετε να εμφανίσετε οποιοδήποτε πεδίο από τον επιλεγμένο πελάτη στη συλλογή, συμπληρώστε την ιδιότητα Κείμενο μιας ετικέτας:  **{Name_of_the_gallery}.Επιλεγμένο.{property_name}**

    Παράδειγμα: Gallery1.Selected.address1_city

1. Για να εμφανίσετε την ενοποιημένη λωρίδα χρόνου για έναν πελάτη, προσθέστε ένα στοιχείο Συλλογής και προσθέστε την ιδιότητα Στοιχεία: **Filter('Ενοποιημένη δραστηριότητα πελάτη', CustomerId = {Customer_Id})**

    Παράδειγμα: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]