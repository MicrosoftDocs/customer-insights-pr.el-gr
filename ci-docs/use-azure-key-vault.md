---
title: Προσκομίστε το δικό σας Azure Key Vault (έκδοση προεπισκόπησης)
description: Μάθετε πώς να ρυθμίσετε τις παραμέτρους του Customer Insights ώστε να χρησιμοποιείτε το δικό σας Azure Key Vault για να διαχειρίζεστε μυστικούς κωδικούς.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246155"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Προσκομίστε το δικό σας Azure Key Vault (έκδοση προεπισκόπησης)

Η σύνδεση ενός αποκλειστικού [Azure Key Vault](/azure/key-vault/general/basic-concepts) σε ένα περιβάλλον Customer Insights βοηθά τους οργανισμούς να ανταποκριθούν στις απαιτήσεις συμμόρφωσης.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Συνδέστε το Key Vault με το περιβάλλον Customer Insights

Ρυθμίστε το αποκλειστικό Key Vault για δημιουργία σταδίων και χρήση μυστικών στο όριο συμμόρφωσης ενός οργανισμού.

### <a name="prerequisites"></a>Προϋποθέσεις

- Μια ενεργή συνδρομή Azure.

- Ένας ρόλος [Διαχειριστή](permissions.md#admin) [ανατέθηκε](permissions.md#add-users) στο Customer Insights.

- Ρόλοι [Συμβάλλων](/azure/role-based-access-control/built-in-roles#contributor) και [Διαχειριστής πρόσβασης χρήστη](/azure/role-based-access-control/built-in-roles#user-access-administrator) στο Key Vault ή στην ομάδα πόρων στην οποία ανήκει το Key Vault. Για περισσότερες πληροφορίες, μεταβείτε στην επιλογή [Προσθήκη ή κατάργηση αντιστοιχίσεων ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal). Εάν δεν έχετε το ρόλο Διαχειριστή πρόσβασης χρήστη στο Key Vault, ορίστε τα δικαιώματα ελέγχου πρόσβασης που βασίζονται σε ρόλους για την αρχή υπηρεσίας Azure για το Dynamics 365 Customer Insights ξεχωριστά. Ακολουθήστε τα βήματα για να [χρησιμοποιήσετε μια αρχή υπηρεσίας Azure](connect-service-principal.md) για το Key Vault που πρέπει να συνδεθεί.

- Το Key Vault πρέπει να έχει **απενεργοποιήσει** το τείχος προστασίας Key Vault.

- Το Key Vault βρίσκεται στην ίδια [θέση Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) με το περιβάλλον Customer Insights. Στο Customer Insights, μεταβείτε στην καρτέλα **Διαχείριση** > **Σύστημα** και **Σχετικά με** για να δείτε την περιοχή του περιβάλλοντος.

### <a name="recommendations"></a>Προτάσεις

- [Χρησιμοποιήστε ένα ξεχωριστό ή αποκλειστικό Key Vault](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) που περιέχει μόνο τα μυστικά που απαιτούνται για Customer Insights.

- Ακολουθήστε τις [βέλτιστες πρακτικές για να χρησιμοποιήσετε το Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) για πρόσβαση ελέγχου, δημιουργία αντιγράφων ασφαλείας, έλεγχο και επιλογές ανάκτησης.

### <a name="link-a-key-vault-to-the-environment"></a>Σύνδεση ενός key vault με το περιβάλλον

1. Μεταβείτε στο **Διαχειριστής** > **Ασφάλεια**, και κατόπιν επιλέξτε την καρτέλα **Key Vault**.
1. Στο πλακίδιο **Key Vault**, επιλέξτε **Ρύθμιση**.
1. Επιλέξτε μια **συνδρομή**.
1. Επιλέξτε ένα key vault από την αναπτυσσόμενη λίστα **Key Vault**. Εάν υπάρχουν υπερβολικά πολλά Key Vault, επιλέξτε μια ομάδα πόρων για να περιορίσετε τα αποτελέσματα αναζήτησης.
1. Ελέγξτε την [Προστασία προσωπικών δεδομένων και τη συμμόρφωση](connections.md#data-privacy-and-compliance) και επιλέξτε **Συμφωνώ**.
1. Επιλέξτε **Αποθήκευση**.

Το πλακίδιο **Key Vault** εμφανίζει τώρα το όνομα του συνδεδεμένου Key Vault, τη συνδρομή και την ομάδα πόρων. Είναι έτοιμο για χρήση στην εγκατάσταση σύνδεσης.
Για λεπτομέρειες σχετικά με τα δικαιώματα επί του Key Vault που εκχωρούνται στο Customer Insights, μεταβείτε στην επιλογή [Δικαιώματα που εκχωρούνται στο Key Vault](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Χρησιμοποιήστε το key vault στη ρύθμιση σύνδεσης

Κατά [ρύθμιση συνδέσεων](connections.md) σε [υποστηριζόμενα συστήματα τρίτων](#supported-connection-types), χρησιμοποιήστε τα μυστικά του συνδεδεμένου Key Vault για τη ρύθμιση των συνδέσεων.

1. Μετάβαση στον **Διαχειριστή** > **Συνδέσεις**.
1. Επιλέξτε **Προσθήκη σύνδεσης**.
1. Για τους υποστηριζόμενους τύπους σύνδεσης, διατίθεται στοιχείο εναλλαγής **Χρήση του Key Vault** αν έχετε συνδέσει ένα key vault.
1. Αντί να καταχωρήσετε το όνομα χρήστη με μη αυτόματο τρόπο, μπορείτε να επιλέξετε το όνομα του μυστικού που κατευθύνει στην τιμή του μυστικού στο key vault.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Τμήμα παραθύρου σύνδεσης με μια σύνδεση SFTP που χρησιμοποιεί ένα μυστικό Key Vault.":::

1. Για να δημιουργήσετε τη σύνδεση, επιλέξτε **Αποθήκευση**.

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

## <a name="permissions-granted-on-the-key-vault"></a>Δικαιώματα που εκχωρούνται στο key vault

Τα παρακάτω δικαιώματα εκχωρούνται στο Customer Insights σε ένα συνδεδεμένο key vault εάν έχει ενεργοποιηθεί είτε η [πολιτική πρόσβασης Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ή το [στοιχείο ελέγχου πρόσβασης που βασίζεται σε ρόλους στο Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Πολιτική πρόσβασης Key Vault

| Τύπος        | Δικαιώματα          |
| ----------- | -------------------- |
| Πλήκτρο         | [Λήψη κλειδιών](/rest/api/keyvault/keys/get-keys/get-keys), [Λήψη κλειδιού](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Μυστικό      | [Λήψη μυστικών](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Λήψη μυστικού](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Πιστοποιητικό | [Λήψη πιστοποιητικών](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Λήψη πιστοποιητικού](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Οι προηγούμενες τιμές είναι οι ελάχιστες για παράθεση και ανάγνωση κατά την εκτέλεση.

### <a name="azure-role-based-access-control"></a>Στοιχείο ελέγχου πρόσβασης βάσει ρόλων Azure

Οι ρόλοι χρήστη [Αναγνώστη Key Vault και Χρήστη μυστικών Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) θα προστεθούν για το Customer Insights.

## <a name="frequently-asked-questions"></a>Συνήθεις ερωτήσεις

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Μπορεί το Customer Insights να γράφει μυστικά ή να αντικαταστήσει μυστικά στο key vault;

Όχι. Μόνο τα δικαιώματα ανάγνωσης και παράθεσης που περιγράφονται στην ενότητα [δικαιώματα που εκχωρήθηκαν](#permissions-granted-on-the-key-vault) εκχωρούνται στο Customer Insights. Το σύστημα δεν μπορεί να προσθέσει, να διαγράψει ή να αντικαταστήσει μυστικά στο key vault. Αυτός είναι και ο λόγος για τον οποίο δεν μπορείτε να καταχωρήσετε διαπιστευτήρια όταν μια σύνδεση χρησιμοποιεί το Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Μπορώ να αλλάξω μια σύνδεση από τη χρήση των μυστικών Key Vault στον προεπιλεγμένο έλεγχο ταυτότητας;

Αρ. Δεν μπορείτε να επιστρέψετε στην προεπιλεγμένη σύνδεση αφού τη ρυθμίσετε χρησιμοποιώντας ένα στοιχείο αποθήκευσης από ένα συνδεδεμένο key vault. Δημιουργήστε μια ξεχωριστή σύνδεση και διαγράψτε την παλιά εάν δεν την χρειάζεστε πλέον.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Πώς μπορώ να ανακαλέσω την πρόσβαση σε ένα key vault για Customer Insights;

Αν η [πολιτική πρόσβασης Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ή το [στοιχείο ελέγχου πρόσβασης που βασίζεται σε ρόλους στο Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), πρέπει να καταργήσετε τα δικαιώματα για την αρχή υπηρεσίας `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` με το όνομα `Dynamics 365 AI for Customer Insights`. Όλες οι συνδέσεις που χρησιμοποιούν το key vault θα σταματήσουν να λειτουργούν.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Ένα μυστικό που χρησιμοποιείται σε μια σύνδεση καταργήθηκε από το key vault. Τι μπορώ να κάνω;

Εμφανίζεται μια ειδοποίηση στο Customer Insights όταν δεν είναι πλέον δυνατή η πρόσβαση σε ένα ρυθμισμένο μυστικό από το key vault. Ενεργοποιήστε [τη δυνατότητα προσωρινής διαγραφής](/azure/key-vault/general/soft-delete-overview) στο key vault για να επαναφέρετε τα μυστικά σε περίπτωση που έχουν διαγραφεί κατά λάθος.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Μια σύνδεση δεν λειτουργεί, αλλά το μυστικό μου βρίσκεται στο key vault. Ποια μπορεί να είναι η αιτία;

Εμφανίζεται μια ειδοποίηση στο Customer Insights όταν δεν μπορεί να αποκτήσει πρόσβαση στο key vault. Η αιτία μπορεί να είναι:

- Τα δικαιώματα για την αρχή υπηρεσίας Customer Insights καταργήθηκαν. Πρέπει να επανέρθουν με μη αυτόματο τρόπο.

- Το τείχος προστασίας στο key vault είναι ενεργοποιημένο. Το τείχος προστασίας πρέπει να απενεργοποιηθεί ώστε το key vault να είναι προσβάσιμο ξανά για το Customer Insights.
