---
title: Σύνδεση Power Automate (έκδοση προεπισκόπησης) | Microsoft Docs
description: Δημιουργία ροών στο Microsoft Power Automate από Dynamics 365 Customer Insights .
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196118"
---
# <a name="power-automate-connector-preview"></a>Σύνδεση Power Automate (προεπισκόπηση)

Πυροδοτήστε συγκεκριμένα συμβάντα να προκύπτουν αυτόματα όταν αλλάζουν τα δεδομένα σας και διαχειριστείτε πιο σύνθετες ροές απευθείας στο [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Γνωστοί περιορισμοί

- Το πολύ 100 κλήσεις ανά 60 δευτερόλεπτα. Χρησιμοποιήστε το [παράμετρος $skip](/connectors/customerinsights/#get-items-from-an-entity) για να καλέσετε το τελικό σημείο του API πολλές φορές.

## <a name="power-automate-triggers"></a>Ενεργοποιήσεις Power Automate

Χρησιμοποιήστε εναύσματα για να δημιουργήσετε ροές cloud και να αυτοματοποιήσετε επαναλαμβανόμενες εργασίες, όπως ειδοποιήσεις ή πιο προηγμένες ενέργειες. Χρησιμοποιήστε ενεργοποιητές όταν:

- Η ανανέωση της πηγής δεδομένων αποτυγχάνει.
- Επιτυγχάνει η ανανέωση πηγής δεδομένων.
- Ένα όριο ξεπερνιέται σε ένα τμήμα. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Υπερβαίνεται ένα όριο σε ένα επιχειρηματικό μέτρο. Μόνο επιχειρηματικά μέτρα χωρίς διάσταση υποστηρίζονται. Η ενεργοποίηση περιορίζεται στη διάβαση πάνω από το κατώφλι.
- Ολοκληρώθηκε μια πλήρης προγραμματισμένη ανανέωση. Αυτό το έναυσμα δεν λειτουργεί για ανανεώσεις που ξεκινούν με μη αυτόματο τρόπο.
- Ολοκληρώθηκε η ανανέωση της διαδικασίας ενοποίησης.

[Ρυθμίστε τις παραμέτρους στο Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Ενέργειες Power Automate

Η Power Automate σύνδεση παρέχει άλλες ενέργειες σε σχέση με τα διαθέσιμα εναύσματα. Για περισσότερες πληροφορίες, διαβάστε το θέμα [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Δημιουργία μιας ροής Power Automate

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.

1. Στο πλακίδιο **Power Automate**, επιλέξτε **Ρύθμιση**.

1. Ανοίγει η σύνδεση του Customer Insights (προεπισκόπηση) στο Power Automate. **Συνδεθείτε** στο Power Automate.

1. Επιλέξτε ένα από τα διαθέσιμα εναύσματα και προσθέστε περισσότερα βήματα στη νέα σας ροή. Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία ροής cloud στο Power Automate](/power-automate/get-started-logic-flow).

Παραδείγματα του πώς να χρησιμοποιήσετε ροές: 
- Δημοσιεύστε ένα μήνυμα σε ένα κανάλι Microsoft Teams εάν αποτύχει μια ανανέωση προέλευσης δεδομένων. 
- Αποστολή μηνύματος ηλεκτρονικού ταχυδρομείου στους κατόχους δεδομένων όταν ξεπεραστεί ένα όριο σε ένα τμήμα.

[!INCLUDE [footer-include](includes/footer-banner.md)]
