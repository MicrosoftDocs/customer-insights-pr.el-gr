---
title: Εμπλουτισμός με προσαρμοσμένη εισαγωγή SFTP
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό προσαρμοσμένων εισαγωγών SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896281"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="54891-103">Εμπλουτισμός προφίλ πελατών με προσαρμοσμένα δεδομένα (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="54891-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="54891-104">Η προσαρμοσμένη εισαγωγή του Πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP) σάς δίνει τη δυνατότητα να εισαγάγετε δεδομένα τα οποία δεν χρειάζεται να περάσουν από τη διεργασία ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="54891-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="54891-105">Πρόκειται για έναν ευέλικτο, ασφαλή και εύκολο τρόπο για να μεταφέρετε τα δεδομένα σας.</span><span class="sxs-lookup"><span data-stu-id="54891-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="54891-106">Η προσαρμοσμένη εισαγωγή SFTP μπορεί να χρησιμοποιηθεί σε συνδυασμό με την [εξαγωγή SFTP](export-sftp.md) που σας δίνει τη δυνατότητα να εξαγάγετε τα δεδομένα προφίλ πελατών που απαιτούνται για τον εμπλουτισμό.</span><span class="sxs-lookup"><span data-stu-id="54891-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="54891-107">Στη συνέχεια, τα δεδομένα μπορούν να υποβληθούν σε επεξεργασία, να εμπλουτιστούν και η προσαρμοσμένη εισαγωγή SFTP μπορεί να χρησιμοποιηθεί για την επαναφορά των εμπλουτισμένων δεδομένων στη δυνατότητα πληροφοριών κοινού του Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54891-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54891-108">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="54891-108">Prerequisites</span></span>

