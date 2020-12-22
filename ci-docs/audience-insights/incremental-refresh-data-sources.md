---
title: Σταδιακή ανανέωση για προελεύσεις δεδομένων βασισμένες σε Power Query
description: Ανανέωση νέων και ενημερωμένων δεδομένων για μεγάλες προελεύσεις δεδομένων που βασίζονται στο Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405842"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="b1f1a-103">Σταδιακή ανανέωση για προελεύσεις δεδομένων βασισμένες στο Power Query</span><span class="sxs-lookup"><span data-stu-id="b1f1a-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="b1f1a-104">Η σταδιακή ανανέωση για τις προελεύσεις δεδομένων παρέχει τα ακόλουθα πλεονεκτήματα:</span><span class="sxs-lookup"><span data-stu-id="b1f1a-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="b1f1a-105">**Ταχύτερη ανανέωση** -Μόνο τα δεδομένα που έχουν αλλάξει ανανεώνονται.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="b1f1a-106">Για παράδειγμα, μπορείτε να ανανεώσετε μόνο τις πέντε τελευταίες ημέρες ενός ιστορικού συνόλου δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="b1f1a-107">**Αυξημένη αξιοπιστία** -Με μικρότερες ανανεώσεις, δεν χρειάζεται να διατηρήσετε τις συνδέσεις σε ασταθή συστήματα προέλευσης για όσο χρονικό διάστημα χρειαστεί, μειώνοντας τον κίνδυνο ζητημάτων σύνδεσης.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="b1f1a-108">**Μειωμένη κατανάλωση πόρων** - Η ανανέωση μόνο ενός υποσυνόλου των συνολικών δεδομένων σας οδηγεί σε πιο αποδοτική χρήση των υπολογιστικών πόρων και μειώνει το περιβαλλοντικό αποτύπωμα.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="b1f1a-109">Ρύθμιση παραμέτρων σταδιακής ανανέωσης</span><span class="sxs-lookup"><span data-stu-id="b1f1a-109">Configure incremental refresh</span></span>

<span data-ttu-id="b1f1a-110">Οι πληροφορίες κοινού σας επιτρέπουν τη σταδιακή ανανέωση για προελεύσεις δεδομένων που εισάγονται μέσω Power Query που υποστηρίζουν σταδιακή λήψη.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="b1f1a-111">Για παράδειγμα, οι βάσεις δεδομένων Azure SQL με πεδία ημερομηνίας και ώρας, τα οποία υποδεικνύουν την ημερομηνία τελευταίας ενημέρωσης των καρτελών δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="b1f1a-112">[Δημιουργήστε μια νέα προέλευση δεδομένων με βάση το Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="b1f1a-113">Πληκτρολογήστε ένα όνομα για την προέλευση δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="b1f1a-114">Επιλέξτε μια προέλευση δεδομένων που υποστηρίζει σταδιακή ανανέωση, όπως τη βάση δεδομένων δημιουργήστε μια βάση δεδομένων Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="b1f1a-115">Επιλέξτε τις οντότητες ή τους πίνακες που θα συγκεντρωθούν.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="b1f1a-116">Ολοκληρώστε τα βήματα μετασχηματισμού και επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="b1f1a-117">Στο παράθυρο διαλόγου **Ρύθμιση τμηματικής ανανέωσης**, επιλέξτε **Ρύθμιση** για να ανοίξετε τις **Ρυθμίσεις τμηματικής ανανέωσης**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="b1f1a-118">Εάν επιλέξετε **Παράλειψη**, η προέλευση δεδομένων θα ανανεώσει ολόκληρο το σύνολο δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="b1f1a-119">Μπορείτε, επίσης, να εφαρμόσετε σταδιακή ανανέωση μεταγενέστερα με την επεξεργασία μιας υπάρχουσας προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="b1f1a-120">Στις **Ρυθμίσεις τμηματικής ανανέωσης** θα ρυθμίσετε τις παραμέτρους της στοιχειώδους ανανέωσης για όλες τις οντότητες που επιλέξατε κατά τη δημιουργία της προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1f1a-121">![Ρύθμιση παραμέτρων οντοτήτων σε προέλευση δεδομένων για σταδιακή ανανέωση](media/incremental-refresh-settings.png "Ρύθμιση παραμέτρων οντοτήτων σε προέλευση δεδομένων για σταδιακή ανανέωση")</span><span class="sxs-lookup"><span data-stu-id="b1f1a-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="b1f1a-122">Επιλέξτε μια οντότητα και δώστε τις εξής λεπτομέρειες:</span><span class="sxs-lookup"><span data-stu-id="b1f1a-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="b1f1a-123">**Ορισμός του πρωτεύοντος κλειδιού**: Επιλέξτε ένα πρωτεύον κλειδί για την οντότητα ή τον πίνακα.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="b1f1a-124">**Καθορίστε το πεδίο "τελευταίο ενημερωμένο"**: Αυτό το πεδίο θα εμφανίσει μόνο τα χαρακτηριστικά τύπου "ημερομηνία" ή "ώρα".</span><span class="sxs-lookup"><span data-stu-id="b1f1a-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="b1f1a-125">Επιλέξτε ένα χαρακτηριστικό που υποδεικνύει την ώρα τελευταίας ενημέρωσης των καρτελών.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="b1f1a-126">Θα χρησιμοποιηθεί για τον προσδιορισμό των καρτελών που εμπίπτουν στο χρονικό πλαίσιο σταδιακής ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="b1f1a-127">**Έλεγχος για ενημερώσεις κάθε**: Καθορίστε τη διάρκεια που θέλετε να έχει το χρονικό πλαίσιο τμηματικής ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="b1f1a-128">Επιλέξτε **Αποθήκευση** για να ολοκληρώσετε τη δημιουργία της προέλευσης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="b1f1a-129">Η αρχική ανανέωση των δεδομένων θα είναι πλήρης.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="b1f1a-130">Στη συνέχεια, η τμηματική ανανέωση των δεδομένων θα γίνει όπως έχει ρυθμιστεί στο προηγούμενο βήμα.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
