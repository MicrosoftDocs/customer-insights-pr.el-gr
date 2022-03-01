---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργήστε ροές στο Microsoft Power Automate από το Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405807"
---
# <a name="power-automate-connector-preview"></a>Σύνδεση Power Automate (προεπισκόπηση)

Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Ενεργοποιήσεις Power Automate

Μπορείτε να χρησιμοποιήσετε μια ποικιλία εναυσμάτων που σας επιτρέπουν να δημιουργείτε ροές για την αυτοματοποίηση επαναλαμβανόμενων εργασιών, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες. 

- Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης. 
- Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.
- Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα,...).
- Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).

[Ρυθμίστε τις παραμέτρους των εναυσμάτων στο Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Ενέργειες Power Automate
Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα. Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Δημιουργία ροής Power Automate σε πληροφορίες κοινού

1. Στις πληροφορίες κοινού, μεταβείτε στο **Διαχειριστής** > **Σύστημα**.

1. Στη σελίδα **Σύστημα**, επιλέξτε την καρτέλα **Κατάσταση**.

1. Στην ενότητα **Προελεύσεις δεδομένων**, επιλέξτε **Ροές** και επιλέξτε **Δημιουργία ροής** από την αναπτυσσόμενη λίστα.
   > [!div class="mx-imgBorder"]
   > ![Η σύνδεση Power Automate που δείχνει μια ενέργεια "Δημιουργία μιας ροής"](media/power-automate-connector-create-flow.png "Η σύνδεση Power Automate που δείχνει μια ενέργεια &quot;Δημιουργία μιας ροής&quot;")

1. Στο στοιχείο Power Automate, επιλέξτε ένα από τα διαθέσιμα εναύσματα για να δημιουργήσετε τη ροή που προτιμάτε. Εάν δημιουργείτε την πρώτη σας ροή, θα πρέπει πρώτα να πραγματοποιήσετε έλεγχο ταυτότητας με τη σύνδεση του Power Automate.
