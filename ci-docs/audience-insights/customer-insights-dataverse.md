---
title: Δεδομένα του Customer Insights στο Microsoft Dataverse
description: Χρήση οντοτήτων Customer Insights ως πίνακες στο Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866934"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Εργασία με δεδομένα Customer Insights στο Microsoft Dataverse

Το Customer Insights παρέχει την επιλογή να είναι διαθέσιμες οι οντότητες εξόδου στο [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Αυτή η ενοποίηση επιτρέπει την εύκολη κοινοποίηση δεδομένων και την προσαρμοσμένη ανάπτυξη μέσω προσέγγισης με χαμηλό περιεχόμενο κώδικα / χωρίς κώδικα. Οι οντότητες εξόδου θα είναι διαθέσιμες ως πίνακες στο Dataverse. Αυτοί οι πίνακες επιτρέπουν σενάρια, όπως [αυτοματοποιημένες ροές μέσω του Power Automate](/power-automate/getting-started), [εφαρμογές που καθορίζονται από μοντέλο](/powerapps/maker/model-driven-apps/) και [εφαρμογές καμβά](/powerapps/maker/canvas-apps/) μέσω του Power Apps. Μπορείτε να χρησιμοποιήσετε τα δεδομένα για οποιαδήποτε άλλη εφαρμογή βασίζεται σε πίνακες Dataverse. Η τρέχουσα υλοποίηση υποστηρίζει κυρίως αναζητήσεις, όπου είναι διαθέσιμη η λήψη δεδομένων από τις διαθέσιμες οντότητες πληροφοριών κοινού για ένα δεδομένο αναγνωριστικό πελάτη.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Επισύναψη περιβάλλοντος Dataverse στο Customer Insights

**Οργανισμοί με υπάρχοντα περιβάλλοντα Dataverse**

Οι οργανισμοί που χρησιμοποιούν ήδη το Dataverse μπορούν [να χρησιμοποιήσουν ένα από τα υπάρχοντα περιβάλλοντα τους Dataverse](create-environment.md) όταν ένας διαχειριστής δημιουργεί πληροφορίες κοινού. Παρέχοντας τη διεύθυνση URL στο περιβάλλον Dataverse, επισυνάπτεται στο νέο περιβάλλον πληροφοριών κοινού. Για να εξασφαλιστεί η καλύτερη δυνατή απόδοση, τα περιβάλλοντα Customer Insights και Dataverse πρέπει να φιλοξενούνται στην ίδια περιοχή.

**Νέος οργανισμός**

Εάν δημιουργήσετε έναν νέο οργανισμό κατά τη ρύθμιση του Customer Insights, θα λάβετε αυτόματα ένα νέο περιβάλλον Dataverse.

> [!NOTE]
> Εάν οι οργανισμοί σας χρησιμοποιούν ήδη το Dataverse στον μισθωτή τους, είναι σημαντικό να θυμάστε ότι η [Δημιουργία περιβάλλοντος Dataverse ελέγχεται από έναν διαχειριστή](/power-platform/admin/control-environment-creation.md). Για παράδειγμα, αν δημιουργείτε ένα νέο περιβάλλον πληροφοριών κοινού με τον λογαριασμό του οργανισμού σας και ο διαχειριστής έχει απενεργοποιήσει τη δημιουργία δοκιμαστικών περιβαλλόντων Dataverse για όλους εκτός από τους διαχειριστές, δεν μπορείτε να δημιουργήσετε ένα νέο δοκιμαστικό περιβάλλον.
> 
> Τα δοκιμαστικά περιβάλλοντα Dataverse που δημιουργούνται στο Customer Insights έχουν 3 GB χώρου αποθήκευσης, τα οποία δεν θα υπολογίζονται ως προς τη συνολική χωρητικότητα που δικαιούται ο μισθωτής. Οι συνδρομές επί πληρωμή λαμβάνουν δικαίωμα Dataverse 15 GB για τη βάση δεδομένων και 20 GB για χώρο αποθήκευσης αρχείων.

## <a name="output-entities"></a>Οντότητες εξόδου

Ορισμένες οντότητες εξόδου από τις πληροφορίες κοινού είναι διαθέσιμες ως πίνακες στο Dataverse. Οι παρακάτω ενότητες περιγράφουν το αναμενόμενο σχήμα αυτών των πινάκων.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Εμπλουτισμός](#enrichment)
- [Πρόβλεψη](#prediction)
- [Ιδιότητα μέλους τμήματος](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Αυτός ο πίνακας περιέχει το ενοποιημένο προφίλ πελάτη από το Customer Insights. Το σχήμα για ένα ενοποιημένο προφίλ πελάτη εξαρτάται από τις οντότητες και τα χαρακτηριστικά που χρησιμοποιούνται στη διεργασία συγχώνευσης. Ένα σχήμα προφίλ πελάτη περιέχει συνήθως ένα υποσύνολο των χαρακτηριστικών από τον [Ορισμό κοινού μοντέλου δεδομένων του προφίλ πελάτη](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Ο πίνακας AlternateKey περιέχει τα κλειδιά των οντοτήτων, οι οποίες συμμετέχουν στη διεργασία ενοποίησης.

|Column  |Τύπος  |Περιγραφή  |
|---------|---------|---------|
|DataSourceName    |String         | Όνομα της προέλευσης δεδομένων. Για παράδειγμα: `datasource5`        |
|EntityName        | String        | Το όνομα της οντότητας στις πληροφορίες κοινού. Για παράδειγμα: `contact1`        |
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
| SegmentProvider      | String       | Εφαρμογή που δημοσιεύει τα τμήματα. Προεπιλογή: πληροφορίες κοινού         |
| SegmentMembershipType | String       | Τύπος του πελάτη για αυτήν την καρτέλα ιδιότητας μέλους τμήματος. Υποστηρίζει πολλούς τύπους, όπως Πελάτης, Επαφή ή Λογαριασμός. Προεπιλογή: Πελάτης  |
| Τμήματα       | Συμβολοσειρά JSON  | Λίστα μοναδικών τμημάτων, στα οποία είναι μέλος το προφίλ πελάτη      |
| msdynci_identifier  | String   | Μοναδικό αναγνωριστικό της καρτέλας ιδιότητας μέλους τμήματος. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Προσδιοριστικό GUID που δημιουργείται από `msdynci_identifier`          |
