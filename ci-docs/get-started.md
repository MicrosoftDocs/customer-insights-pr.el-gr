---
title: Γρήγορα αποτελέσματα με το Dynamics 365 Customer Insights
description: Μια επισκόπηση του Customer Insights βοηθά τους πόρους να αποκτήσουν γρήγορα αποτελέσματα.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304611"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Γρήγορα αποτελέσματα με το Dynamics 365 Customer Insights

Το Customer Insights μπορεί να σας βοηθήσει να κατανοήσετε καλύτερα τους πελάτες σας. Συνδέστε δεδομένα από διάφορες πηγές συναλλαγής, συμπεριφοράς και παρατηρητικότητας για να δημιουργήσετε μια προβολή πελάτη 360 μοιρών. Χρησιμοποιήστε αυτές τις πληροφορίες για να οδηγήσετε τις εμπειρίες και τις διεργασίες με επίκεντρο τον πελάτη. Ενοποιήστε και κατανοήστε τα δεδομένα πελατών και αξιοποιήστε τα για έξυπνες πληροφορίες και ενέργειες.

## <a name="step-1-create-an-environment"></a>Βήμα 1: Δημιουργία περιβάλλοντος

Πρώτα, δημιουργήστε ένα περιβάλλον για εργασία. Εάν ο οργανισμός σας έχει ήδη αγοράσει μια άδεια χρήσης, ανατρέξτε στο θέμα [Δημιουργία περιβάλλοντος](create-environment.md). Για να ξεκινήσετε μια δοκιμαστική έκδοση για το Customer Insights, ανατρέξτε στο θέμα [Ρύθμιση ενός δοκιμαστικού περιβάλλοντος](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Βήμα 2: Εξερεύνηση του Customer Insights

Την πρώτη φορά που θα συνδεθείτε στο Customer Insights, ρυθμίστε τις παραμέτρους και εξερευνήστε το προϊόν.

1. [Συνδεθείτε στο Customer Insights](https://home.ci.ai.dynamics.com) χρησιμοποιώντας το λογαριασμό χρήστη Microsoft Azure Active Directory (AAD).

1. Αλλάξτε το περιβάλλον για να δείτε τα δεδομένα επίδειξης και [να εξερευνήσετε το Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Βήμα 3: Κατάποση, ενοποίηση και ρύθμιση Σχέσεις για τα δεδομένα σας

Τα ενοποιημένα προφίλ αποτελούν τη βάση για τη λήψη πληροφοριών και την ανάληψη ενεργειών σχετικά με τα δεδομένα. Εισαγωγή δεδομένων από διάφορες προελεύσεις και εκτέλεση της διαδικασίας έγκρισης δεδομένων για συνδυασμό ενοποιημένων προφίλ. Καθορίστε σχέσεις μεταξύ των οντοτήτων που έχουν ληφθεί και χρησιμοποιήστε δυνατότητες εμπλουτισμού για να προσθέσετε πληροφορίες στα προφίλ.

1. Κάντε εισαγωγή δεδομένων δημιουργώντας προελεύσεις δεδομένων από πολλές επιλογές. Επιλέξτε μεταξύ [Azure Data Lake Storage, συμπεριλαμβανομένου του Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) ή [συνδέσμων Power Query](connect-power-query.md).

1. Εκτελέστε τη [διεργασία ενοποίησης δεδομένων](data-unification.md) προσδιορίζοντας τα [πεδία προέλευσης](map-entities.md), καταργώντας [διπλότυπα](remove-duplicates.md), [αντιστοιχίζοντας συνθήκες](match-entities.md) και [ενοποιώντας πεδία](merge-entities.md).

1. Εξοικειωθείτε με τις [οντότητες που δημιουργεί το σύστημα](entities.md) και [Σχέσεις μεταξύ των οντοτήτων που έχουν σχέση με την λήψη](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Βήμα 4: Βελτίωση ενοποιημένων προφίλ με προβλέψεις, δραστηριότητες και μέτρα

Με τη ρύθμιση ενοποιημένων προφίλ, βελτιώστε τα δεδομένα σας και αυξήστε περαιτέρω τις πληροφορίες που παρέχουν.

1. Επιλέξτε από μια αναπτυγμένη βιβλιοθήκη υπηρεσιών παροχής εμπλουτισμού για να [εμπλουτίσετε τα δεδομένα των πελατών σας](enrichment-hub.md).

1. Χρησιμοποιήστε [διαθέσιμα μοντέλα](predictions-overview.md) για να προβλέψετε πιθανότητες απώλειας ή αναμενόμενα έσοδα.

1. [Ρυθμίστε τις παραμέτρους των δραστηριοτήτων](activities.md) με βάση δεδομένα που έχουν κατά προσέγγιση και απεικονίστε τις αλληλεπιδράσεις με τους πελάτες σας σε ένα χρονολογική χρονοδιάγραμμα.

1. [Δημιουργήστε μέτρα](measures.md) για τη μέτρηση των επιχειρηματικών σας στόχων και των KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Βήμα 5: Δημιουργία τμημάτων αγοράς και ενεργοποίηση δεδομένων μέσω διάφορων επιλογών εξαγωγής

Τώρα που τα δεδομένα σας έχουν ολοκληρωθεί και περιέχουν ένα ευρύ φάσμα πληροφοριών για τους πελάτες σας, αναζητήστε τρόπους αντιμετώπισης αυτών των δεδομένων.

1. [Δημιουργήστε τμήματα](segments.md), υποσύνολα της πελατειακής σας βάσης, για να εξασφαλίσετε ότι οι ενέργειες σας είναι σχετικές με τους πελάτες-στόχους.

1. Περιηγηθείτε στον εκτεταμένο κατάλογο [επιλογών εξαγωγής](export-destinations.md) όπου μπορείτε να χρησιμοποιήσετε δεδομένα πελατών. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε δεδομένα για να διαχειριστείτε προωθήσεις και επαφές με το ψηφιακή μάρκετινγκ.

1. Εξετάστε τις επιλογές ενοποίησης, για παράδειγμα σε άλλες εφαρμογές Dynamics 365 με το [πρόσθετο Κάρτας πελάτη](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]