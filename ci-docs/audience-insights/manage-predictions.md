---
title: Κοινόχρηστες εργασίες για σενάρια πρόβλεψης
description: Μάθετε πώς να διαχειρίζεστε, να αντιμετωπίζετε προβλήματα και να βελτιώνετε τις προβλέψεις.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095712"
---
# <a name="manage-predictions"></a><span data-ttu-id="7da5a-103">Διαχείριση προβλέψεων</span><span class="sxs-lookup"><span data-stu-id="7da5a-103">Manage predictions</span></span>

<span data-ttu-id="7da5a-104">Αυτό το άρθρο ασχολείται με ορισμένες εργασίες που είναι κοινές στα περισσότερα σενάρια πρόβλεψης.</span><span class="sxs-lookup"><span data-stu-id="7da5a-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="7da5a-105">Αντιμετώπιση προβλημάτων μιας αποτυχημένης πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="7da5a-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="7da5a-106">Μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** και επιλέξτε την καρτέλα **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="7da5a-107">Επιλέξτε τα κατακόρυφα αποσιωπητικά δίπλα στην πρόβλεψη για τα οποία θέλετε να προβάλετε αρχεία καταγραφής σφαλμάτων.</span><span class="sxs-lookup"><span data-stu-id="7da5a-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="7da5a-108">Επιλέξτε **Αρχεία καταγραφής**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-108">Select **Logs**.</span></span>

1. <span data-ttu-id="7da5a-109">Ελέγξτε όλα τα σφάλματα.</span><span class="sxs-lookup"><span data-stu-id="7da5a-109">Review all the errors.</span></span> <span data-ttu-id="7da5a-110">Υπάρχουν διάφοροι τύποι σφαλμάτων που μπορεί να προκύψουν και περιγράφουν ποια συνθήκη προκάλεσε το σφάλμα.</span><span class="sxs-lookup"><span data-stu-id="7da5a-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="7da5a-111">Για παράδειγμα, ένα σφάλμα κατά το οποίο τα δεδομένα δεν είναι αρκετά για να προβλέψετε με ακρίβεια, συνήθως επιλύεται με τη φόρτωση πρόσθετων δεδομένων στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7da5a-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="7da5a-112">Αναφορά χρηστικότητας δεδομένων εισόδου</span><span class="sxs-lookup"><span data-stu-id="7da5a-112">Input data usability report</span></span>

<span data-ttu-id="7da5a-113">Η αναφορά χρηστικότητας δεδομένων εισόδου παρέχει μια ενοποιημένη προβολή των σφαλμάτων και των προειδοποιήσεων που ενδέχεται να δημιουργούνται από τις πρώτες σας προβλέψεις.</span><span class="sxs-lookup"><span data-stu-id="7da5a-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="7da5a-114">Επίσης, παρέχει συστάσεις σχετικά με τον τρόπο βελτίωσης της απόδοσης του μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="7da5a-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="7da5a-115">Η αναφορά είναι διαθέσιμη αφού ένα μοντέλο ολοκληρώσει τη διαδικασία εκπαίδευσης.</span><span class="sxs-lookup"><span data-stu-id="7da5a-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="7da5a-116">Δημιουργείται για κάθε μοντέλο ξεχωριστά, ανεξάρτητα από το αν έχει ολοκληρωθεί με επιτυχία ή όχι.</span><span class="sxs-lookup"><span data-stu-id="7da5a-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="7da5a-117">Αυτήν τη στιγμή, αυτή η δυνατότητα λειτουργεί μόνο για το μοντέλο Transaction Churn.</span><span class="sxs-lookup"><span data-stu-id="7da5a-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="7da5a-118">Προβολή της αναφοράς χρηστικότητας δεδομένων εισόδου</span><span class="sxs-lookup"><span data-stu-id="7da5a-118">View the input data usability report</span></span>

