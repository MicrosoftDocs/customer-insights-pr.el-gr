---
title: Εύρεση παρόμοιων πελατών με AI
description: Εύρεση παρόμοιων τμημάτων πελατών με τεχνητή νοημοσύνη.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405839"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="d0432-103">Παρόμοιοι πελάτες (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="d0432-103">Similar Customers (preview)</span></span>

<span data-ttu-id="d0432-104">Αυτή η δυνατότητα σάς επιτρέπει να βρίσκετε παρόμοιους πελάτες στη βάση πελατών σας με χρήση τεχνητής νοημοσύνης.</span><span class="sxs-lookup"><span data-stu-id="d0432-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="d0432-105">Πρέπει να έχετε δημιουργήσει τουλάχιστον ένα τμήμα για να χρησιμοποιήσετε αυτήν τη δυνατότητα.</span><span class="sxs-lookup"><span data-stu-id="d0432-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="d0432-106">Η ανάπτυξη των κριτηρίων ενός υπάρχοντος τμήματος συμβάλλει στη εύρεση πελατών που είναι παρόμοιοι με αυτό το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="d0432-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="d0432-107">Η *εύρεση παρόμοιων πελατών* χρησιμοποιεί αυτοματοποιημένα μέσα για την αξιολόγηση των δεδομένων και την πραγματοποίηση προβλέψεων με βάση τα εν λόγω δεδομένα και επομένως έχει τη δυνατότητα να χρησιμοποιηθεί ως μέθοδος δημιουργίας προφίλ, όπως ορίζεται από τον γενικό κανονισμό για την προστασία των δεδομένων ("ΓΚΠΔ").</span><span class="sxs-lookup"><span data-stu-id="d0432-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="d0432-108">Η χρήση αυτής της δυνατότητας από τον πελάτη για την επεξεργασία των δεδομένων μπορεί να υπόκειται στον ΓΚΠΔ ή άλλες νομοθεσίες ή κανονισμούς.</span><span class="sxs-lookup"><span data-stu-id="d0432-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="d0432-109">Είστε υπεύθυνοι για τη διασφάλιση ότι η χρήση του Dynamics 365 Customer Insights, συμπεριλαμβανομένων προβλέψεων, συμμορφώνεται με όλους τους ισχύοντες νόμους και κανονισμούς, συμπεριλαμβανομένων των νόμων που σχετίζονται με την προστασία της ιδιωτικής ζωής, τα προσωπικά δεδομένα, τα βιομετρικά δεδομένα, την προστασία των δεδομένων και την εμπιστευτικότητα των επικοινωνιών.</span><span class="sxs-lookup"><span data-stu-id="d0432-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="d0432-110">Εύρεση παρόμοιων πελατών</span><span class="sxs-lookup"><span data-stu-id="d0432-110">Finding similar customers</span></span>

