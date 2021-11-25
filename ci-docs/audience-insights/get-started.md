---
title: Γρήγορα αποτελέσματα με τις πληροφορίες κοινού στο Dynamics 365 Customer Insights
description: Μια επισκόπηση των κοινό πληροφοριών βοηθά τους πόρους να έχουν γρήγορα αποτελέσματα.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645264"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Γρήγορα αποτελέσματα με τις πληροφορίες κοινού Dynamics 365 Customer Insights

Οι πληροφορίες κοινού, σάς βοηθάνε να κατανοήσετε καλύτερα τους πελάτες σας. Συνδέστε δεδομένα από διάφορες πηγές συναλλαγής, συμπεριφοράς και παρατηρητικότητας για να δημιουργήσετε μια προβολή πελάτη 360 μοιρών. Χρησιμοποιήστε αυτές τις πληροφορίες για να οδηγήσετε τις εμπειρίες και τις διεργασίες με επίκεντρο τον πελάτη. Ενοποιήστε και κατανοήστε τα δεδομένα πελατών και αξιοποιήστε τα για έξυπνες πληροφορίες και ενέργειες.

## <a name="step-1-create-an-environment"></a>Βήμα 1: Δημιουργία περιβάλλοντος

Για να ξεκινήσετε, πρέπει πρώτα να δημιουργήσετε ένα περιβάλλον στο οποίο θα εργαστείτε. Εάν ο οργανισμός σας έχει ήδη αγοράσει μια άδεια χρήσης, ανατρέξτε στο θέμα [Δημιουργία περιβάλλοντος](create-environment.md). Για να ξεκινήσετε μια δοκιμαστική έκδοση για κοινό πληροφορίες, ανατρέξτε στο θέμα [Ρύθμιση ενός δοκιμαστικού περιβάλλοντος](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Βήμα 2: Εξερεύνηση πληροφοριών κοινού

Την πρώτη φορά που θα συνδεθείτε στις Πληροφορίες κοινού μπορείτε να ρυθμίσετε τις παραμέτρους και να εξερευνήσετε το προϊόν.

1. [Συνδεθείτε με τις πληροφορίες κοινού](https://home.ci.ai.dynamics.com) χρησιμοποιώντας το λογαριασμό χρήστη Microsoft Azure Active Directory (AAD).

1. [Αλλάξτε το περιβάλλον](manage-environments.md#switch-environments) για να δείτε τα δεδομένα επίδειξης και να [εξερευνήσετε τις πληροφορίες κοινού](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Βήμα 3: Κατάποση, ενοποίηση και ρύθμιση Σχέσεις για τα δεδομένα σας

Τα ενοποιημένα προφίλ αποτελούν τη βάση για τη λήψη πληροφοριών και την ανάληψη ενεργειών σχετικά με τα δεδομένα. Εισαγωγή δεδομένων από διάφορες προελεύσεις και εκτέλεση της διαδικασίας έγκρισης δεδομένων για συνδυασμό ενοποιημένων προφίλ. Καθορίστε Σχέσεις μεταξύ των οντοτήτων που έχουν χρησιμοποιηθεί χρησιμοποιούν δυνατότητες εμπλουτισμού για την προσθήκη πληροφοριών στα προφίλ. 

1. Κάντε εισαγωγή δεδομένων δημιουργώντας προελεύσεις δεδομένων από πολλές επιλογές. Επιλέξτε μεταξύ [Power Query σύνδεσης](connect-power-query.md), ένα φάκελο [Common Data Model](connect-common-data-model.md), ή [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Εκτελέστε τη [διεργασία αντιστοίχισης δεδομένων](data-unification.md) μέσω του [χάρτη](map-entities.md), της [αντιστοίχισης](match-entities.md) και των φάσεων [συγχώνευσης](merge-entities.md).

1. Εξοικειωθείτε με τις [οντότητες που δημιουργεί το σύστημα](entities.md) και [Σχέσεις μεταξύ των οντοτήτων που έχουν σχέση με την λήψη](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Βήμα 4: Βελτίωση ενοποιημένων προφίλ με προβλέψεις, δραστηριότητες και μέτρα

Με τη ρύθμιση ενοποιημένων προφίλ, μπορείτε να βελτιώσετε τα δεδομένα σας και να αυξήσετε περαιτέρω τις πληροφορίες που παρέχουν.

1. Επιλέξτε από μια αναπτυγμένη βιβλιοθήκη υπηρεσιών παροχής εμπλουτισμού για να [εμπλουτίσετε τα δεδομένα των πελατών σας](enrichment-hub.md).

1. Χρησιμοποιήστε [διαθέσιμα μοντέλα](predictions-overview.md) για να προβλέψετε πιθανότητες απώλειας ή αναμενόμενα έσοδα.

1. [Ρυθμίστε τις παραμέτρους των δραστηριοτήτων](activities.md) με βάση δεδομένα που έχουν κατά προσέγγιση και απεικονίστε τις αλληλεπιδράσεις με τους πελάτες σας σε ένα χρονολογική χρονοδιάγραμμα. 

1. [Δημιουργήστε μέτρα](measures.md) για τη μέτρηση των επιχειρηματικών σας στόχων και των KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Βήμα 5: Δημιουργία τμημάτων αγοράς και ενεργοποίηση δεδομένων μέσω διάφορων επιλογών εξαγωγής

Τώρα που τα δεδομένα σας έχουν ολοκληρωθεί και περιέχουν ένα ευρύ φάσμα πληροφοριών για τους πελάτες σας, είναι ώρα να αναζητήσετε τρόπους για να ενεργούν βάσει αυτών των δεδομένων. 

1. [Δημιουργήστε τμήματα](segments.md), υποσύνολα της πελατειακής σας βάσης, για να εξασφαλίσετε ότι οι ενέργειες σας είναι σχετικές με τους πελάτες-στόχους.

1. Περιηγηθείτε στον εκτεταμένο κατάλογο [επιλογών εξαγωγής](export-destinations.md) όπου μπορείτε να χρησιμοποιήσετε δεδομένα πελατών. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε δεδομένα για να διαχειριστείτε προωθήσεις και επαφές με το ψηφιακή μάρκετινγκ.

1. Εξετάστε τις επιλογές ενοποίησης, για παράδειγμα, με την [άμεση σύνδεση στις πληροφορίες δέσμευσης](../engagement-insights/integrate-audience-insights-engagement-insights.md) ή σε άλλες εφαρμογές Dynamics 365 με το πρόσθετο [Κάρτα πελάτη](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]