<span data-ttu-id="54891-109">Για να ρυθμίσετε την προσαρμοσμένη εισαγωγή SFTP, θα πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="54891-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="54891-110">Έχετε το όνομα αρχείου και τη θέση (διαδρομή) του αρχείου που θα εισαχθεί στον κεντρικό υπολογιστή SFTP.</span><span class="sxs-lookup"><span data-stu-id="54891-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="54891-111">Υπάρχει ένα αρχείο *model.json* που καθορίζει [το σχήμα του κοινού μοντέλου δεδομένων](/common-data-model/) για τα δεδομένα που θα εισαχθούν.</span><span class="sxs-lookup"><span data-stu-id="54891-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="54891-112">Αυτό το αρχείο πρέπει να βρίσκεται στον ίδιο κατάλογο με το αρχείο προς εισαγωγή.</span><span class="sxs-lookup"><span data-stu-id="54891-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="54891-113">Μια σύνδεση SFTP έχει ήδη ρυθμιστεί από έναν διαχειριστή *ή* έχετε δικαιώματα [διαχειριστή](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="54891-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="54891-114">Θα χρειαστείτε τα διαπιστευτήρια χρήστη, τη διεύθυνση URL και τον αριθμό θύρας για τη θέση SFTP από την οποία θέλετε να εισαγάγετε δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="54891-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="54891-115">Ρύθμιση παραμέτρων της εισαγωγής</span><span class="sxs-lookup"><span data-stu-id="54891-115">Configure the import</span></span>

1. <span data-ttu-id="54891-116">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.</span><span class="sxs-lookup"><span data-stu-id="54891-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="54891-117">Στο **πλακίδιο προσαρμοσμένης εισαγωγής SFTP**, επιλέξτε **Εμπλουτισμός των δεδομένων μου** κι, έπειτα, επιλέξτε **Έναρξη**.</span><span class="sxs-lookup"><span data-stu-id="54891-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Πλακίδιο προσαρμοσμένης εισαγωγής SFTP.":::

1. <span data-ttu-id="54891-119">Επιλέξτε μια [σύνδεση](connections.md) από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="54891-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="54891-120">Επικοινωνήστε με έναν διαχειριστή εάν δεν υπάρχει διαθέσιμη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="54891-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="54891-121">Εάν είστε διαχειριστής, μπορείτε να δημιουργήσετε μια σύνδεση επιλέγοντας **Προσθήκη σύνδεσης** και επιλέγοντας **Προσαρμοσμένη εισαγωγή SFTP** από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="54891-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="54891-122">Επιλέξτε **Σύνδεση με Προσαρμοσμένη εισαγωγή** για να επιβεβαιώσετε την επιλεγμένη σύνδεση.</span><span class="sxs-lookup"><span data-stu-id="54891-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="54891-123">Επιλέξτε **Επόμενο** και εισαγάγετε **Όνομα αρχείου** και **Διαδρομή** του αρχείου δεδομένων που θέλετε να εισαγάγετε.</span><span class="sxs-lookup"><span data-stu-id="54891-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Στιγμιότυπο οθόνης κατά την εισαγωγή της θέσης δεδομένων.":::

1. <span data-ttu-id="54891-125">Επιλέξτε **Επόμενο** και δώστε ένα όνομα για τον εμπλουτισμό και ένα όνομα για την οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="54891-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="54891-126">Επιλέξτε **Αποθήκευση εμπλουτισμού** αφού αναθεωρήσετε τις επιλογές σας.</span><span class="sxs-lookup"><span data-stu-id="54891-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="54891-127">Ρύθμιση παραμέτρων της σύνδεσης για προσαρμοσμένη εισαγωγή SFTP</span><span class="sxs-lookup"><span data-stu-id="54891-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="54891-128">Για να ρυθμίσετε τις παραμέτρους των συνδέσεων, θα πρέπει να είστε διαχειριστής.</span><span class="sxs-lookup"><span data-stu-id="54891-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="54891-129">Επιλέξτε **Προσθήκη σύνδεσης** κατά τη ρύθμιση παραμέτρων ενός εμπλουτισμού *ή* μεταβείτε στο **Διαχειριστής** > **Συνδέσεις** και επιλέξτε **Ρύθμιση** στο πλακίδιο προσαρμοσμένης εισαγωγής.</span><span class="sxs-lookup"><span data-stu-id="54891-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="54891-130">Πληκτρολογήστε ένα όνομα για τη σύνδεση στο πλαίσιο **Εμφανιζόμενο όνομα**.</span><span class="sxs-lookup"><span data-stu-id="54891-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="54891-131">Εισαγάγετε έγκυρο όνομα χρήστη, κωδικό πρόσβασης και διεύθυνση URL κεντρικού υπολογιστή για τον διακομιστή STFP στον οποίο βρίσκονται τα δεδομένα προς εισαγωγή.</span><span class="sxs-lookup"><span data-stu-id="54891-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="54891-132">Ελέγξτε και δώστε τη συγκατάθεσή σας για το **Απόρρητο και τη συμμόρφωση των δεδομένων** επιλέγοντας το πλαίσιο ελέγχου **Συμφωνώ**.</span><span class="sxs-lookup"><span data-stu-id="54891-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="54891-133">Επιλέξτε **Επαλήθευση** για να επικυρώσετε τη ρύθμιση παραμέτρων.</span><span class="sxs-lookup"><span data-stu-id="54891-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="54891-134">Όταν ολοκληρωθεί η επαλήθευση, η σύνδεση μπορεί να αποθηκευτεί κάνοντας κλικ στην επιλογή **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="54891-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="54891-135">![Σελίδα ρύθμισης παραμέτρων σύνδεσης Experian](media/enrichment-SFTP-connection.png "Σελίδα ρύθμισης παραμέτρων σύνδεσης Experian.")</span><span class="sxs-lookup"><span data-stu-id="54891-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="54891-136">Ορισμός αντιστοιχίσεων πεδίων</span><span class="sxs-lookup"><span data-stu-id="54891-136">Defining field mappings</span></span> 

<span data-ttu-id="54891-137">Ο κατάλογος που περιέχει το αρχείο που πρόκειται να εισαχθεί στον διακομιστή SFTP πρέπει επίσης να περιέχει ένα αρχείο *model.json*.</span><span class="sxs-lookup"><span data-stu-id="54891-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="54891-138">Αυτό το αρχείο καθορίζει το σχήμα που θα χρησιμοποιηθεί για την εισαγωγή των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="54891-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="54891-139">Το σχήμα πρέπει να χρησιμοποιεί [το Common Data Model](/common-data-model/) για τον καθορισμό της αντιστοίχισης πεδίων.</span><span class="sxs-lookup"><span data-stu-id="54891-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="54891-140">Ένα απλό παράδειγμα ενός αρχείου model.json μοιάζει με αυτό:</span><span class="sxs-lookup"><span data-stu-id="54891-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="54891-141">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="54891-141">Enrichment results</span></span>

<span data-ttu-id="54891-142">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="54891-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="54891-143">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54891-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54891-144">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων που πρόκειται να εισαχθούν και από τη σύνδεση στον διακομιστή SFTP.</span><span class="sxs-lookup"><span data-stu-id="54891-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="54891-145">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα πρόσφατα δεδομένα προσαρμοσμένου εμπλουτισμού που εισαγάγατε στο πλαίσιο των **Εμπλουτισμών μου**.</span><span class="sxs-lookup"><span data-stu-id="54891-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="54891-146">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="54891-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="54891-147">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="54891-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="54891-148">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="54891-148">Next steps</span></span>

<span data-ttu-id="54891-149">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="54891-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="54891-150">Δημιουργήστε [τμήματα αγοράς](segments.md), [μέτρα](measures.md) και [εξαγάγετε τα δεδομένα](export-destinations.md) για την παροχή εξατομικευμένων εμπειριών στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="54891-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
