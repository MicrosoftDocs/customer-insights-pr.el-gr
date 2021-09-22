---
title: Δημιουργία σύνδεσης μεταξύ των πληροφοριών κοινού και των πληροφοριών δέσμευσης
description: Δημιουργήστε μια ενεργή σύνδεση μεταξύ των πληροφοριών κοινού και των πληροφοριών δέσμευσης, ώστε να είναι δυνατή η αμφίδρομη κοινή χρήση δεδομένων.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461013"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Δημιουργία σύνδεσης μεταξύ των πληροφοριών κοινού και των πληροφοριών δέσμευσης

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Η ενοποίηση μεταξύ των πληροφοριών δέσμευσης και των πληροφοριών κοινού συνδέει περιβάλλοντα και από τις δύο δυνατότητες και επιτρέπει την αμφίδρομη κοινή χρήση των δεδομένων μεταξύ τους.

Χρησιμοποιήστε ενοποιημένα προφίλ και τμήματα από τις πληροφορίες κοινού για περισσότερες επιλογές ανάλυσης στις πληροφορίες δέσμευσης. Εξαγάγετε συμβάντα με υψηλή επιχειρηματική αξία από τις πληροφορίες δέσμευσης. Χρησιμοποιήστε αυτά τα συμβάντα για να προσθέσετε δεδομένα σε ενοποιημένα προφίλ στις πληροφορίες κοινού.

## <a name="prerequisites"></a>Προϋποθέσεις

