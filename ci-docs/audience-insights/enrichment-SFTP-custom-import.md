---
title: Εμπλουτισμός με προσαρμοσμένη εισαγωγή SFTP
description: Γενικές πληροφορίες σχετικά με τον εμπλουτισμό προσαρμοσμένων εισαγωγών SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595855"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4d90c-103">Εμπλουτισμός προφίλ πελατών με προσαρμοσμένα δεδομένα (προεπισκόπηση)</span><span class="sxs-lookup"><span data-stu-id="4d90c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4d90c-104">Η προσαρμοσμένη εισαγωγή πρωτοκόλλου ασφαλούς μεταφοράς αρχείων (SFTP) σάς δίνει τη δυνατότητα να εισαγάγετε δεδομένα τα οποία δεν χρειάζεται να περάσουν από τη διεργασία ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="4d90c-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4d90c-105">Πρόκειται για έναν ευέλικτο, ασφαλή και εύκολο τρόπο για να μεταφέρετε τα δεδομένα σας.</span><span class="sxs-lookup"><span data-stu-id="4d90c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4d90c-106">Η προσαρμοσμένη εισαγωγή SFTP μπορεί να χρησιμοποιηθεί σε συνδυασμό με την [εξαγωγή SFTP](export-sftp.md) που σας δίνει τη δυνατότητα να εξαγάγετε τα δεδομένα προφίλ πελατών που απαιτούνται για τον εμπλουτισμό.</span><span class="sxs-lookup"><span data-stu-id="4d90c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4d90c-107">Στη συνέχεια, τα δεδομένα μπορούν να υποβληθούν σε επεξεργασία, να εμπλουτιστούν και η προσαρμοσμένη εισαγωγή SFTP μπορεί να χρησιμοποιηθεί για την επαναφορά των εμπλουτισμένων δεδομένων στη δυνατότητα πληροφοριών κοινού του Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4d90c-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d90c-108">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="4d90c-108">Prerequisites</span></span>

<span data-ttu-id="4d90c-109">Για να ρυθμίσετε την προσαρμοσμένη εισαγωγή SFTP, θα πρέπει να πληρούνται οι ακόλουθες προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="4d90c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4d90c-110">Να έχετε διαπιστευτήρια χρήστη (όνομα χρήστη και κωδικό πρόσβασης) για τη θέση SFTP από την οποία πρόκειται να εισαχθούν τα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="4d90c-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="4d90c-111">Να διαθέτετε τη διεύθυνση URL και τον αριθμό θύρας (συνήθως 22) για τον κεντρικό υπολογιστή STFP.</span><span class="sxs-lookup"><span data-stu-id="4d90c-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="4d90c-112">Να διαθέτετε το όνομα αρχείου και τη θέση του αρχείου που πρόκειται να εισαχθεί στον κεντρικό υπολογιστή SFTP.</span><span class="sxs-lookup"><span data-stu-id="4d90c-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4d90c-113">Υπάρχει ένα αρχείο *model.json* που καθορίζει το σχήμα για τα δεδομένα που πρόκειται να εισαχθούν.</span><span class="sxs-lookup"><span data-stu-id="4d90c-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="4d90c-114">Αυτό το αρχείο πρέπει να βρίσκεται στον ίδιο κατάλογο με το αρχείο προς εισαγωγή.</span><span class="sxs-lookup"><span data-stu-id="4d90c-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4d90c-115">Να έχετε δικαίωμα [Διαχειριστή](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="4d90c-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="4d90c-116">Ρύθμιση παραμέτρων</span><span class="sxs-lookup"><span data-stu-id="4d90c-116">Configuration</span></span>