1. <span data-ttu-id="d0432-111">Στις πληροφορίες κοινού, μεταβείτε στα **Τμήματα** και επιλέξτε το τμήμα στο οποίο θέλετε να βασίσετε το νέο τμήμα.</span><span class="sxs-lookup"><span data-stu-id="d0432-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="d0432-112">Αυτό είναι το *τμήμα προέλευσής* σας.</span><span class="sxs-lookup"><span data-stu-id="d0432-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="d0432-113">Στη γραμμή ενεργειών, επιλέξτε **Εύρεση παρόμοιων πελατών**.</span><span class="sxs-lookup"><span data-stu-id="d0432-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="d0432-114">Ελέγξτε το προτεινόμενο όνομα για το νέο τμήμα και αλλάξτε το, εάν είναι απαραίτητο.</span><span class="sxs-lookup"><span data-stu-id="d0432-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="d0432-115">Ελέγξτε τα πεδία που καθορίζουν το νέο σας τμήμα.</span><span class="sxs-lookup"><span data-stu-id="d0432-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="d0432-116">Αυτά τα πεδία ορίζουν τη βάση στην οποία το σύστημα θα προσπαθήσει να βρει παρόμοιους πελάτες στο τμήμα προέλευσής σας.</span><span class="sxs-lookup"><span data-stu-id="d0432-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="d0432-117">Από προεπιλογή, το σύστημα θα επιλέξει τα συνιστώμενα πεδία.</span><span class="sxs-lookup"><span data-stu-id="d0432-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="d0432-118">Τα πεδία που μπορούν να μειώσουν σημαντικά την απόδοση του μοντέλου εξαιρούνται αυτόματα:</span><span class="sxs-lookup"><span data-stu-id="d0432-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="d0432-119">Πεδία με τους ακόλουθους τύπους δεδομένων: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="d0432-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="d0432-120">Πεδία με προτεραιότητα (ο αριθμός των στοιχείων σε ένα πεδίο) μικρότερη από 2 ή μεγαλύτερη από 30</span><span class="sxs-lookup"><span data-stu-id="d0432-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="d0432-121">Επιλέξτε εάν θέλετε να συμπεριλάβετε **Όλους τους πελάτες** ή μόνο πελάτες σε ένα **Συγκεκριμένο υπάρχον τμήμα** στο νέο τμήμα σας.</span><span class="sxs-lookup"><span data-stu-id="d0432-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="d0432-122">Εξαιρέστε τους πελάτες στο τμήμα προέλευσης επιλέγοντας το πλαίσιο ελέγχου **Εξαίρεση όλων στο τμήμα προέλευσης**.</span><span class="sxs-lookup"><span data-stu-id="d0432-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="d0432-123">Από προεπιλογή, το σύστημα προτείνει την συμπερίληψη μόνο του 20% του μεγέθους του κοινού προορισμού στην έξοδό σας.</span><span class="sxs-lookup"><span data-stu-id="d0432-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="d0432-124">Επεξεργαστείτε αυτό το όριο, όπως απαιτείται.</span><span class="sxs-lookup"><span data-stu-id="d0432-124">Edit this threshold as needed.</span></span> <span data-ttu-id="d0432-125">Η αύξηση του ορίου θα μειώσει την ακρίβεια.</span><span class="sxs-lookup"><span data-stu-id="d0432-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="d0432-126">Επιλέξτε **Εκτέλεση** στο κάτω μέρος της σελίδας για να ξεκινήσετε μια δυαδική εργασία ταξινόμησης (μια μέθοδος Εκμάθηση μηχανής) η οποία αναλύει το σύνολο δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="d0432-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="d0432-127">Προβολή του αντίστοιχου τμήματος</span><span class="sxs-lookup"><span data-stu-id="d0432-127">View the similar segment</span></span>

