---
title: Αιτήματα δικαιωμάτων υποκειμένου δεδομένων (DSR) βάσει του ΓΚΠΔ | Microsoft Docs
description: Απαντήστε σε αιτήσεις υποκειμένων δεδομένων για τη δυνατότητα πληροφοριών κοινού του Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350269"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Αιτήματα δικαιωμάτων υποκειμένου δεδομένων (DSR) βάσει του ΓΚΠΔ

Ο Γενικός Κανονισμός για την προστασία δεδομένων (ΓΚΠΔ) της Ευρωπαϊκής ένωσης τέθηκε σε ισχύ στις 25 Μαΐου 2018. Παρέχει σημαντικά δικαιώματα στα άτομα σχετικά με τα δεδομένα τους. Ο ΓΚΠΔ αφορά στην προστασία και την εφαρμογή των δικαιωμάτων απορρήτου των ατόμων. Μπορείτε να διαβάσετε περισσότερα σχετικά με τη δέσμευση ασφάλειας και τη συμμόρφωση της Microsoft στο [Κέντρο αξιοπιστίας της Microsoft](https://www.microsoft.com/trust-center).

Δεσμευόμαστε να βοηθήσουμε τους πελάτες μας να ανταποκριθούν στις απαιτήσεις του ΓΚΠΔ. Περιλαμβάνει το δικαίωμα διαγραφής και εξαγωγής δεδομένων που περιλαμβάνουν προσωπικές πληροφορίες, όπως αναγνωριστικά χρηστών, αριθμούς τηλεφώνου και διευθύνσεις ηλεκτρονικού ταχυδρομείου. Οι διαχειριστές μπορούν να υλοποιούν αιτήματα χρηστών για διαγραφή ή εξαγωγή προσωπικών δεδομένων.

## <a name="audience-insights"></a>Πληροφορίες κοινού

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Απάντηση σε αιτήσεις διαγραφής υποκειμένων δεδομένων GDPR για τη δυνατότητα πληροφοριών κοινού του Dynamics 365 Customer Insights

Το "δικαίωμα απαλοιφής" με την κατάργηση προσωπικών δεδομένων από τα δεδομένα πελάτη μιας εταιρείας αποτελεί βασική προστασία στον Γενικό κανονισμό για την προστασία δεδομένων (ΓΚΠΔ). Η κατάργηση προσωπικών δεδομένων περιλαμβάνει την κατάργηση όλων των προσωπικών δεδομένων και των αρχείων καταγραφής που δημιουργούνται από το σύστημα, εκτός από τις πληροφορίες του αρχείου καταγραφής ελέγχου.

#### <a name="manage-data-subject-delete-requests"></a>Διαχείριση αιτήσεων διαγραφής θεμάτων δεδομένων

Οι πληροφορίες κοινού προσφέρουν τις ακόλουθες εμπειρίες εντός του προϊόντος για τη διαγραφή προσωπικών δεδομένων για ένα συγκεκριμένο πελάτη ή χρήστη:

- **Διαχείριση αιτήσεων διαγραφής για δεδομένα πελατών**: τα δεδομένα πελατών στο Customer Insights λαμβάνονται από αρχικές πηγές δεδομένων εξωτερικές του Customer Insights. Όλες οι αιτήσεις διαγραφής ΓΚΠΔ πρέπει να εκτελεστούν στην αρχική πηγή δεδομένων.
- **Διαχείριση αιτήσεων διαγραφής για δεδομένα χρήστη του Customer Insights**: τα δεδομένα για χρήστες δημιουργούνται από το Customer Insights. Όλες οι αιτήσεις διαγραφής ΓΚΠΔ πρέπει να εκτελεστούν στο Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Διαχείριση αιτήσεων για διαγραφή δεδομένων πελατών

Ένας διαχειριστής του Customer Insights μπορεί να ακολουθήσει αυτά τα βήματα για να καταργήσει τα δεδομένα πελατών που διαγράφηκαν στην προέλευση δεδομένων:

1. Συνδεθείτε στο Dynamics 365 Customer Insights.
2. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Προελεύσεις δεδομένων**
3. Για κάθε προέλευση δεδομένων στη λίστα που περιέχει δεδομένα πελατών που έχουν διαγραφεί:
   1. Επιλέξτε (...) και μετά επιλέξτε **Ανανέωση**.
   2. Δείτε την κατάσταση της προέλευσης δεδομένων στο **Κατάσταση**. Το σημάδι ελέγχου σημαίνει ότι η ανανέωση ήταν επιτυχής. Το προειδοποιητικό τρίγωνο σημαίνει ότι κάτι δεν πήγε καλά. Εάν εμφανίζεται προειδοποιητικό τρίγωνο, επικοινωνήστε με το D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Διαχείριση αιτήσεων διαγραφής ΓΚΠΔ για δεδομένα πελατών.](audience-insights/media/gdpr-data-sources.png "Διαχείριση αιτήσεων διαγραφής ΓΚΠΔ για δεδομένα πελατών")

##### <a name="manage-delete-requests-for-user-data"></a>Διαχείριση αιτήσεων διαγραφής για δεδομένα χρηστών

Ένας διαχειριστής του Customer Insights μπορεί να ακολουθήσει αυτά τα βήματα για να διαγράψει τα δεδομένα χρηστών Customer Insights:

