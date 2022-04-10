---
title: Έλεγχος Dynamics 365 Customer Insights με παρακολούθηση Azure
description: Μάθετε πώς να στέλνετε αρχεία καταγραφής στην Παρακολούθηση Microsoft Azure.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523669"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Καταχώρηση προώθησης στο Dynamics 365 Customer Insights με Παρακολούθηση Azure (Έκδοση προεπισκόπησης)

Το Dynamics 365 Customer Insights παρέχει μια άμεση ενοποίηση με την Παρακολούθηση Azure. Τα αρχεία καταγραφής πόρων Παρακολούθησης Azure σάς επιτρέπουν να παρακολουθείτε και να στέλνετε αρχεία καταγραφής στον [Χώρο αποθήκευσης Azure](https://azure.microsoft.com/services/storage/), στην [Ανάλυση αρχείων καταγραφής Azure](/azure/azure-monitor/logs/log-analytics-overview) ή να τα διοχετεύετε στα [Κέντρα συμβάντων Azure](https://azure.microsoft.com/services/event-hubs/).

Το Customer Insights αποστέλλει τα ακόλουθα αρχεία καταγραφής συμβάντων:

- **Συμβάντα ελέγχου**
  - **APIEvent** - επιτρέπει την παρακολούθηση αλλαγών που γίνεται μέσω του περιβάλλοντος εργασίας χρήστη Dynamics 365 Customer Insights.
- **Συμβάντα λειτουργίας**
  - **WorkflowEvent** - Η ροή εργασιών επιτρέπει σε κάποιον να ρυθμίσει [προελεύσεις δεδομένων](data-sources.md), [να ενοποιήσει](data-unification.md) και [να εμπλουτίσει](enrichment-hub.md) και, τέλος, [να εξαγάγει](export-destinations.md) δεδομένα σε άλλα συστήματα. Όλα αυτά τα βήματα μπορούν να γίνουν μεμονωμένα (π.χ. να ενεργοποιούν μια μεμονωμένη εξαγωγή) ή να ενορχηστρωμένα (π.χ. ανανέωση δεδομένων από πηγές δεδομένων που ενεργοποιούν τη διεργασία ενοποίηση, η οποία θα τραβήξει επιπλέον εμπλουτισμούς και αφού γίνει θα εξαγάγει τα δεδομένα σε άλλο σύστημα). Για περισσότερες λεπτομέρειες, ανατρέξτε στο [Σχήμα WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - όλες οι κλήσεις API στην παρουσία των πελατών στο Dynamics 365 Customer Insights. Για περισσότερες λεπτομέρειες, ανατρέξτε στο [Σχήμα APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Ρύθμιση των διαγνωστικών ρυθμίσεων

### <a name="prerequisites"></a>Προϋποθέσεις

Για να ρυθμίσετε διαγνώσεις στο Customer Insights, πρέπει να πληρούνται οι παρακάτω προϋποθέσεις:

- Έχετε ενεργή [συνδρομή στο Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Έχετε δικαιώματα [Διαχειριστή](permissions.md#admin) στο Customer Insights.
- Έχετε το ρόλο **Συμμετέχοντα** και **Διαχειριστή πρόσβασης χρήστη** στον πόρο προορισμού στο Azure. Ο πόρος μπορεί να είναι ένας λογαριασμός Υπηρεσίας αποθήκευσης Azure, ένα Κέντρο συμβάντων Azure ή ένας χώρος εργασίας ανάλυσης αρχείων καταγραφής Azure. Για περισσότερες πληροφορίες, δείτε [Προσθήκη ή κατάργηση αντιστοιχίσεων ρόλων Azure χρησιμοποιώντας την πύλη Azure](/azure/role-based-access-control/role-assignments-portal).
- [Απαιτήσεις προορισμού](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) για την Υπηρεσία αποθήκευσης Azure, το Κέντρο συμβάντων Azure ή την Ανάλυση αρχείου καταγραφής Azure πληρούνται.
- Έχετε τουλάχιστον τον ρόλο **Αναγνώστης** στην ομάδα πόρων στην οποία ανήκει ο πόρος.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Ρύθμιση διαγνωστικών με την Παρακολούθηση Azure

1. Στο Customer Insights, επιλέξτε **Σύστημα** > **Διάγνωση** για να δείτε τους προορισμούς διαγνωστικών που έχουν ρυθμιστεί σε αυτήν την παρουσία.

1. Επιλέξτε **Προσθήκη προορισμού**.

   > [!div class="mx-imgBorder"]
   > ![Σύνδεση διαγνωστικού ελέγχου](media/diagnostics-pane.png "Σύνδεση διαγνωστικού ελέγχου")

1. Δώστε ένα όνομα στο πεδίο **Όνομα για προορισμού διαγνωστικών ελέγχων**.

1. Επιλέξτε τον **Μισθωτή** της συνδρομής Azure με τον πόρο προορισμού και επιλέξτε **Σύνδεση**.

1. Επιλέξτε τον **Τύπο πόρου** (Λογαριασμός υπηρεσίας αποθήκευσης, Κέντρο συμβάντων ή ανάλυση αρχείου καταγραφής).

1. Επιλέξτε τη **Συνδρομή** για τον πόρο προορισμού.

1. Επιλέξτε την **Ομάδα πόρων** για τον πόρο προορισμού.

1. Επιλέξτε τον **Πόρο**.

1. Επιβεβαιώστε τη δήλωση **προστασίας προσωπικών δεδομένων και συμμόρφωσης**.

1. Επιλέξτε **Σύνδεση στο σύστημα** για να συνδεθείτε στον πόρο προορισμού. Τα αρχεία καταγραφής αρχίζουν να εμφανίζονται στον προορισμό μετά από 15 λεπτά, εάν το API χρησιμοποιείται και δημιουργεί συμβάντα.

### <a name="remove-a-destination"></a>Κατάργηση προορισμού

1. Μεταβείτε στο **Σύστημα** > **Διαγνωστικός έλεγχος**.

1. Επιλέξτε τον προορισμό των διαγνωστικών ελέγχων στη λίστα.

1. Στη στήλη **Ενέργειες**, επιλέξτε το εικονίδιο **Διαγραφή**.

1. Επιβεβαιώστε τη διαγραφή για διακοπή της προώθησης του αρχείου καταγραφής. Ο πόρος στη συνδρομή Azure δεν θα διαγραφεί. Μπορείτε να επιλέξετε τη σύνδεση στη στήλη **Ενέργειες** για να ανοίξετε την πύλη Azure για τον επιλεγμένο πόρο και να τον διαγράψετε εκεί.

## <a name="log-categories-and-event-schemas"></a>Κατηγορίες καταγραφής και σχήματα συμβάντων

Αυτήν τη στιγμή [τα συμβάντα API](apis.md) και τα συμβάντα ροής εργασιών υποστηρίοζνται και εφαρμόζονται οι παρακάτω κατηγορίες και σχήματα.
Το σχήμα αρχείου καταγραφής ακολουθεί το [κοινό σχήμα της Παρακολούθησης Azure](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Κατηγορίες

Το Customer Insights παρέχει δύο κατηγορίες:

- **Συμβάντα ελέγχου**: [Συμβάντα API](#api-event-schema) για παρακολούθηση των αλλαγών στη ρύθμιση παραμέτρων της υπηρεσίας. ΟΙ λειτουργίες `POST|PUT|DELETE|PATCH` πάνε σε αυτήν την κατηγορία.
- **Λειτουργικά συμβάντα**: [Συμβάντα API](#api-event-schema) ή [συμβάντα ροής εργασιών](#workflow-event-schema) που δημιουργούνται κατά τη χρήση της υπηρεσίας.  Για παράδειγμα, αιτήσεις `GET` ή συμβάντα εκτέλεσης μιας ροής εργασιών.

## <a name="configuration-on-the-destination-resource"></a>Ρύθμιση παραμέτρων στον πόρο προορισμού

Με βάση την επιλογή σας στον τύπο πόρου, θα εφαρμοστούν αυτόματα τα παρακάτω βήματα:

### <a name="storage-account"></a>Storage account

Η αρχή υπηρεσίας Customer Insights λαμβάνει το δικαίωμα **συμμετέχων λογαριασμού υπηρεσίας αποθήκευσης** στον επιλεγμένο πόρο και δημιουργεί δύο κοντέινερ κάτω από τον επιλεγμένο χώρο ονομάτων:

- `insight-logs-audit` που περιέχει **συμβάντα ελέγχου**
- `insight-logs-operational` που περιέχει **λειτουργικά συμβάντα**

### <a name="event-hub"></a>Κέντρο συμβάντων

Η αρχή υπηρεσίας Customer Insights λαμβάνει το δικαίωμα **κάτοχος δεδομένων κέντρων συμβάντων Azure** στον πόρο και θα δημιουργήσει δύο κέντρων συμβάτων κάτω από τον επιλεγμένο χώρο ονομάτων:

- `insight-logs-audit` που περιέχει **συμβάντα ελέγχου**
- `insight-logs-operational` που περιέχει **λειτουργικά συμβάντα**

### <a name="log-analytics"></a>Ανάλυση αρχείων καταγραφής

Η αρχή υπηρεσίας Customer Insights λαμβάνει το δικαίωμα **συμμετέχων ανάλυσης καταγραφής** στον πόρο. Τα αρχεία καταγραφής θα είναι διαθέσιμα στην περιοχή **Αρχεία καταγραφής** > **Πίνακες** > **Διαχείριση αρχείων καταγραφής** στον επιλεγμένο χώρο εργασίας ανάλυσης αρχείων καταγραφής. Αναπτύξτε τη λύση **Διαχείριση αρχείων καταγραφής** και εντοπίστε τους πίνακες `CIEventsAudit` και `CIEventsOperational`.

- `CIEventsAudit` που περιέχει **συμβάντα ελέγχου**
- `CIEventsOperational` που περιέχει **λειτουργικά συμβάντα**

Στο παράθυρο **Ερωτήματα**, αναπτύξτε τη λύση **Έλεγχος** και εντοπίστε το παράδειγμα ερωτημάτων που παρέχονται μέσω αναζήτησης για `CIEvents`.

## <a name="event-schemas"></a>Σχήματα συμβάντος

Τα συμβάντα API και τα συμβάντα ροής εργασίας έχουν μια κοινή δομή και λεπτομέρειες σχετικά με αυτές τις διαφορές, ανατρέξτε στο [σχήμα συμβάντος API](#api-event-schema) ή στο [σχήμα συμβάντος ροής εργασίας](#workflow-event-schema).

### <a name="api-event-schema"></a>Σχήμα συμβάντος API

| Πεδίο             | DataType  | Απαιτείται/προαιρετικό | Description       | Παράδειγμα        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Χρονική σήμανση | Απαραίτητο          | Χρονική σήμανση του συμβάντος (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Απαραίτητο          | ResourceId της παρουσίας που εξέπεμψε το συμβάν         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Απαραίτητο          | Το όνομα της λειτουργίας που αντιπροσωπεύει αυτό το συμβάν.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Απαραίτητο          | Κατηγορία αρχείου καταγραφής του συμβάντος. Είτε `Operational` ή `Audit`. Σε όλες οι αιτήσεις HTTP POST/PUT/PATCH/DELETE έχει προστεθεί ετικέτα `Audit` και όλα τα υπόλοιπα `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Απαραίτητο          | Κατάσταση του συμβάντος. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Προαιρετικές          | Κατάσταση αποτελέσματος του συμβάντος. Εάν η λειτουργία αντιστοιχεί σε μια κλήση REST API, είναι ο κωδικός κατάστασης HTTP.        | `200`             |
| `durationMs`      | Μεγάλου μήκους      | Προαιρετικές          | Διάρκεια της λειτουργίας σε χιλιοστά του δευτερολέπτου.     | `133`     |
| `callerIpAddress` | String    | Προαιρετικές          | Διεύθυνση IP καλούντα, εάν η λειτουργία αντιστοιχεί σε μια κλήση API που προέρχεται από μια δημοσίως διαθέσιμη διεύθυνση IP.                                                 | `144.318.99.233`         |
| `identity`        | String    | Προαιρετικές          | Αντικείμενο JSON που περιγράφει την ταυτότητα του χρήστη ή της εφαρμογής που έκανε τη λειτουργία.       | Ανατρέξτε στην ενότητα [Ταυτότητα](#identity-schema).     |  
| `properties`      | String    | Προαιρετικές          | Αντικείμενο JSON με περισσότερες ιδιότητες για τη συγκεκριμένη κατηγορία συμβάντων.      | Δείτε την ενότητα [Ιδιότητες](#api-properties-schema).    |
| `level`           | String    | Απαραίτητο          | Επίπεδο ασφάλειας του συμβάντος.    | `Informational`, `Warning`, `Error` ή `Critical`.           |
| `uri`             | String    | Προαιρετικές          | URI απόλυτης αίτησης.    |               |

#### <a name="identity-schema"></a>Σχήμα ταυτότητας

Το αντικείμενο JSON `identity` έχει την ακόλουθη δομή

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Πεδίο                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Ανατεθείς ρόλος για τον χρήστη ή την εφαρμογή. Για περισσότερες πληροφορίες, ανατρέξτε στα [δικαιώματα χρήστη](permissions.md).                                     |
| `Authorization.RequiredRoles` | Απαιτούμενοι ρόλοι για να γίνει η λειτουργία. Ο ρόλος `Admin` επιτρέπεται σε για να γίνου όλες οι λειτουργίες.                                                    |
| `Claims`                      | Διεκδικήσεις του διακριτικού web JSON (JWT) χρήστη ή εφαρμογής. Οι ιδιότητες της απαίτησης διαφέρουν ανάλογα με τον οργανισμό και τη ρύθμιση παραμέτρων Azure Active Directory. |

#### <a name="api-properties-schema"></a>Σχήμα ιδιοτήτων API

[Τα συμβάντα API](apis.md) έχουν τις ακόλουθες ιδιότητες.

| Πεδίο                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Πάντα `ApiEvent`, σημειώνοντας το συμβάν αρχείου καταγραφής ως συμβάν API.                                                                 |
| `properties.userAgent`       | Ο εκπρόσωπος του προγράμματος περιήγησης που αποστέλλει την αίτηση ή `unknown`.                                                                        |
| `properties.method`          | Μέθοδος HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Σχετική διαδρομή της αίτησης.                                                                                          |
| `properties.origin`          | URI που υποδεικνύει από πού προέρχεται ένα fetch ή `unknown`.                                                                  |
| `properties.operationStatus` | `Success` για κωδικό κατάστασης HTTP < 400 <br> `ClientError` για κωδικό κατάτσασης HTTP < 500 <br> `Error` για κατάσταση HTTP >= 500 |
| `properties.tenantId`        | Αναγνωριστικό οργανισμού                                                                                                        |
| `properties.tenantName`      | Όνομα του οργανισμού.                                                                                              |
| `properties.callerObjectId`  | ObjectId Azure Active Directory του καλούντα.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Σχήμα συμβάντος ροής εργασιών

Η ροή εργασιών περιέχει πολλά βήματα. [Κατάργηση προελεύσεων δεδομένων](data-sources.md), [ενοποίηση](data-unification.md), [εμπλουτισμός](enrichment-hub.md) και [εξαγωγή](export-destinations.md) δεδομένων. Όλα αυτά τα βήματα μπορούν να εκτελούνται μεμονωμένα ή να ενορχηστρωμένα με τις ακόλουθες διαδικασίες. 

#### <a name="operation-types"></a>Τύποι λειτουργιών

| OperationType     | Ομάδα                                     |
| ----------------- | ----------------------------------------- |
| Κατανάλωση         | [Προελεύσεις δεδομένων](data-sources.md)           |
| DataPreparation   | [Προελεύσεις δεδομένων](data-sources.md)           |
| Αντιστ.               | [Ενοποίηση δεδομένων](data-unification.md)   |
| Match             | [Ενοποίηση δεδομένων](data-unification.md)   |
| Συγχώνευση             | [Ενοποίηση δεδομένων](data-unification.md)   |
| ProfileStore      | [Προφίλ πελατών](customer-profiles.md) |
| Αναζήτηση            | [Προφίλ πελατών](customer-profiles.md) |
| Δραστηρ.          | [Δραστηριότητες](activities.md)                  |
| AttributeMeasures | [Τμήματα και μετρήσεις](segments.md)      |
| EntityMeasures    | [Τμήματα και μετρήσεις](segments.md)      |
| Μετρήσεις          | [Τμήματα και μετρήσεις](segments.md)      |
| Κατακερματισμός      | [Τμήματα και μετρήσεις](segments.md)      |
| Εμπλουτισμός        | [Εμπλουτισμός](enrichment-hub.md)                                          |
| Ευφυΐα      | [Προβλέψεις](predictions-overview.md)                                          |
| AiBuilder         | [Προβλέψεις](predictions-overview.md)                                          |
| Δεδομενικές πληροφορίες          | [Προβλέψεις](predictions-overview.md)                                          |
| Export            | [Εξαγωγές](export-destinations.md)                                          |
| ModelManagement   | [Προβλέψεις](custom-models.md)                                           |
| Σχέση      | [Ενοποίηση δεδομένων](relationships.md)                                           |

#### <a name="field-description"></a>Περιγραφή πεδίου

| Πεδίο           | DataType  | Απαιτείται/προαιρετικό | Description                                                                                                                                                   | Παράδειγμα                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Χρονική σήμανση | Απαραίτητο          | Χρονική σήμανση του συμβάντος (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Απαραίτητο          | ResourceId της παρουσίας που εξέπεμψε το συμβάν.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Απαραίτητο          | Το όνομα της λειτουργίας που αντιπροσωπεύει αυτό το συμβάν. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Ανατρέξτε στο [Τύποι κειτουργίας](#operation-types) για αναφορά. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Απαραίτητο          | Κατηγορία αρχείου καταγραφής του συμβάντος. Πάντα `Operational` για συμβάντα ροής εργασιών                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Απαραίτητο          | Κατάσταση του συμβάντος. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Μεγάλου μήκους      | Προαιρετικές          | Διάρκεια της λειτουργίας σε χιλιοστά του δευτερολέπτου.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Προαιρετικές          | Αντικείμενο JSON με περισσότερες ιδιότητες για τη συγκεκριμένη κατηγορία συμβάντων.                                                                                        | Δείτε δευτερεύουσα ενότητα [Ιδιότητες ροής εργασίας](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Απαραίτητο          | Επίπεδο ασφάλειας του συμβάντος.                                                                                                                                  | `Informational`, `Warning`, ή `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Σχήμα ιδιοτήτων ροής εργασίας

Τα συμβάντα ροής εργασίας έχουν τις ακόλουθες ιδιότητες.

| Πεδίο              | Workflow | Κλείσιμο εργασίας | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ναι      | Ναι  | Πάντα `WorkflowEvent`, σημειώνοντας το συμβάν ως συμβάν ροής εργασίας.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ναι      | Ναι  | Αναγνωριστικό της εκτέλεσης ροής εργασιών. Όλα τα συμβάντα ροής εργασιών και εργασιών εντός της εκτέλεσης ροής εργασιών έχουν το ίδιο `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ναι      | Ναι  | Αναγνωριστικό της λειτουργίας, ανατρέξτε στην ενότητα [Τύποι λειτουργίας](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ναι      | No   | Μόνο ροή εργασιών. Αριθμός των εργασιών που ενεργοποιεί η ροή εργασιών.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ναι      | No   | Προαιρετικό. Μόνο συμβάντα ροής εργασίας. Το Azure Active Directory [objectId του χρήστη](/azure/marketplace/find-tenant-object-id#find-user-object-id) που ενεργοποίησε τη ροή εργασιών, ανατρέξτε επίσης στο `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ναι      | No   | ανανέωση `full` ή `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ναι      | No   | `OnDemand` ή `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ναι      | No   | `Running` ή  `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ναι      | Ναι  | Χρονική σήμανση UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ναι      | Ναι  | Χρονική σήμανση UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ναι      | Ναι  | Χρονική σήμανση UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ναι      | Ναι  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ναι  | - Για OperationType = `Export`, το αναγνωριστικό είναι το guid της ρύθμισης παραμέτρων εξαγωγής. <br> - Για OperationType = `Enrichment`, είναι το guid του εμπλουτισμού <br> - Για OperationType `Measures`και `Segmentation`, το αναγνωριστικό είναι το όνομα της οντότητας. |
| `properties.friendlyName`                    | No       | Ναι  | Το φιλικό για το χρήστη όνομα της εξαγωγής ή η οντότητα που επεξεργάζεται.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ναι  | Προαιρετικό. Μήνυμα σφάλματος με περισσότερες λεπτομέρειες.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ναι  | Προαιρετικό. Μόνο για OperationType `Export`. Προσδιορίζει τον τύπο της εξαγωγής. Για περισσότερες πληροφορίες, ανατρέξτε στην [επισκόπηση των προορισμών εξαγωγής](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ναι  | Προαιρετικό. Μόνο για OperationType `Export`. Περιέχει μια λίστα ρυθμισμένων οντοτήτων στην εξαγωγή.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ναι  | Προαιρετικό. Μόνο για OperationType `Export`. Αναλυτικό μήνυμα για την εξαγωγή.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ναι  | Προαιρετικό. Μόνο για OperationType `Segmentation`. Υποδεικνύει το συνολικό αριθμό μελών που έχει το τμήμα.                                                                                                                                                    |
