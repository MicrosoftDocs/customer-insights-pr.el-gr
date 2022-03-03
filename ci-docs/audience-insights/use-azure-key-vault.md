---
title: Προσκομίστε το δικό σας Azure Key Vault για τη διαχείριση μυστικών
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους του Customer Insights ώστε να χρησιμοποιείτε το δικό σας Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 5b22c1464b3f089551f485f98d6d93840ff77136
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355891"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Προσκομίστε το δικό σας Azure Key Vault (έκδοση προεπισκόπησης)

Η σύνδεση ενός αποκλειστικού [Azure Key Vault](/azure/key-vault/general/basic-concepts)σε ένα περιβάλλον πληροφοριών κοινού βοηθά τους οργανισμούς να ανταποκριθούν στις απαιτήσεις συμμόρφωσης.
Το αποκλειστικό Key Vault μπορεί να χρησιμοποιηθεί για προεργασία και χρήση μυστικών στο όριο συμμόρφωσης ενός οργανισμού. Οι πληροφορίες κοινού μπορούν να χρησιμοποιούν τα μυστικά του Azure Key Vault για τη [ρύθμιση συνδέσεων](connections.md) σε συστήματα τρίτων.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Συνδέστε το Key Vault με το περιβάλλον πληροφοριών κοινού

### <a name="prerequisites"></a>Προϋποθέσεις

Για να ρυθμίσετε τις παραμέτρους του Key Vault στις πληροφορίες κοινού, πρέπει να πληρούνται οι παρακάτω προϋποθέσεις:

- Έχετε ενεργή συνδρομή στο Azure.

