---
title: Σύνδεσμος Power Automate | Microsoft Docs
description: Δημιουργία ροών στο Microsoft Power Automate από Dynamics 365 Customer Insights .
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dd90ef4576246b49d4a9c74005196ee9813a6744
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455907"
---
# <a name="power-automate-connector-preview"></a>Σύνδεση Power Automate (προεπισκόπηση)

Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Μπορείτε να κάνετε το πολύ 100 κλήσεις ανά 60 δευτερόλεπτα. Μπορείτε να καλέσετε το τελικό σημείο api πολλές φορές χρησιμοποιώντας την $skip λογαριασμού. [Μάθετε περισσότερα σχετικά με την $skip επιλογής](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Ενεργοποιήσεις Power Automate

Χρησιμοποιήστε εναύσματα για να δημιουργήσετε ροές cloud και να αυτοματοποιήσετε επαναλαμβανόμενες εργασίες, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες. 

- Ενεργοποιείται όταν αποτύχει μια προέλευση δεδομένων ανανέωσης. 
- Ενεργοποιείται όταν επιτύχει μια προέλευση δεδομένων ανανέωσης.
- Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε ένα τμήμα αγοράς. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ενεργοποιείται όταν διασταυρώνεται ένα όριο σε μια επιχειρηματική μέτρηση. Μόνο επιχειρηματικά μέτρα χωρίς διάσταση υποστηρίζονται. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ενεργοποίηση κατά την ολοκλήρωση μιας πλήρους ανανέωσης (προελεύσεις δεδομένων, τμήματα, μέτρα, ...).
- Ενεργοποιείται όταν ολοκληρώνεται η ανανέωση της διαδικασίας ενοποίησης (αντιστοίχιση, ταίριασμα, συγχώνευση).

[Ρυθμίστε τις παραμέτρους στο Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Ενέργειες Power Automate

Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα. Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Δημιουργία μιας ροής Power Automate

1. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Εξαγωγή προορισμών**.

1. Στο πλακίδιο **Power Automate**, επιλέξτε **Ρύθμιση**.

1. Ανοίγει η σύνδεση του Customer Insights (προεπισκόπηση) στο Power Automate. **Συνδεθείτε** στο Power Automate.

1. Επιλέξτε ένα από τα διαθέσιμα εναύσματα και προσθέστε περισσότερα βήματα στη νέα σας ροή. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία ροής cloud στο Power Automate](/power-automate/get-started-logic-flow).

Παραδείγματα του πώς να χρησιμοποιήσετε ροές: 
- Δημοσιεύστε ένα μήνυμα σε ένα κανάλι Microsoft Teams εάν αποτύχει μια ανανέωση προέλευσης δεδομένων. 
- Αποστολή μηνύματος ηλεκτρονικού ταχυδρομείου στους κατόχους δεδομένων όταν ξεπεραστεί ένα όριο σε ένα τμήμα.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