<span data-ttu-id="d0432-128">Μετά την επεξεργασία του αντίστοιχου τμήματος, θα βρείτε το νέο τμήμα που περιλαμβάνεται στη σελίδα **Τμήματα**.</span><span class="sxs-lookup"><span data-stu-id="d0432-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d0432-129">![Τμήμα παρόμοιων πελατών](media/expanded-segment.png "Τμήμα παρόμοιων πελατών")</span><span class="sxs-lookup"><span data-stu-id="d0432-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="d0432-130">Επιλέξτε **Προβολή** στη γραμμή ενεργειών για να ανοίξετε τις λεπτομέρειες του τμήματος.</span><span class="sxs-lookup"><span data-stu-id="d0432-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="d0432-131">Αυτή η προβολή περιέχει πληροφορίες σχετικά με τη διανομή των αποτελεσμάτων στις [βαθμολογίες ομοιότητας](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="d0432-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="d0432-132">Επίσης, θα βρείτε τις τιμές της βαθμολογίας ομοιότητας στην **Προεπισκόπηση μέλη τμήματος**.</span><span class="sxs-lookup"><span data-stu-id="d0432-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="d0432-133">Χρήση της εξόδου ενός παρόμοιου τμήματος</span><span class="sxs-lookup"><span data-stu-id="d0432-133">Use the output of a similar segment</span></span>

<span data-ttu-id="d0432-134">Μπορείτε να [εργαστείτε με την έξοδο ενός παρόμοιου τμήματος](segments.md) όπως και με άλλα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="d0432-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="d0432-135">Για παράδειγμα, εξαγάγετε το τμήμα ή δημιουργήστε μια μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="d0432-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="d0432-136">Ανανέωση και επεξεργασία παρόμοιου τμήματος</span><span class="sxs-lookup"><span data-stu-id="d0432-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="d0432-137">Για να ανανεώσετε ένα παρόμοιο τμήμα, επιλέξτε το στη σελίδα **Τμήματα** και επιλέξτε **Ανανέωση** στη γραμμή ενεργειών.</span><span class="sxs-lookup"><span data-stu-id="d0432-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="d0432-138">Με την επεξεργασία ενός παρόμοιου τμήματος θα γίνει ξανά επεξεργασία των δεδομένων σας.</span><span class="sxs-lookup"><span data-stu-id="d0432-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="d0432-139">Γίνεται ενημέρωση του τμήματος που δημιουργήθηκε προηγουμένως με ανανεωμένα δεδομένα.</span><span class="sxs-lookup"><span data-stu-id="d0432-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="d0432-140">Για να επεξεργαστείτε ένα παρόμοιο τμήμα, επιλέξτε το στη σελίδα **Τμήματα** και επιλέξτε **Επεξεργασία** στη γραμμή ενεργειών.</span><span class="sxs-lookup"><span data-stu-id="d0432-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="d0432-141">Εφαρμόστε τις αλλαγές σας και επιλέξτε **Εκτέλεση** για να ξεκινήσετε την επεξεργασία.</span><span class="sxs-lookup"><span data-stu-id="d0432-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="d0432-142">Διαγραφή παρόμοιου τμήματος</span><span class="sxs-lookup"><span data-stu-id="d0432-142">Delete a similar segment</span></span>

<span data-ttu-id="d0432-143">Επιλέξτε το τμήμα στη σελίδα **Τμήματα** και επιλέξτε **Διαγραφή** στη γραμμή ενεργειών.</span><span class="sxs-lookup"><span data-stu-id="d0432-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="d0432-144">Στη συνέχεια, επιβεβαιώστε τη διαγραφή.</span><span class="sxs-lookup"><span data-stu-id="d0432-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="d0432-145">Πληροφορίες για τις βαθμολογίες ομοιότητας</span><span class="sxs-lookup"><span data-stu-id="d0432-145">About similarity scores</span></span>

<span data-ttu-id="d0432-146">Το μοντέλο δυαδικής ταξινόμησης Εκμάθηση μηχανής αντιστοιχίζει μια βαθμολογία σε πελάτες παρόμοιου τμήματος.</span><span class="sxs-lookup"><span data-stu-id="d0432-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="d0432-147">Η βαθμολογία βασίζεται στην ομοιότητα με τους πελάτες στο τμήμα προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="d0432-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="d0432-148">Οι βαθμολογίες ομοιότητας κάτω του 0,55 είναι πελάτες που το σύστημα ταξινόμησε ως *δεν είναι παρόμοιοι* με τους πελάτες στο τμήμα προέλευσης</span><span class="sxs-lookup"><span data-stu-id="d0432-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="d0432-149">Οι βαθμολογίες ομοιότητας μεταξύ 0,55 – 0,7 ταξινομούνται ως *κάπως παρόμοιοι*</span><span class="sxs-lookup"><span data-stu-id="d0432-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="d0432-150">Οι βαθμολογίες ομοιότητας μεταξύ 0,7 – 0,85 ταξινομούνται ως *παρόμοιοι*</span><span class="sxs-lookup"><span data-stu-id="d0432-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="d0432-151">Οι βαθμολογίες ομοιότητας μεταξύ 0,85 – 1 είναι πελάτες που το σύστημα ταξινόμησε ως *πολύ παρόμοιοι*</span><span class="sxs-lookup"><span data-stu-id="d0432-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="d0432-152">Οι πελάτες με βαθμολογίες ομοιότητας κάτω από 0,4 δεν περιλαμβάνονται στην έξοδο του μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="d0432-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="d0432-153">Το σύστημα δεν τους θεωρεί αρκετά παρόμοιους με το τμήμα προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="d0432-153">The system doesn't consider them similar enough to the source segment.</span></span>
