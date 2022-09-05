---
title: Παραδείγματα ερωτήματος Odata για API του Customer Insights
description: Συχνά χρησιμοποιούνται παραδείγματα για το Πρωτόκολλο ανοιχτών δεδομένων (OData) για την υποβολή ερωτημάτων στα API του Customer Insights για τον έλεγχο δεδομένων.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387202"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Παραδείγματα ερωτήματος Odata για API του Customer Insights

Το Πρωτόκολλο ανοιχτών δεδομένων (OData) είναι ένα πρωτόκολλο πρόσβασης σε δεδομένα, το οποίο είναι ενσωματωμένο σε κύρια πρωτόκολλα, όπως το HTTP. Χρησιμοποιεί συχνά αποδεκτές μεθοδολογίες όπως το REST για το web. Υπάρχουν διάφορων ειδών βιβλιοθήκες και εργαλεία που μπορούν να χρησιμοποιηθούν για την κατανάλωση των υπηρεσιών OData.

Δείτε ορισμένα παραδείγματα ερωτημάτων που ζητούνται συχνά και σας βοηθούν να δημιουργήσετε τις δικές σας υλοποιήσεις με βάση τα [API του Customer Insights](apis.md).

Τροποποιήστε τα δείγματα ερωτημάτων για να λειτουργούν στα περιβάλλοντα προορισμού:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` όπου {instanceId} βρίσκεται το GUID του περιβάλλοντος Customer Insights που θέλετε να υποβάλετε ερώτημα. Η [λειτουργία ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) σάς επιτρέπει να βρείτε το {InstanceId} στο οποίο έχετε πρόσβαση.
- {CID}: GUID μιας ενοποιημένης καρτέλας πελάτη. Παράδειγμα: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Αναγνωριστικό του πρωτεύοντος κλειδιού μιας καρτέλας πελάτη σε μια προέλευση δεδομένων. Παράδειγμα: `CNTID_1002`
- {DSname}: Συμβολοσειρά με το όνομα οντότητας μιας προέλευσης δεδομένων που αποκτά πρόσβαση στο Customer Insights. Παράδειγμα: `Website_contacts`.
- {SegmentName}: Συμβολοσειρά με το όνομα της οντότητας εξόδου ενός τμήματος στο Customer Insights. Παράδειγμα: `Male_under_40`.

## <a name="customer"></a>Πελάτη

Ερωτήματα-δείγματα για την οντότητα *Πελάτης*.

|Τύπος ερωτήματος |Παράδειγμα  | Σημείωμα  |
|---------|---------|---------|
|Μεμονωμένο αναγνωριστικό πελάτη     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Εναλλακτικό κλειδί    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Τα εναλλακτικά κλειδιά διατηρούνται στην ενοποιημένη οντότητα πελάτη       |
|Επιλέξτε   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|σε    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Εναλλακτικό κλειδί + σε   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Αναζήτηση  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Επιστρέφει τα 10 πρώτα αποτελέσματα για μια συμβολοσειρά αναζήτησης      |
|Ιδιότητα μέλους τμήματος  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Επιστρέφει έναν προκαθορισμένο αριθμό γραμμών από την οντότητα τμηματοποίησης      |
|Τμήμα ιδιότητας μέλους για έναν πελάτη | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Επιστρέφει το προφίλ πελάτη εάν είναι μέλος του συγκεκριμένου τμήματος     |

## <a name="unified-activity"></a>Ενοποιημένη δραστηριότητα

Ερωτήματα-δείγματα για την οντότητα *UnifiedActivity*.

|Τύπος ερωτήματος |Παράδειγμα  | Σημείωμα  |
|---------|---------|---------|
|Δραστηριότητα του CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Παραθέτει δραστηριότητες ενός συγκεκριμένου προφίλ πελατών |
|Χρονικό πλαίσιο δραστηριότητας    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Δραστηριότητες ενός προφίλ πελάτη σε ένα χρονικό πλαίσιο       |
|Τύπος δραστηριότητας    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Δραστηριότητα κατά εμφανιζόμενο όνομα     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Ταξινόμηση δραστηριοτήτων    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Αύξουσα ή φθίνουσα ταξινόμηση δραστηριοτήτων       |
|Ανάπτυξη δραστηριότητας από ιδιότητα μέλους τμήματος  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Άλλα παραδείγματα

Δείγματα ερωτημάτων για άλλες οντότητες.

|Τύπος ερωτήματος |Παράδειγμα  | Σημείωμα  |
|---------|---------|---------|
|Μετρήσεις του CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Εμπλουτισμένες επωνυμίες του CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Εμπλουτισμένα ενδιαφερόντα του CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Όρος In + Ανάπτυξη     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Ερωτήματα Odata που δεν υποστηρίζονται

Τα ακόλουθα ερωτήματα δεν υποστηρίζονται από το Customer Insights:

- `$filter` στις οντότητες προέλευσης που έχουν ληφθεί. Μπορείτε να εκτελέσετε ερωτήματα $filter σε οντότητες συστήματος που δημιουργεί το Customer Insights.
- `$expand` από ένα ερώτημα `$search`. Παράδειγμα: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` από `$select` εάν έχει επιλεγεί μόνο ένα υποσύνολο χαρακτηριστικών. Παράδειγμα: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` εμπλουτισμένες εκδηλώσεις ενδιαφέροντος ή εμπορικής επωνυμίας για ένα δεδομένο πελάτη. Παράδειγμα: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Οντότητες εξόδου μοντέλου πρόβλεψης ερωτήματος μέσω εναλλακτικού κλειδιού. Παράδειγμα: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