- Έχετε τον ρόλο [Διαχειριστή](permissions.md#administrator) στις πληροφορίες κοινού. Μάθετε περισσότερα σχετικά με τα [δικαιώματα χρηστών σε πληροφορίες κοινού](permissions.md#assign-roles-and-permissions).

- Έχετε τους ρόλους [Συμμετέχων](/azure/role-based-access-control/built-in-roles#contributor) και [Διαχειριστής πρόσβασης χρήστη](/azure/role-based-access-control/built-in-roles#user-access-administrator) στο Key Vault ή στην ομάδα πόρων στην οποία ανήκει το Key Vault. Για περισσότερες πληροφορίες, μεταβείτε στην επιλογή [Προσθήκη ή κατάργηση αντιστοιχίσεων ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal). Εάν δεν έχετε το ρόλο Διαχειριστή πρόσβασης χρήστη στο Key Vault, πρέπει να ορίσετε τα δικαιώματα ελέγχου πρόσβασης που βασίζονται σε ρόλους για την αρχή υπηρεσίας Azure για το Dynamics 365 Customer Insights ξεχωριστά. Ακολουθήστε τα βήματα για να [χρησιμοποιήσετε μια αρχή υπηρεσίας Azure](connect-service-principal.md) για το Key Vault που πρέπει να συνδεθεί.

- Το key vault πρέπει να έχει **απενεργοποιήσει** το τείχος προστασίας Key Vault.

- Το key vault βρίσκεται στην ίδια [θέση Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) με το περιβάλλον πληροφοριών κοινού. Η περιοχή του περιβάλλοντος στις πληροφορίες κοινού παρατίθεται στην περιοχή **Διαχειριστής** > **Σύστημα** > **Σχετικά με** > **Περιοχή**.

### <a name="link-a-key-vault-to-the-environment"></a>Σύνδεση ενός key vault με το περιβάλλον

1. Μεταβείτε στο **Διαχειριστής** > **Σύστημα**, και κατόπιν επιλέξτε την καρτέλα **Ασφάλεια**.
1. Στο πλακίδιο **Key Vault**, επιλέξτε **Ρύθμιση**.
1. Επιλέξτε μια **συνδρομή**.
1. Επιλέξτε ένα key vault από την αναπτυσσόμενη λίστα **Key Vault**. Εάν εμφανίζονται υπερβολικά πολλά key vault, επιλέξτε μια ομάδα πόρων για να περιορίσετε τα αποτελέσματα αναζήτησης.
1. Αποδεχτείτε τη δήλωση **προστασίας προσωπικών δεδομένων και συμμόρφωσης**.
1. Επιλέξτε **Αποθήκευση**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Βήματα για να ρυθμίσετε ένα συνδεδεμένο key vault στις πληροφορίες κοινού.":::

Το πλακίδιο **Key Vault** εμφανίζει τώρα το όνομα του συνδεδεμένου κλειδιού, την ομάδα πόρων και τη συνδρομή. Είναι έτοιμο για χρήση στην εγκατάσταση σύνδεσης.
Για λεπτομέρειες σχετικά με τα δικαιώματα που εκχωρούνται στο key vault στις πληροφορίες κοινού, μεταβείτε στην επιλογή [Δικαιώματα που εκχωρούνται στο key vault στις πληροφορίες κοινού](#permissions-granted-on-the-key-vault-to-audience-insights), στη συνέχεια αυτού του άρθρου.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Χρησιμοποιήστε το key vault στη ρύθμιση σύνδεσης

Κατά [ρύθμιση συνδέσεων](connections.md) σε συστήματα τρίτων, μπορούν να χρησιμοποιηθούν τα μυστικά του συνδεδεμένου Key Vault για τη ρύθμιση των συνδέσεων.

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.
1. Επιλέξτε **Προσθήκη σύνδεσης**.
1. Για τους υποστηριζόμενους τύπους σύνδεσης, διατίθεται στοιχείο εναλλαγής **Χρήση του Key Vault** αν έχετε συνδέσει ένα key vault.
1. Αντί να καταχωρήσετε το όνομα χρήστη με μη αυτόματο τρόπο, μπορείτε να επιλέξετε το όνομα του μυστικού που κατευθύνει στην τιμή του μυστικού στο key vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Τμήμα παραθύρου σύνδεσης με μια σύνδεση SFTP που χρησιμοποιεί ένα μυστικό Key Vault.":::

## <a name="supported-connection-types"></a>Υποστηριζόμενοι τύποι σύνδεσης

Υποστηρίζονται οι παρακάτω συνδέσεις [εξαγωγής](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Αυτόματος Πιλότος](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Δικαιώματα που εκχωρούνται στο key vault σε πληροφορίες κοινού

Τα παρακάτω δικαιώματα εκχωρούνται σε πληροφορίες κοινού για ένα συνδεδεμένο key vault εάν έχει ενεργοποιηθεί είτε η [πολιτική πρόσβασης Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ή το [στοιχείο ελέγχου πρόσβασης που βασίζεται σε ρόλους στο Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Πολιτική πρόσβασης Key Vault

| Τύπος        | Δικαιώματα          |
| ----------- | -------------------- |
| Πλήκτρο         | [Λήψη κλειδιών](/rest/api/keyvault/get-keys), [Λήψη κλειδιού](/rest/api/keyvault/get-key)                                 |
| Μυστικό      | [Λήψη μυστικών](/rest/api/keyvault/get-secrets), [Λήψη μυστικού](/rest/api/keyvault/get-secret)                     |
| Πιστοποιητικό | [Λήψη πιστοποιητικών](/rest/api/keyvault/get-certificates), [Λήψη πιστοποιητικού](/rest/api/keyvault/get-certificate) |

Οι προηγούμενες τιμές είναι οι ελάχιστες για παράθεση και ανάγνωση κατά την εκτέλεση.

### <a name="azure-role-based-access-control"></a>Στοιχείο ελέγχου πρόσβασης βάσει ρόλων Azure

Οι ρόλοι χρήστη Αναγνώστη Key Vault και Χρήστη μυστικών Key Vault θα προστεθούν για πληροφορίες κοινού. Για λεπτομέρειες σχετικά με αυτούς τους ρόλους, μεταβείτε στους [ενσωματωμένους ρόλους Azure για τις λειτουργίες αποθήκευσης δεδομένων Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Προτάσεις

- Χρησιμοποιήστε ένα ξεχωριστό ή αποκλειστικό key vault που περιέχει μόνο τα μυστικά που απαιτούνται για πληροφορίες κοινού. Μάθετε περισσότερα για τους λόγους [για τους οποίους συνιστώνται ξεχωριστοί χώροι αποθήκευσης κλειδιών](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Ακολουθήστε τις [βέλτιστες πρακτικές για να χρησιμοποιήσετε το Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) για πρόσβαση ελέγχου, δημιουργία αντιγράφων ασφαλείας, έλεγχο και επιλογές ανάκτησης.

## <a name="frequently-asked-questions"></a>Συνήθεις ερωτήσεις

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Μπορούν οι πληροφορίες κοινού να γράφουν μυστικά ή να αντικαταστήσουν μυστικά στο key vault;

Αρ. Μόνο τα δικαιώματα ανάγνωσης και παράθεσης που περιγράφονται στην ενότητα [εκχωρούνται δικαιώματα](#permissions-granted-on-the-key-vault-to-audience-insights) νωρίτερα σε αυτό το άρθρο εκχωρούνται σε πληροφορίες κοινού. Το σύστημα δεν μπορεί να προσθέσει, να διαγράψει ή να αντικαταστήσει μυστικά στο key vault. Αυτός είναι και ο λόγος για τον οποίο δεν μπορείτε να καταχωρήσετε διαπιστευτήρια όταν μια σύνδεση χρησιμοποιεί το Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Μπορώ να αλλάξω μια σύνδεση από τη χρήση των μυστικών Key Vault στον προεπιλεγμένο έλεγχο ταυτότητας;

Αρ. Δεν μπορείτε να επιστρέψετε στην προεπιλεγμένη σύνδεση αφού τη ρυθμίσετε χρησιμοποιώντας ένα στοιχείο αποθήκευσης από ένα συνδεδεμένο key vault. Δημιουργήστε μια ξεχωριστή σύνδεση και διαγράψτε την παλιά εάν δεν την χρειάζεστε πλέον.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Πώς μπορώ να ανακαλέσω την πρόσβαση σε ένα key vault για πληροφορίες κοινού;

Ανάλογα με το εάν έχει ενεργοποιηθεί η [πολιτική πρόσβασης Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ή το [στοιχείο ελέγχου πρόσβασης που βασίζεται σε ρόλους στο Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), πρέπει να καταργήσετε τα δικαιώματα για την αρχή υπηρεσίας `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` με το όνομα `Dynamics 365 AI for Customer Insights`. Όλες οι συνδέσεις που χρησιμοποιούν το key vault θα σταματήσουν να λειτουργούν.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Ένα μυστικό που χρησιμοποιείται σε μια σύνδεση καταργήθηκε από το key vault. Τι μπορώ να κάνω;

Εμφανίζεται μια ειδοποίηση στις πληροφορίες κοινού όταν δεν είναι πλέον δυνατή η πρόσβαση σε ένα ρυθμισμένο μυστικό από το key vault. Ενεργοποιήστε [τη δυνατότητα προσωρινής διαγραφής](/azure/key-vault/general/soft-delete-overview) στο key vault για να επαναφέρετε τα μυστικά σε περίπτωση που έχουν διαγραφεί κατά λάθος.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Μια σύνδεση δεν λειτουργεί, αλλά το μυστικό μου βρίσκεται στο key vault. Ποια μπορεί να είναι η αιτία;

Εμφανίζεται μια ειδοποίηση στις πληροφορίες κοινού όταν δεν μπορεί να αποκτήσει πρόσβαση στο key vault. Η αιτία μπορεί να είναι:

- Τα δικαιώματα για την αρχή υπηρεσίας πληροφοριών κοινού καταργήθηκαν. Πρέπει να επανέρθουν με μη αυτόματο τρόπο.

- Το τείχος προστασίας στο key vault είναι ενεργοποιημένο. Το τείχος προστασίας πρέπει να απενεργοποιηθεί ώστε το key vault να είναι προσβάσιμο ξανά για πληροφορίες κοινού.