- Τα προφίλ πληροφοριών κοινού πρέπει να αποθηκεύονται σε έναν λογαριασμό Azure Data Lake Storage που σας ανήκει ή σε μια διαχειριζόμενη λίμνη δεδομένων [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;. 

- Χρειάζεστε δικαιώματα διαχειριστή τόσο για τις πληροφορίες δέσμευσης όσο και για τις πληροφορίες δέσμευσης κοινού.

- Τα συνδεδεμένα περιβάλλοντα πρέπει να είναι στην ίδια γεωγραφική περιοχή.

> [!NOTE]
> - Αν η συνδρομή πληροφοριών κοινού είναι δοκιμαστική έκδοση, η οποία χρησιμοποιεί μια εσωτερικά διαχειριζόμενη λίμνη δεδομένων πληροφοριών κονιού, επικοινωνήστε με την [pirequest@microsoft.com](mailto:pirequest@microsoft.com) για βοήθεια. 
> - Αν το περιβάλλον πληροφοριών κοινού σας χρησιμοποιεί το δικό σας Azure Data Lake Storage για την αποθήκευση δεδομένων, πρέπει να προσθέσετε μια αρχή υπηρεσίας Azure πληροφοριών δέσμευσης στον λογαριασμό χώρου αποθήκευσης. Για λεπτομέρειες, μεταβείτε στη [Σύνδεση σε έναν λογαριασμό Azure Data Lake Storage με μια αρχή υπηρεσίας Azure για πληροφορίες κοινού](../audience-insights/connect-service-principal.md). Επίσης, το περιβάλλον πληροφοριών κοινού σας θα πρέπει να έχει ένα συσχετισμένο [περιβάλλον Dataverse](../audience-insights/get-started-paid.md). 

## <a name="create-an-environment-link"></a>Δημιουργία σύνδεση περιβάλλοντος

Μπορείτε να δημιουργήσετε μια σύνδεση περιβάλλοντος ενημερώνοντας τις ρυθμίσεις **Διαχειριστής** > **Περιβάλλον** σε πληροφορίες δέσμευσης.

**Για να δημιουργήσετε μια ενεργή σύνδεση μεταξύ των πληροφοριών κοινού και των πληροφοριών δέσμευσης**

1. Στη σελίδα **Διαχειριστής περιβάλλοντος**, επιλέξτε την καρτέλα **Σύνδεση περιβαλλόντων**.

    :::image type="content" source="media/integrate1.png" alt-text="Ρύθμιση περιβάλλοντος.":::

1. Επιλέξτε **Εγκατάσταση περιβαλλόντων** στην επάνω αριστερή γωνία ή στο κάτω μέρος της οθόνης.

     :::image type="content" source="media/integrate2.png" alt-text="Επιλογή ενός περιβάλλοντος πληροφοριών κοινού.":::

1. Επιλέξτε ένα περιβάλλον πληροφοριών κοινού και, στη συνέχεια, επιλέξτε ***Επόμενο** για ολοκλήρωση. Τώρα μπορείτε να επιλέξετε προαιρετικές δυνατότητες για τα συνδεδεμένα περιβάλλοντα.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Ενεργοποίηση χαρακτηριστικών και τμημάτων ενοποιημένων προφίλ πληροφοριών κοινού

Μετά τη σύνδεησ περιβαλλόντων, μπορείτε να επιλέξετε προαιρετικές δυνατότητες για τα συνδεδεμένα περιβάλλοντα. Αυτές οι δυνατότητες επιτρέπουν τα ενοποιημένα χαρακτηριστικά προφίλ και τα τμήματα πληροφορίες κοινού για αλληλεπιδραστική ανάλυση στα δεδομένα των πελατών.

**Για την ανάλυση δεδομένων web σε πληροφορίες δέσμευσης**

1. Στη σελίδα **Διαχειριστής περιβάλλοντος**, ενεργοποιήστε την εναλλαγή **Κοινή χρήση δεδομένων από πληροφορίες κοινού με πληροφορίες δέσμευσης** και, στη συνέχεια, επιλέξτε **Επόμενο**.

    :::image type="content" source="media/integrate4.png" alt-text="Επιλογή χαρακτηριστικών.":::

1. Επιλέξτε τα χαρακτηριστικά των ενοποιημένων προφίλ που θα γίνουν διαστάσεις στις πληροφορίες δέσμευσης. (Δεν είναι όλα τα χαρακτηριστικά χρήσιμες διαστάσεις. Για παράδειγμα, δεν είναι πιθανό να χρειαστείτε **Όνομα** ή **Επώνυμο** ως χαρακτηριστικό για την ανάλυση των συμβάντων της τοποθεσίας Web σας.)

    :::image type="content" source="media/integrate5.png" alt-text="Επιμέλεια διαστάσεων.":::

   >[!NOTE]
   > Όλα τα χαρακτηριστικά προφίλ πληροφοριών κοινού που αντιπροσωπεύουν αναγνωριστικά (όπως το **αναγνωριστικό** και το **εναλλακτικό αναγνωριστικό**) φιλτράρονται από τα διαθέσιμα χαρακτηριστικά και γίνονται διαστάσεις στις πληροφορίες δέσμευσης.

1. Όταν τελειώσετε με την επιλογή χαρακτηριστικών, επιλέξτε **Επόμενο**.
1. Προσθέστε χρήστες που μπορούν να προβάλλουν τις ιδαστάσεις του προφίλ πληροφοριών κοινού και τα τμήματα στις πληροφορίες δέσμευσης.

    :::image type="content" source="media/integrate6.png" alt-text="Διαχείριση πρόσβασης σε δεδομένα πελατών.":::

   > [!IMPORTANT]
   > Αν δεν προσθέσετε ρητά χρήστες σε αυτό το βήμα, τα δεδομένα θα κρυφτούν από τους χρήστες σε πληροφορίες δέσμευσης.

1. Ελέγξτε την επιλογή σας και, στη συνέχεια, επιλέξτε **Τέλος**.

    :::image type="content" source="media/integrate7.png" alt-text="Εξετάστε τις ρυθμίσεις δεδομένων πελατών.":::

## <a name="export-refined-events-to-audience-insights"></a>Εξαγάγετε εκλεπτυσμένα συμβάντα σε πληροφορίες κοινού

Αφού δημιουργήσετε μια σύνδεση μεταξύ περιβαλλβαλλών, μπορείτε να εξαγάγετε πιο εκλεπτυσμένα συμβάντα από πληροφορίες δέσμευσης σε πληροφορίες κοινού και να τα χρησιμοποιήσετε ως ένα νέο προέλευση δεδομένων. 

Για περισσότερες πληροφορίες, μεταβείτε στην [ενσωμάτωση δεδομένων web από πληροφορίες δέσμευσης με πληροφορίες κοινού](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
