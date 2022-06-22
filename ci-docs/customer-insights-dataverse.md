---
title: Εργασία με δεδομένα Customer Insights στο Microsoft Dataverse
description: Μάθετε πώς να συνδέσετε το Customer Insights και το Microsoft Dataverse και κατανοήστε τις οντότητες εξόδου που εξάγονται στο Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011520"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Εργασία με δεδομένα Customer Insights στο Microsoft Dataverse

Το Customer Insights παρέχει την επιλογή ώστε οι οντότητες εξόδου να είναι διαθέσιμες ως [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Αυτή η ενοποίηση επιτρέπει την εύκολη κοινοποίηση δεδομένων και την προσαρμοσμένη ανάπτυξη μέσω προσέγγισης με χαμηλό περιεχόμενο κώδικα / χωρίς κώδικα. Οι [οντότητες εξόδου](#output-entities) είναι διαθέσιμες ως πίνακες σε ένα Dataverse περιβάλλον. Μπορείτε να χρησιμοποιήσετε τα δεδομένα για οποιαδήποτε άλλη εφαρμογή βάσει πινάκων Dataverse. Αυτοί οι πίνακες επιτρέπουν σενάρια, όπως αυτοματοποιημένες ροές εργασιών μέσω Power Automate ή δημιουργία εφαρμογών με το Power Apps.

Η σύνδεση στο περιβάλλον σας Dataverse σάς επιτρέπει επίσης να [προσλαμβάνετε δεδομένα από προελεύσεις δεδομένων εσωτερικής εγκατάστασης χρησιμοποιώντας ροές δεδομένων και πύλες Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Προϋποθέσεις

- Τα περιβάλλοντα Customer Insights και Dataverse πρέπει να φιλοξενούνται στην ίδια περιοχή.
- Πρέπει να έχετε ρόλο καθολικού διαχειριστή στο περιβάλλον Dataverse. Επαληθεύστε ότι αυτό το [Dataverse περιβάλλον σχετίζεται](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) με ορισμένες ομάδες ασφαλείας και βεβαιωθείτε ότι έχετε προστεθεί σε αυτές τις ομάδες ασφαλείας.
- Κανένα άλλο περιβάλλον Customer Insights δεν συσχετίζεται ήδη με το περιβάλλον Dataverse που θέλετε να συνδέσετε. Μάθετε πώς να [καταργήσετε μια υπάρχουσα σύνδεση σε ένα Dataverse περιβάλλον](#remove-an-existing-connection-to-a-dataverse-environment).
- Ένα περιβάλλον Microsoft Dataverse μπορεί να συνδεθεί μόνο σε ένα λογαριασμό χώρου αποθήκευσης. Εφαρμόζεται μόνο εάν ρυθμίσετε τις παραμέτρους του περιβάλλοντος για να [χρησιμοποιήσετε το Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Σύνδεση περιβάλλοντος Dataverse στο Customer Insights

Το βήμα **Microsoft Dataverse** σάς επιτρέπει να συνδέσετε το Customer Insights με το περιβάλλον Dataverse σας κατά [τη δημιουργία ενός περιβάλλοντος Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="κοινή χρήση δεδομένων με Microsoft Dataverse που ενεργοποιείται αυτόματα για νέα περιβάλλοντα.":::

Οι διαχειριστές μπορούν να ρυθμίσουν τις παραμέτρους του Customer Insights ώστε να συνδέουν ένα υπάρχον περιβάλλον Dataverse. Παρέχοντας τη διεύθυνση URL στο περιβάλλον Dataverse, επισυνάπτεται στο νέο περιβάλλον Customer Insights.

Εάν δεν θέλετε να χρησιμοποιήσετε ένα υπάρχον Dataverse περιβάλλον, το σύστημα δημιουργεί ένα νέο περιβάλλον για τα δεδομένα Customer Insights στον μισθωτή σας. [Οι διαχειριστές του Power Platform μπορεί να ελέγχει ποιος μπορεί να δημιουργήσει περιβάλλοντα](/power-platform/admin/control-environment-creation). Όταν ρυθμίζετε ένα νέο περιβάλλον Customer Insights και ο διαχειριστής έχει απενεργοποιήσει τη δημιουργία περιβαλλόντων Dataverse για όλους εκτός από διαχειριστές, ενδεχομένως να μην μπορείτε να δημιουργήσετε ένα νέο περιβάλλον.

**Ενεργοποιήστε την κοινή χρήση δεδομένων** με το Dataverse επιλέγοντας το πλαίσιο ελέγχου κοινής χρήσης δεδομένων.

Αν χρησιμοποιείτε το δικό σας λογαριασμό χώρου αποθήκευσης Data Lake, χρειάζεστε επίσης το **αναγνωριστικό δικαιωμάτων**. Για περισσότερες πληροφορίες σχετικά με τον τρόπο λήψης του αναγνωριστικού δικαιωμάτων, ανατρέξτε στην παρακάτω ενότητα.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Ενεργοποίηση κοινής χρήσης δεδομένων με το Dataverse από το δικό σας Azure Data Lake Storage (εκδοση προεπισκόπησης)

Η ενεργοποίηση της κοινής χρήσης δεδομένων με το Microsoft Dataverse όταν το περιβάλλον σας [χρησιμοποιεί τον δικό σας λογαριασμό Azure Data Lake Storage](own-data-lake-storage.md) χρειάζεται επιπλέον ρύθμιση παραμέτρων. Ο χρήστης που ρυθμίζει το περιβάλλον Customer Insights πρέπει να έχει τουλάχιστον δικαιώματα **αναγνώστη δεδομένων αντικειμένου Blob χώρου αποθήκευσης** στο κοντέινερ *CustomerInsights* στον λογαριασμό Azure Data Lake Storage.

1. Δημιουργήστε δύο ομάδες ασφαλείας στη συνδρομή σας στο Azure - μία ομάδα ασφαλείας **Αναγνώστης** και μία ομάδα ασφαλείας **Συμβάλλων** και ορίστε την υπηρεσία Microsoft Dataverse ως κάτοχο και για τις δύο ομάδες ασφαλείας.
2. Διαχειριστείτε τη Λίστα ελέγχου πρόσβασης (ACL) στο κοντέινερ CustomerInsights στο λογαριασμό χώρου αποθήκευσης μέσω αυτών των ομάδων ασφαλείας. Προσθέστε την Microsoft Dataverse υπηρεσία και οποιεσδήποτε Dataverseε πιχειρηματικές εφαρμογές βασισμένες σε αυτήν, όπως το Dynamics 365 Marketing στην ομάδα ασφαλείας **Αναγνώστης** με δικαιώματα **μόνο για ανάγνωση**. Προσθέστε *μόνο* την εφαρμογή Customers Insights στην ομάδα ασφαλείας **Συμβάλλων** για να χορηγήσετε δικαιώματα **ανάγνωσης και εγγραφής** για τη σύνταξη προφίλ και πληροφοριών.

### <a name="limitations"></a>Περιορισμοί

Υπάρχουν δύο περιορισμοί κατά τη χρήση του Dataverse με τον δικό σας λογαριασμό Azure Data Lake Storage:

- Υπάρχει αντιστοίχιση 1 προς 1 μεταξύ ενός οργανισμού Dataverse και ενός λογαριασμού Azure Data Lake Storage. Αφού ένας οργανισμός Dataverse συνδεθεί σε έναν λογαριασμό χώρου αποθήκευσης, δεν μπορεί να συνδεθεί σε άλλο λογαριασμό χώρου αποθήκευσης. Αυτός ο περιορισμός αποτρέπει τη μη συμπλήρωση πολλών λογαριασμών χώρου αποθήκευσης από Dataverse.
- Η κοινή χρήση δεδομένων δεν θα λειτουργήσει αν απαιτείται μια ρύθμιση Azure Private Link για πρόσβαση στο λογαριασμό Azure Data Lake Storage επειδή βρίσκεται πίσω από ένα τείχος προστασίας. Το Dataverse προς το παρόν δεν υποστηρίζει τη σύνδεση σε ιδιωτικά τελικά σημεία μέσω ιδιωτικής σύνδεσης.

### <a name="set-up-powershell"></a>Ρύθμιση PowerShell

Για να εκτελέσετε τις δέσμες ενεργειών PowerShell, πρέπει πρώτα να ρυθμίσετε το PowerShell αντίστοιχα.

1. Εγκαταστήστε την πιο πρόσφατη έκδοση του [Azure Active Directory PowerShell για Graph](/powershell/azure/active-directory/install-adv2).
   1. Στον υπολογιστή σας, επιλέξτε το πλήκτρο των Windows στο πληκτρολόγιό σας και αναζητήστε το **Windows PowerShell** και επιλέξτε **Εκτέλεση ως Διαχειριστής**.
   1. Στο παράθυρο PowerShell που ανοίγει, καταχωρείστε `Install-Module AzureAD`.
2. Εισαγάγετε τρεις μονάδες.
    1. Στο παράθυρο PowerShell, εισέλθετε στο `Install-Module -Name Az.Accounts` και ακολουθήστε τα βήματα.
    1. Επαναλάβετε για τα `Install-Module -Name Az.Resources` και `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Βήματα ρύθμισης παραμέτρων

1. Πραγματοποιήστε λήψη των δύο δεσμών ενεργειών PowerShell που πρέπει να εκτελέσετε από το [αποθετήριο GitHub](https://github.com/trin-msft/byol) του τεχνικού μας.
    1. `CreateSecurityGroups.ps1`
       - Για να εκτελέσετε τη δέσμη ενεργειών PowerShell, χρειάζετε άδειες *διαχειριστή μισθωτών*.
       - Αυτή η δέσμη ενεργειών PowerShell δημιουργεί δύο ομάδες ασφαλείας στη συνδρομή σας στο Azure. Μία για την ομάδα αναγνώστη και μία για την ομάδα συμβαοντα και θα κάνετε την υπηρεσία Microsoft Dataverse κάτοχο αυτών των δύο ομάδων ασφαλείας.
       - Εκτελέστε αυτήν τη δέσμη ενεργειών PowerShell στο Windows PowerShell παρέχοντας το αναγνωριστικό συνδρομής Azure που περιέχει το δικό σας Azure Data Lake Storage. Ανοίξτε τη δέσμη ενεργειών PowerShell σε ένα πρόγραμμα επεξεργασίας για να εξετάσετε τις πρόσθετες πληροφορίες και τη λογική που υλοποιείται.
       - Αποθηκεύστε και τις δύο τιμές αναγνωριστικών ομάδας ασφαλείας που δημιουργούνται από αυτήν τη δέσμη ενεργειών, επειδή θα τις χρησιμοποιήσουμε στη δέσμη ενεργειών `ByolSetup.ps1`.

        > [!NOTE]
        > Η δημιουργία ομάδας ασφαλείας μπορεί να απενεργοποιηθεί στον μισθωτή σας. Σε αυτή την περίπτωση, θα ήταν απαραίτητη μια μη αυτόματη ρύθμιση και ο διαχειριστής του Azure AD θα πρέπει να[ ενεργοποιήσει τη δημιουργία ομάδας ασφαλείας](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Χρειάζεστε δικαιώματα *κατόχου δεδομένων αντικειμένου blob χώρου αποθήκευσης* σε επίπεδο λογαριασμού/κοντέινερ χώρου αποθήκευσης για να εκτελέσετε αυτήν τη δέσμη ενεργειών ή αυτή η δέσμη ενεργειών θα δημιουργήσει μία για εσάς. Η ανάθεση ρόλου σας μπορεί να καταργηθεί με μη αυτόματο τρόπο μετά την επιτυχημένη εκτέλεση της δέσμης ενεργειών.
        - Αυτή η δέσμη ενεργειών PowerShell προσθέτει το απαιτούμενο στοιχείο ελέγχου πρόσβασης βασισμένης σε tole (SHELLAC) Microsoft Dataverse για την υπηρεσία και για οποιεσδήποτε επιχειρηματικές Dataverse εφαρμογές βασισμένες σε αυτές. Επίσης, ενημερώνει τη Λίστα ελέγχου πρόσβασης (ACL) στο κοντέινερ CustomerInsights για τις ομάδες ασφαλείας που δημιουργήθηκαν με τη δέσμη ενεργειών `CreateSecurityGroups.ps1`. Η ομάδα συμβάλλοντος θα έχει *rwx* δικαίωμα και η ομάδα αναγνώστη θα έχει *r-x* δικαιώματα μόνο.
        - Εκτελέστε αυτήν τη δέσμη ενεργειών PowerShell στο Windows PowerShell παρέχοντας το αναγνωριστικό συνδρομής Azure που περιέχει το όνομα λογαριασμού χώρου αποθήκευσης Azure Data Lake Storage, το όνομα ομάδας πόρων και τις τιμές αναγνωριστικών της ομάδας ασφαλείας αναγνώστη και συμβάλλοντος. Ανοίξτε τη δέσμη ενεργειών PowerShell σε ένα πρόγραμμα επεξεργασίας για να εξετάσετε τις πρόσθετες πληροφορίες και τη λογική που υλοποιείται.
        - Αντιγράψτε τη συμβολοσειρά εξόδου αφού ολοκληρωθεί με επιτυχία η εκτέλεση της δέσμης ενεργειών. Η συμβολοσειρά εξόδου έχει την εξής εμφάνιση: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Εισαγάγετε τη συμβολοσειρά εξόδου που αντιγράψατε από παραπάνω στο πεδίο **Αναγνωριστικό δικαιωμάτων** του βήματος ρύθμισης παραμέτρων περιβάλλοντος για το Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Επιλογές ρύθμισης παραμέτρων για να ενεργοποιήσετε την κοινή χρήση δεδομένων από δικό σας Azure Data Lake Storage με το Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Καταργήστε μια υφιστάμενη σύνδεση σε ένα περιβάλλον Dataverse

Όταν συνδέεστε σε ένα Dataverse περιβάλλον, το μήνυμα σφάλματος **Αυτός ο οργανισμός CDS είναι ήδη συνδεδεμένος με μια άλλη παρουσία Customer Insights** σημαίνει ότι το περιβάλλον Dataverse χρησιμοποιείται ήδη σε ένα περιβάλλον Customer Insights. Μπορείτε να καταργήσετε την υπάρχουσα σύνδεση ως καθολικός διαχειριστής στο Dataverse περιβάλλον. Η συμπλήρωση των αλλαγών μπορεί να διαρκέσει μερικές ώρες.

1. Μετάβαση στο [Power Apps](https://make.powerapps.com).
1. Επιλέξτε το περιβάλλον από τον επιλογέα περιβάλλοντος.
1. Μεταβείτε στις **Λύσεις**
1. Καταργήστε ή διαγράψτε τη λύση με το όνομα **Πρόσθετο κάρτας πελάτη Dynamics 365 Customer Insights (έκδοση προεπισκόπησης)**.

Ή

1. Ανοίξτε το Dataverse περιβάλλον σας.
1. Μεταβείτε στις **Ρυθμίσεις για προχωρημένους** > **Λύσεις**.
1. Καταργήστε τη λύση **CustomerInsightsCustomerCard**.

Εάν η κατάργηση της σύνδεσης αποτύχει λόγω εξαρτήσεων, θα πρέπει επίσης να καταργήσετε τις εξαρτήσεις. Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Κατάργηση εξαρτήσεων](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Οντότητες εξόδου

Ορισμένες οντότητες εξόδου από το Customer Insights είναι διαθέσιμες ως πίνακες στο Dataverse. Οι παρακάτω ενότητες περιγράφουν το αναμενόμενο σχήμα αυτών των πινάκων.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Εμπλουτισμός](#enrichment)
- [Πρόβλεψη](#prediction)
- [Ιδιότητα μέλους τμήματος](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Αυτός ο πίνακας περιέχει το ενοποιημένο προφίλ πελάτη από το Customer Insights. Το σχήμα για ένα ενοποιημένο προφίλ πελάτη εξαρτάται από τις οντότητες και τα χαρακτηριστικά που χρησιμοποιούνται στη διεργασία ενοποίησης δεδομένων. Ένα σχήμα προφίλ πελάτη περιέχει συνήθως ένα υποσύνολο των χαρακτηριστικών από τον [Ορισμό κοινού μοντέλου δεδομένων του προφίλ πελάτη](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Ο πίνακας AlternateKey περιέχει τα κλειδιά των οντοτήτων, οι οποίες συμμετέχουν στη διεργασία ενοποίησης.

|Column  |Τύπος  |Περιγραφή  |
|---------|---------|---------|
|DataSourceName    |String         | Όνομα της προέλευσης δεδομένων. Για παράδειγμα: `datasource5`        |
|EntityName        | String        | Το όνομα της οντότητας στο Customer Insights. Για παράδειγμα: `contact1`        |
|AlternateValue    |String         |Το εναλλακτικό αναγνωριστικό που αντιστοιχίζεται στο αναγνωριστικό πελάτη. Παράδειγμα: `cntid_1078`         |
|KeyRing           | Κείμενο πολλών γραμμών        | Τιμή JSON  </br> Δείγμα: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Αναγνωριστικό του ενοποιημένου προφίλ πελάτη.         |
|AlternateKeyId     | GUID         |  Προσδιοριστικό AlternateKey GUID βάσει του msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Δείγμα: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Αυτός ο πίνακας περιέχει δραστηριότητες από χρήστες, οι οποίες είναι διαθέσιμοι στο Customer Insights.

| Column            | Τύπος        | Περιγραφή                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Αναγνωριστικό προφίλ πελάτη                                                                      |
| ActivityId        | String      | Εσωτερικό αναγνωριστικό της δραστηριότητας του πελάτη (πρωτεύον κλειδί)                                       |
| SourceEntityName  | String      | Όνομα της οντότητας προέλευσης                                                                |
| SourceActivityId  | String      | Πρωτεύον κλειδί από την οντότητα προέλευσης                                                       |
| ActivityType      | String      | Σημασιολογικός τύπος δραστηριότητας ή όνομα προσαρμοσμένης δραστηριότητας                                        |
| ActivityTimeStamp | DATETIME    | Χρονική σήμανση δραστηριότητας                                                                      |
| Τίτλος             | String      | Τίτλος ή όνομα της δραστηριότητας                                                               |
| Περιγραφή       | String      | Περιγραφή δραστηριότητας                                                                     |
| Διεύθυνση URL               | String      | Σύνδεση σε εξωτερική διεύθυνση URL ειδικά για τη δραστηριότητα                                         |
| SemanticData      | Συμβολοσειρά JSON | Περιλαμβάνει μια λίστα ζευγών κλειδιών τιμών για πεδία αντιστοίχισης σημασιών ειδικά για τον τύπο δραστηριότητας |
| RangeIndex        | String      | Χρονική σήμανση Unix που χρησιμοποιείται για την ταξινόμηση του χρονοδιαγράμματος δραστηριοτήτων και των ερωτημάτων αποτελεσματικού εύρους |
| mydynci_unifiedactivityid   | GUID | Εσωτερικό αναγνωριστικό της δραστηριότητας του πελάτη (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Αυτός ο πίνακας περιέχει τα δεδομένα εξόδου των ενεργειών που βασίζονται σε χαρακτηριστικό του πελάτη.

| Column             | Τύπος             | Περιγραφή                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Αναγνωριστικό προφίλ πελάτη        |
| Μετρήσεις           | Συμβολοσειρά JSON      | Περιλαμβάνει μια λίστα ζευγών κλειδιών τιμών για το όνομα μέτρησης και τις τιμές για τον δεδομένο πελάτη | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Αναγνωριστικό προφίλ πελάτη |


### <a name="enrichment"></a>Εμπλουτισμός

Ο πίνακας αυτός περιέχει την έξοδο της διεργασίας εμπλουτισμού.

| Column               | Τύπος             |  Περιγραφή                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Αναγνωριστικό προφίλ πελάτη                                 |
| EnrichmentProvider   | String           | Το όνομα παρόχου για τον εμπλουτισμό                                  |
| EnrichmentType       | String           | Τύπος εμπλουτισμού                                      |
| Τιμές               | Συμβολοσειρά JSON      | Λίστα χαρακτηριστικών που δημιουργήθηκε από τη διεργασία εμπλουτισμού |
| msdynci_enrichmentid | GUID             | Προσδιοριστικό GUID που δημιουργήθηκε από το msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Πρόβλεψη

Ο πίνακας αυτός περιέχει την έξοδο των προβλέψεων του μοντέλου.

| Column               | Τύπος        | Περιγραφή                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Αναγνωριστικό προφίλ πελάτη                                  |
| ModelProvider        | String      | Το όνομα παρόχου του μοντέλου                                      |
| Μοντέλο                | String      | Όνομα μοντέλου                                                |
| Τιμές               | Συμβολοσειρά JSON | Λίστα χαρακτηριστικών που δημιουργήθηκε από το μοντέλο |
| msdynci_predictionid | GUID        | Προσδιοριστικό GUID που δημιουργήθηκε από το msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Ιδιότητα μέλους τμήματος

Αυτός ο πίνακας περιέχει τις πληροφορίες ιδιότητας μέλους τμήματος των προφίλ πελατών.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Αναγνωριστικό προφίλ πελάτη        |
| SegmentProvider      | String       | Εφαρμογή που δημοσιεύει τα τμήματα.      |
| SegmentMembershipType | String       | Τύπος του πελάτη για αυτήν την καρτέλα ιδιότητας μέλους τμήματος. Υποστηρίζει πολλούς τύπους, όπως Πελάτης, Επαφή ή Λογαριασμός. Προεπιλογή: Πελάτης  |
| Τμήματα       | Συμβολοσειρά JSON  | Λίστα μοναδικών τμημάτων, στα οποία είναι μέλος το προφίλ πελάτη      |
| msdynci_identifier  | String   | Μοναδικό αναγνωριστικό της καρτέλας ιδιότητας μέλους τμήματος. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Προσδιοριστικό GUID που δημιουργείται από `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