1. Συνδεθείτε στο Dynamics 365 Customer Insights.
2. Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Διαχειριστής** > **Δικαιώματα**.
3. Επιλέξτε το πλαίσιο ελέγχου για τον χρήστη που θέλετε να διαγράψετε.
4. Επιλέξτε **Κατάργηση**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Απόκριση σε αιτήσεις εξαγωγής υποκειμένων δεδομένων ΓΚΠΔ

Στο πλαίσιο της δέσμευσής μας να συνεργαστούμε μαζί σας για το ταξίδι σας στο Γενικό Κανονισμό για την Προστασία Δεδομένων (ΓΚΠΔ), έχουμε αναπτύξει έγγραφα που θα σας βοηθήσουν να προετοιμαστείτε. Αυτή η τεκμηρίωση περιγράφει τα βήματα που μπορείτε να λάβετε σήμερα για να υποστηρίξετε τη συμμόρφωση με τον ΓΚΠΔ όταν χρησιμοποιείτε πληροφορίες κοινού.

#### <a name="manage-export-and-view-requests"></a>Διαχείριση αιτήσεων εξαγωγής και προβολής

Το δικαίωμα φορητότητας των δεδομένων επιτρέπει σε θέματα δεδομένων να ζητήσουν ένα αντίγραφο των προσωπικών δεδομένων του σε ηλεκτρονική μορφή (η οποία ορίζεται ως "δομημένη, συνήθως χρησιμοποιούμενη, αναγνώσιμη από μηχάνημα και διαλειτουργική μορφή") που μπορεί να μεταβιβαστεί σε άλλο υπεύθυνο επεξεργασίας δεδομένων.

##### <a name="export-customer-data-tenant-admin"></a>Εξαγωγή δεδομένων πελατών (διαχειριστής μισθωτών)

Ένας διαχειριστής μισθωτών μπορεί να ακολουθεί αυτά τα βήματα για να εξαγάγει δεδομένα:

1. Στείλτε ένα μήνυμα ηλεκτρονικού ταχυδρομείου στο D365CI@microsoft.com για να καθορίσετε τη διεύθυνση ηλεκτρονικού ταχυδρομείου του πελάτη στην αίτηση. Η ομάδα του Customer Insights θα στείλει ένα μήνυμα ηλεκτρονικού ταχυδρομείου στη διεύθυνση ηλεκτρονικού ταχυδρομείου που έχει καταχωρηθεί στη διεύθυνση διαχείρισης μισθωτών, ζητώντας επιβεβαίωση για εξαγωγή δεδομένων.
2. Επιβεβαιώστε την επιβεβαίωση για εξαγωγή των δεδομένων για τον ζητούμενο πελάτη.
3. Λάβετε τα δεδομένα που έχουν εξαχθεί μέσω της διεύθυνσης ηλεκτρονικού ταχυδρομείου του διαχειριστή μισθωτών.

##### <a name="export-user-data-tenant-admin"></a>Εξαγωγή δεδομένων χρηστών (διαχειριστής μισθωτών)

1. Στείλτε ένα μήνυμα ηλεκτρονικού ταχυδρομείου στο D365CI@microsoft.com για να καθορίσετε τη διεύθυνση ηλεκτρονικού ταχυδρομείου του χρήστη στην αίτηση. Η ομάδα του Customer Insights θα στείλει ένα μήνυμα ηλεκτρονικού ταχυδρομείου στη διεύθυνση ηλεκτρονικού ταχυδρομείου που έχει καταχωρηθεί στη διεύθυνση διαχείρισης μισθωτών, ζητώντας επιβεβαίωση για εξαγωγή δεδομένων.
2. Επιβεβαιώστε την επιβεβαίωση για εξαγωγή των δεδομένων για τον ζητούμενο χρήστη.
3. Λάβετε τα δεδομένα που έχουν εξαχθεί μέσω της διεύθυνσης ηλεκτρονικού ταχυδρομείου του διαχειριστή μισθωτών.

## <a name="consent-management-preview"></a>Διαχείριση συναίνεσης (προεπισκόπηση)

Η δυνατότητα διαχείρισης συναινέσεις δεν συλλέγει απευθείας δεδομένα χρηστών. Εισάγει και επεξεργάζεται μόνο τα δεδομένα συγκατάθεσης που παρέχονται από χρήστες σε άλλες εφαρμογές.

Για να καταργήσετε τα δεδομένα συγκατάθεσης σχετικά με συγκεκριμένους χρήστες, καταργήστε τα στην προέλευση δεδομένων που έχει πρόσβαση στη δυνατότητα διαχείρισης συναίνεσης. Μετά την ανανέωση της προέλευσης δεδομένων, τα δεδομένα που έχουν καταργηθεί θα διαγραφούν και στο Κέντρο συναινέσεις. Οι εφαρμογές που χρησιμοποιούν την οντότητα συγκατάθεσης θα διαγράψουν επίσης δεδομένα που έχουν καταργηθεί στην προέλευση μετά από μια [ανανέωση](audience-insights/system.md#refresh-processes). Συνιστούμε να ανανεώσετε γρήγορα την προέλευση δεδομένων, αφού ανταποκριθείτε σε ένα αίτημα θέματος δεδομένων, για να καταργήσετε τα δεδομένα του χρήστη από όλες τις άλλες διεργασίες και εφαρμογές.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]