1. <span data-ttu-id="4d90c-117">Μεταβείτε στα **Δεδομένα** > **Εμπλουτισμός** και επιλέξτε την καρτέλα **Εντοπισμός**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4d90c-118">Στο **πλακίδιο προσαρμοσμένης εισαγωγής SFTP**, επιλέξτε **Εμπλουτισμός των δεδομένων μου**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d90c-119">![Πλακίδιο προσαρμοσμένης εισαγωγής SFTP](media/SFTP_Custom_Import_tile.png "Πλακίδιο προσαρμοσμένης εισαγωγής SFTP")</span><span class="sxs-lookup"><span data-stu-id="4d90c-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="4d90c-120">Επιλέξτε **Έναρξη** και δώστε τα διαπιστευτήρια και τη διεύθυνση του διακομιστή SFTP.</span><span class="sxs-lookup"><span data-stu-id="4d90c-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="4d90c-121">Για παράδειγμα, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="4d90c-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="4d90c-122">Εάν δεν βρίσκεται στον ριζικό φάκελο, εισαγάγετε το όνομα του αρχείου που περιέχει τα δεδομένα και τη διαδρομή προς το αρχείο στον διακομιστή SFTP.</span><span class="sxs-lookup"><span data-stu-id="4d90c-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="4d90c-123">Επιβεβαιώστε όλες τις εισόδους επιλέγοντας **Σύνδεση με Προσαρμοσμένη εισαγωγή**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d90c-124">![Αναδυόμενη επιλογή ρύθμισης προσαρμοσμένων εισαγωγών SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Αναδυόμενη επιλογή ρύθμισης προσαρμοσμένων εισαγωγών SFTP")</span><span class="sxs-lookup"><span data-stu-id="4d90c-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="4d90c-125">Ορισμός αντιστοιχίσεων πεδίων</span><span class="sxs-lookup"><span data-stu-id="4d90c-125">Defining field mappings</span></span> 

<span data-ttu-id="4d90c-126">Ο κατάλογος που περιέχει το αρχείο που πρόκειται να εισαχθεί στον διακομιστή SFTP πρέπει επίσης να περιέχει ένα αρχείο *model.json*.</span><span class="sxs-lookup"><span data-stu-id="4d90c-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4d90c-127">Αυτό το αρχείο καθορίζει το σχήμα που θα χρησιμοποιηθεί για την εισαγωγή των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="4d90c-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4d90c-128">Το σχήμα πρέπει να χρησιμοποιεί [το Common Data Model](/common-data-model/) για τον καθορισμό της αντιστοίχισης πεδίων.</span><span class="sxs-lookup"><span data-stu-id="4d90c-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4d90c-129">Ένα απλό παράδειγμα ενός αρχείου model.json μοιάζει με αυτό:</span><span class="sxs-lookup"><span data-stu-id="4d90c-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="4d90c-130">Αποτελέσματα εμπλουτισμού</span><span class="sxs-lookup"><span data-stu-id="4d90c-130">Enrichment results</span></span>

<span data-ttu-id="4d90c-131">Για να ξεκινήσετε τη διεργασία εμπλουτισμού, επιλέξτε **Εκτέλεση** από τη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="4d90c-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4d90c-132">Μπορείτε, επίσης, να επιτρέψετε στο σύστημα την εκτέλεση του εμπλουτισμού αυτόματα ως μέρος μιας [προγραμματισμένης ανανέωσης](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4d90c-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4d90c-133">Ο χρόνος επεξεργασίας θα εξαρτηθεί από το μέγεθος των δεδομένων που πρόκειται να εισαχθούν και από τη σύνδεση στον διακομιστή SFTP.</span><span class="sxs-lookup"><span data-stu-id="4d90c-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4d90c-134">Μετά την ολοκλήρωση της διαδικασίας εμπλουτισμού, μπορείτε να εξετάσετε τα πρόσφατα δεδομένα προσαρμοσμένου εμπλουτισμού που εισαγάγατε στο πλαίσιο των **Εμπλουτισμών μου**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4d90c-135">Επιπλέον, θα βρείτε την ώρα της τελευταίας ενημέρωσης και τον αριθμό των εμπλουτισμένων προφίλ.</span><span class="sxs-lookup"><span data-stu-id="4d90c-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4d90c-136">Μπορείτε να αποκτήσετε πρόσβαση σε μια λεπτομερή προβολή για κάθε εμπλουτισμένο προφίλ επιλέγοντας **Προβολή εμπλουτισμένων δεδομένων**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d90c-137">Επόμενα βήματα</span><span class="sxs-lookup"><span data-stu-id="4d90c-137">Next steps</span></span>

<span data-ttu-id="4d90c-138">Δημιουργήστε τα εμπλουτισμένα δεδομένα των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="4d90c-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4d90c-139">Δημιουργήστε [τμήματα αγοράς](segments.md), [μέτρα](measures.md) και [εξαγάγετε τα δεδομένα](export-destinations.md) για την παροχή εξατομικευμένων εμπειριών στους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="4d90c-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]