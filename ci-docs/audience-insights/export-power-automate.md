---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργία ροών στο Microsoft Power Automate από Dynamics 365 Customer Insights .
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597925"
---
# <a name="power-automate-connector-preview"></a>Σύνδεση Power Automate (προεπισκόπηση)

Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Ενεργοποιήσεις Power Automate

Χρησιμοποιήστε εναύσματα για να δημιουργήσετε ροές cloud και να αυτοματοποιήσετε επαναλαμβανόμενες εργασίες, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες. 

- Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης. 
- Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.
- Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα,...).
- Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).

[Ρυθμίστε τις παραμέτρους των εναυσμάτων στο Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Ενέργειες Power Automate
Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα. Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Δημιουργία μιας ροής Power Automate

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στο πλακίδιο **Power Automate**, επιλέξτε **Ρύθμιση**.

1. Ανοίγει η σύνδεση του Customer Insights (προεπισκόπηση) στο Power Automate. **Συνδεθείτε** στο Power Automate.

1. Επιλέξτε ένα από τα διαθέσιμα εναύσματα και προσθέστε περισσότερα βήματα στη νέα σας ροή. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία ροής cloud στο Power Automate](/power-automate/get-started-logic-flow).

Παραδείγματα τρόπου χρήσης ροών: 
- Δημοσιεύστε ένα μήνυμα σε ένα κανάλι Microsoft Teams εάν αποτύχει μια ανανέωση προέλευσης δεδομένων. 
- Αποστολή μηνύματος ηλεκτρονικού ταχυδρομείου στους κατόχους δεδομένων όταν ξεπεραστεί ένα όριο σε ένα τμήμα.



[!INCLUDE[footer-include](../includes/footer-banner.md)]