<span data-ttu-id="7da5a-119">Αφού ένα έτοιμο προς χρήση μοντέλο ολοκληρώσει το βήμα εκπαίδευσης, προβάλετε την αναφορά:</span><span class="sxs-lookup"><span data-stu-id="7da5a-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="7da5a-120">Επιλέξτε τα αποσιωπητικά δίπλα στο όνομα του μοντέλου και επιλέξτε **Αναφορά χρηστικότητας δεδομένων εισόδου**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="7da5a-121">Επιλέξτε την κατάσταση ενός μοντέλου, επιλέξτε **Προβολή αναφοράς χρηστικότητας δεδομένων εισόδου** στο πλαϊνό τμήμα παραθύρου.</span><span class="sxs-lookup"><span data-stu-id="7da5a-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="7da5a-122">Επιλέξτε ένα από τα μοντέλα στη λίστα και επιλέξτε **Αναφορά χρηστικότητας δεδομένων εισόδου** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="7da5a-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="7da5a-123">Ανοίξτε τη σελίδα αποτελεσμάτων μοντέλου και επιλέξτε **Αναφορά χρηστικότητας δεδομένων εισόδου** στη γραμμή εντολών.</span><span class="sxs-lookup"><span data-stu-id="7da5a-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="7da5a-124">Πληροφορίες στην αναφορά χρηστικότητας δεδομένων εισόδου</span><span class="sxs-lookup"><span data-stu-id="7da5a-124">Information in the input data usability report</span></span>

<span data-ttu-id="7da5a-125">Οι παρακάτω στήλες στην αναφορά περιέχουν χρήσιμες πληροφορίες για τη βελτίωση των δεδομένων για το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="7da5a-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Παράδειγμα αναφοράς χρηστικότητας δεδομένων εισόδου που δείχνει έναν πίνακα με σφάλματα, προειδοποιήσεις και συστάσεις.":::

- <span data-ttu-id="7da5a-127">Όνομα: Περιγραφικό όνομα του σφάλματος, της προειδοποίησης ή της σύστασης.</span><span class="sxs-lookup"><span data-stu-id="7da5a-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="7da5a-128">Βήμα: Φάση μοντέλου, εκπαίδευση ή βαθμολογία, στα οποία αναφέρονται οι πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="7da5a-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="7da5a-129">Κατάσταση: Σοβαρότητα των πληροφοριών (σφάλμα, προειδοποίηση, σύσταση).</span><span class="sxs-lookup"><span data-stu-id="7da5a-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="7da5a-130">Όνομα στήλης: Στήλη σε μια οντότητα που πρέπει να τροποποιηθεί για τη βελτίωση των επιδόσεων του μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="7da5a-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="7da5a-131">Όνομα οντότητας: Το όνομα της οντότητας που πρέπει να τροποποιηθεί για τη βελτίωση των επιδόσεων του μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="7da5a-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="7da5a-132">Λεπτομέρειες: Λεπτομέρειες σχετικά με το σφάλμα, την προειδοποίηση ή τη σύσταση.</span><span class="sxs-lookup"><span data-stu-id="7da5a-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="7da5a-133">Ανανέωση πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="7da5a-133">Refresh a prediction</span></span>

<span data-ttu-id="7da5a-134">Οι προβλέψεις θα ανανεώνονται αυτόματα στο ίδιο [χρονοδιάγραμμα που θα ανανεώνονται τα δεδομένα σας](system.md#schedule-tab) όπως έχουν ρυθμιστεί στις ρυθμίσεις.</span><span class="sxs-lookup"><span data-stu-id="7da5a-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="7da5a-135">Μπορείτε να τα ανανεώσετε και με μη αυτόματο τρόπο.</span><span class="sxs-lookup"><span data-stu-id="7da5a-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="7da5a-136">Μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** και επιλέξτε την καρτέλα **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="7da5a-137">Επιλέξτε τις κατακόρυφες ελλείψεις δίπλα στην πρόβλεψη που θέλετε να ανανεώσετε.</span><span class="sxs-lookup"><span data-stu-id="7da5a-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="7da5a-138">Επιλέξτε **Ανανέωση**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="7da5a-139">Διαγραφή πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="7da5a-139">Delete a prediction</span></span>

<span data-ttu-id="7da5a-140">Η διαγραφή μιας πρόβλεψης καταργεί επίσης την οντότητα εξόδου.</span><span class="sxs-lookup"><span data-stu-id="7da5a-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="7da5a-141">Μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** και επιλέξτε την καρτέλα **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="7da5a-142">Επιλέξτε τις κατακόρυφες ελλείψεις δίπλα στην πρόβλεψη που θέλετε να διαγράψετε.</span><span class="sxs-lookup"><span data-stu-id="7da5a-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="7da5a-143">Επιλέξτε **Διαγραφή**.</span><span class="sxs-lookup"><span data-stu-id="7da5a-143">Select **Delete**.</span></span>
