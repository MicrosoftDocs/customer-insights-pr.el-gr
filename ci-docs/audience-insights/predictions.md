---
title: Ολοκλήρωση μερικών δεδομένων με χρήση προβλέψεων
description: Χρήση των προβλέψεων για τη συμπλήρωση μη ολοκληρωμένων δεδομένων πελατών.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648711"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="f7d4b-103">Ολοκληρώστε τα μερικά δεδομένα σας με προβλέψεις</span><span class="sxs-lookup"><span data-stu-id="f7d4b-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f7d4b-104">Οι προβλέψεις σάς επιτρέπουν να δημιουργείτε εύκολα προβλέψιμες τιμές που μπορούν να βελτιώσουν την κατανόησή σας για έναν πελάτη.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="f7d4b-105">Στη σελίδα **Ευφυΐα** > **Προβλέψεις**, μπορείτε να επιλέξετε **Οι προβλέψις μου** για να δείτε τις προβλέψεις που έχετε ρυθμίσει σε άλλα τμήματα των πληροφοριών κοινού και σας επιτρέπουν να τις προσαρμόσετε περαιτέρω.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="f7d4b-106">Δεν μπορείτε να χρησιμοποιήσετε αυτήν τη δυνατότητα εάν το περιβάλλον σας χρησιμοποιεί χώρο αποθήκευσης Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="f7d4b-107">Η δυνατότητα "προβλέψεις" χρησιμοποιεί αυτοματοποιημένα μέσα για την αξιολόγηση δεδομένων και την πραγματοποίηση προβλέψεων με βάση τα εν λόγω δεδομένα και επομένως έχει τη δυνατότητα να χρησιμοποιηθεί ως μέθοδος δημιουργίας προφίλ, όπως ορίζεται αυτός ο όρος από τον Γενικό κανονισμό για την προστασία των δεδομένων ("ΓΚΠΔ").</span><span class="sxs-lookup"><span data-stu-id="f7d4b-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="f7d4b-108">Η χρήση αυτής της δυνατότητας από τον πελάτη για την επεξεργασία των δεδομένων μπορεί να υπόκειται στον ΓΚΠΔ ή άλλες νομοθεσίες ή κανονισμούς.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="f7d4b-109">Είστε υπεύθυνοι για τη διασφάλιση ότι η χρήση του Dynamics 365 Customer Insights, συμπεριλαμβανομένων προβλέψεων, συμμορφώνεται με όλους τους ισχύοντες νόμους και κανονισμούς, συμπεριλαμβανομένων των νόμων που σχετίζονται με την προστασία της ιδιωτικής ζωής, τα προσωπικά δεδομένα, τα βιομετρικά δεδομένα, την προστασία των δεδομένων και την εμπιστευτικότητα των επικοινωνιών.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7d4b-110">Προαπαιτούμενα στοιχεία</span><span class="sxs-lookup"><span data-stu-id="f7d4b-110">Prerequisites</span></span>

<span data-ttu-id="f7d4b-111">Για να είναι δυνατή η χρήση της δυνατότητας "προβλέψεις" για τον οργανισμό σας, βεβαιωθείτε ότι πληρούνται οι ακόλουθες προϋποθέσεις:</span><span class="sxs-lookup"><span data-stu-id="f7d4b-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="f7d4b-112">Ο οργανισμός σας έχει μια παρουσία [που έχει ρυθμιστεί στο Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) και είναι στον ίδιο οργανισμό με το Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="f7d4b-113">Το περιβάλλον σας επισυνάπτεται στην παρουσία του Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="f7d4b-114">Εάν [δημιουργείτε ένα νέο περιβάλλον](manage-environments.md), ρυθμίστε τις παραμέτρους του στο παράθυρο διαλόγου **Δημιουργία ενός περιβάλλοντος** και επιλέξτε **Για προχωρημένους**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="f7d4b-115">Εάν έχετε ήδη δημιουργήσει ένα περιβάλλον, μεταβείτε στις ρυθμίσεις του και επιλέξτε **Για προχωρημένους**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="f7d4b-116">Είτε έτσι είτε αλλιώς, στην ενότητα **Χρήση προβλέψεων**, εισαγάγετε τη διεύθυνση URL της παρουσίας του Common Data Service στην οποία θέλετε να επισυνάψετε το περιβάλλον σας.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="f7d4b-117">Δημιουργία πρόβλεψης στην οντότητα πελάτη</span><span class="sxs-lookup"><span data-stu-id="f7d4b-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="f7d4b-118">Στις πληροφορίες κοινού, μεταβείτε στα **Δεδομένα** > **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="f7d4b-119">Επιλέξτε την οντότητα **Πελάτης**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="f7d4b-120">Στην οντότητα **Πελάτης: CustomerInsights**, επιλέξτε την καρτέλα **Πεδία**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="f7d4b-121">Βρείτε το όνομα του χαρακτηριστικού για το οποίο θέλετε να προβλέψετε τιμές, έπειτα επιλέξτε το εικονίδιο **Επισκόπηση** στη στήλη **Σύνοψη**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7d4b-122">![Εικονίδιο επισκόπησης](media/intelligence-overviewicon.png "Εικονίδιο επισκόπησης")</span><span class="sxs-lookup"><span data-stu-id="f7d4b-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="f7d4b-123">Εάν υπάρχει ένα υψηλό ποσοστό αγνοουμένων τιμών για το χαρακτηριστικό σας, επιλέξτε **Πρόβλεψη τιμών που λείπουν** για να συνεχίσετε με την πρόβλεψή σας.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7d4b-124">![Εμφανίζεται το κουμπί "Επισκόπηση κατάστασης με πρόβλεψη τιμών που λείπουν"](media/intelligence-overviewpredictmissingvalues.png "Εμφανίζεται το κουμπί "Επισκόπηση κατάστασης με πρόβλεψη τιμών που λείπουν"")</span><span class="sxs-lookup"><span data-stu-id="f7d4b-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="f7d4b-125">Δώστε ένα **Εμφανιζόμενο όνομα** και ένα **Όνομα οντότητας εξόδου** για τα αποτελέσματα της πρόβλεψης.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="f7d4b-126">Μια προ-συμπληρωμένη λίστα επιλογών θα σας δείξει πού μπορείτε να αντιστοιχίσετε τις τιμές σε μια αναμενόμενη κατηγορία.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="f7d4b-127">Σε αυτήν την περίπτωση, οι μόνες επιλογές κατηγορίας σας θα είναι 0 ή 1 καθώς αντιστοιχίζονται με την αληθή/ψευδή ή δυαδική φύση της πρόβλεψης.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="f7d4b-128">Στη στήλη Κατηγορίας, αντιστοιχίστε τις τιμές των πεδίων που θα θέλατε να ταξινομηθούν ως "0" στην τελική πρόβλεψη στο "0" στη στήλη "κατηγορία" και τα στοιχεία που θα θέλατε να ταξινομηθούν ως "1" στην τελική πρόβλεψη για το "1".</span><span class="sxs-lookup"><span data-stu-id="f7d4b-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7d4b-129">![Παράδειγμα εμφάνισης αντιστοιχισμένων τιμών πεδίων σε κατηγορίες](media/intelligence-categorymapping.png "Παράδειγμα εμφάνισης αντιστοιχισμένων τιμών πεδίων σε κατηγορίες")</span><span class="sxs-lookup"><span data-stu-id="f7d4b-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="f7d4b-130">Επιλέξτε **Τέλος** και θα γίνει επεξεργασία της πρόβλεψης.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="f7d4b-131">Η επεξεργασία θα διαρκέσει αρκετό χρόνο, ανάλογα με το μέγεθος και την πολυπλοκότητα των δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="f7d4b-132">Τα αποτελέσματα θα είναι διαθέσιμα σε μια νέα οντότητα με βάση το **Όνομα της οντότητας εξόδου** της πρόβλεψης που δημιουργήσατε.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="f7d4b-133">Δημιουργία πρόβλεψης κατά τη δημιουργία ενός τμήματος</span><span class="sxs-lookup"><span data-stu-id="f7d4b-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="f7d4b-134">Η πρόβλεψη των τιμών που λείπουν για ένα συγκεκριμένο χαρακτηριστικό επιλογής είναι επίσης δυνατή κατά τη δημιουργία ενός τμήματος.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="f7d4b-135">Συγκεκριμένα, όταν δημιουργείτε γρήγορα ένα τμήμα με βάση είτε την ενοποιημένη οντότητα πελάτη είτε την οντότητα Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="f7d4b-136">Ως μέρος αυτής της ροής, επιλέγετε ένα συγκεκριμένο χαρακτηριστικό για να βασίζετε το τμήμα σας, όπως η ικανοποίηση του πελάτη, το ποσό αγοράς ή οποιοδήποτε χαρακτηριστικό προτίμησής σας.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="f7d4b-137">Μετά τη δημιουργία τμήματος, το σύστημα θα προτείνει μια μέθοδο για την πρόβλεψη των τιμών που λείπουν για αυτό το χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="f7d4b-138">Στις πληροφορίες κοινού, μεταβείτε στα **Τμήματα** και επιλέξτε το πλακίδιο **Προφίλ**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="f7d4b-139">Επιλέξτε ένα **Πεδίο** για να δημιουργήσετε ένα τμήμα και επιλέξτε έναν **Τελεστή** και, στη συνέχεια , επιλέξτε **Επανεξέταση**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="f7d4b-140">Δώστε ένα **Όνομα** και ένα **Εμφανιζόμενο όνομα** για το τμήμα.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="f7d4b-141">Επιλέξτε **Αποθήκευση**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-141">Select **Save**.</span></span>

5. <span data-ttu-id="f7d4b-142">Εάν το τμήμα που μόλις δημιουργήσατε έχει ελλιπή δεδομένα στο πεδίο προέλευσης, μπορείτε να επιλέξετε να προβλέψετε τις τιμές που λείπουν.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7d4b-143">![Κουμπί πρόβλεψης](media/segments-predictoption.png "Κουμπί πρόβλεψης")</span><span class="sxs-lookup"><span data-stu-id="f7d4b-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="f7d4b-144">Δώστε ένα **Εμφανιζόμενο όνομα** και ένα **Όνομα οντότητας εξόδου** για τα αποτελέσματα της πρόβλεψης.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="f7d4b-145">Επιλέξτε **Τέλος**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-145">Select **Done**.</span></span> <span data-ttu-id="f7d4b-146">Η πρόβλεψή σας θα δημιουργηθεί σύντομα και θα είναι διαθέσιμη σε μια νέα οντότητα με το όνομα που παρείχατε για το **Όνομα της οντότητας εξόδου**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="f7d4b-147">Προβολή πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="f7d4b-147">View a prediction</span></span>

1. <span data-ttu-id="f7d4b-148">Στις πληροφορίες κοινού, μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** > **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="f7d4b-149">Επιλέξτε την πρόβλεψη που θέλετε να επανεξετάσετε.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="f7d4b-150">Επιλέξτε την έλλειψη στη στήλη **Ενέργειες** και επιλέξτε **Προβολή**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="f7d4b-151">Θα δείτε έναν αριθμό σημείων δεδομένων στην προβολή της πρόβλεψής σας.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7d4b-152">![Σελίδα προβλέψεων](media/intelligence-predictionsviewpage.png "Σελίδα προβλέψεων")</span><span class="sxs-lookup"><span data-stu-id="f7d4b-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="f7d4b-153">**Οι αναμενόμενες τιμές** δείχνουν την αντιστοίχιση που δημιουργήσατε κατά τη διάρκεια της τιμής πεδίου στη φάση αντιστοίχισης κατηγοριών.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="f7d4b-154">Θα εμφανιστούν οι τιμές στο σύνολο δεδομένων σας που έχουν αντιστοιχιστεί σε μια συγκεκριμένη κατηγορία.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="f7d4b-155">-**Οι κορυφαίοι παράγοντες επηρεασμού** είναι οι παράγοντες εντός του σύνολο δεδομένων σας που ήταν πιθανότερο να επηρεάσουν την εμπιστοσύνη της πρόβλεψης για την τιμή του πεδίου σας που αντιστοιχίζεται σε μια συγκεκριμένη κατηγορία.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="f7d4b-156">**Οι επιδόσεις** δείχνουν τον τρόπο με τον οποίο εκτελούνται οι προβλέψεις.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="f7d4b-157">Επιλέξτε τον σύνδεσμο για να μάθετε περισσότερα.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="f7d4b-158">**Η προεπισκόπηση** δείχνει τα δείγματα του συνόλου δεδομένων εξόδου από την πρόβλεψή σας και την πιθανότητα ή την εμπιστοσύνη μας σχετικά με την αναμενόμενη τιμή όπου το 0 είναι αβέβαιο και το 1 είναι βέβαιο.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="f7d4b-159">Ενημέρωση μιας πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="f7d4b-159">Update a prediction</span></span>

1. <span data-ttu-id="f7d4b-160">Στις πληροφορίες κοινού, μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** > **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="f7d4b-161">Επιλέξτε την πρόβλεψη που θέλετε να ενημερώσετε και επιλέξτε το εικονίδιο **Ενημέρωση**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="f7d4b-162">Η πρόβλεψη θα προγραμματιστεί για επεξεργασία.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="f7d4b-163">Μπορείτε να δείτε την ώρα που ενημερώθηκε τελευταία στη στήλη **Ενημερωμένο** της σελίδας **Προβλέψεις**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="f7d4b-164">Επεξεργασία πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="f7d4b-164">Edit a prediction</span></span>

<span data-ttu-id="f7d4b-165">Αφού δημιουργήσετε μια πρόβλεψη, μπορείτε να προσαρμόσετε το μοντέλο στο AI Builder για να αυξήσετε την αποτελεσματικότητα του μοντέλου σας.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="f7d4b-166">Στις πληροφορίες κοινού, μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** > **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="f7d4b-167">Επιλέξτε την πρόβλεψη που θέλετε να επεξεργαστείτε.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="f7d4b-168">Επιλέξτε την έλλειψη στη στήλη **Ενέργειες** και επιλέξτε **Προβολή**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="f7d4b-169">Επιλέξτε **Προσαρμογή στο AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="f7d4b-170">Ενημερώστε το μοντέλο σας στο AI Builder.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="f7d4b-171">[Μάθετε περισσότερα σχετικά με τη διαχείριση μοντέλων στο AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="f7d4b-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="f7d4b-172">Η επόμενη εκτέλεση της πρόβλεψής σας θα χρησιμοποιήσει το ενημερωμένο μοντέλο που δημιουργήσατε.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="f7d4b-173">Τα νέα μοντέλα που δημιουργούνται στο AI Builder δεν θα εμφανίζονται στις πληροφορίες κοινού, εκτός εάν το μοντέλο δημιουργήθηκε από τις εμπειρίες που παρατέθηκαν παραπάνω.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="f7d4b-174">Κατάργηση μιας πρόβλεψης</span><span class="sxs-lookup"><span data-stu-id="f7d4b-174">Remove a prediction</span></span>

1. <span data-ttu-id="f7d4b-175">Στις πληροφορίες κοινού, μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** > **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="f7d4b-176">Επιλέξτε την πρόβλεψη που θέλετε να διαγράψετε.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="f7d4b-177">Επιλέξτε την έλλειψη στη στήλη **Ενέργειες** και επιλέξτε **Διαγραφή**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="f7d4b-178">Επιβεβαιώστε τη διαγραφή.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f7d4b-179">Αντιμετώπιση προβλημάτων</span><span class="sxs-lookup"><span data-stu-id="f7d4b-179">Troubleshooting</span></span>

<span data-ttu-id="f7d4b-180">Εάν δεν μπορείτε να ολοκληρώσετε τη διεργασία επισύναψης του Common Data Service λόγω σφάλματος, μπορείτε να επιχειρήσετε να ολοκληρώσετε τη διαδικασία με μη αυτόματο τρόπο.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="f7d4b-181">Υπάρχουν δύο γνωστά ζητήματα που μπορεί να προκύψουν στη διαδικασία επισύναψης:</span><span class="sxs-lookup"><span data-stu-id="f7d4b-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="f7d4b-182">Η λύση πρόσθετου κάρτας πελάτη δεν έχει εγκατασταθεί.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="f7d4b-183">Ολοκληρώστε τις οδηγίες για την [εγκατάσταση και τη ρύθμιση παραμέτρων της λύσης](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="f7d4b-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="f7d4b-184">Δεν εκχωρούνται δικαιώματα εφαρμογής.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="f7d4b-185">Μετάβαση στο [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f7d4b-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="f7d4b-186">Επιλέξτε **Περιβάλλοντα**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="f7d4b-187">Επιλέξτε την έλλειψη δίπλα στο περιβάλλον στο οποίο θέλετε να προσθέσετε το δικαίωμα και επιλέξτε **Ρυθμίσεις**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="f7d4b-188">Αναπτύξτε το στοιχείο **Χρήστες + δικαιώματα** και επιλέξτε **Χρήστες**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="f7d4b-189">Επιλέξτε **+ Νέος** και επιλέξτε **Χρήστης**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="f7d4b-190">Επιλέξτε **Χρήστης εφαρμογής** εάν δεν είναι ήδη επιλεγμένος και καταχωρίστε τις παρακάτω πληροφορίες:</span><span class="sxs-lookup"><span data-stu-id="f7d4b-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="f7d4b-191">**Όνομα χρήστη:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f7d4b-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="f7d4b-192">**Αναγνωριστικό εφαρμογής:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="f7d4b-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="f7d4b-193">**Όνομα:** Πελάτης</span><span class="sxs-lookup"><span data-stu-id="f7d4b-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="f7d4b-194">**Επώνυμο:** Insights</span><span class="sxs-lookup"><span data-stu-id="f7d4b-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="f7d4b-195">**Κύρια διεύθυνση ηλεκτρονικού ταχυδρομείου:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f7d4b-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="f7d4b-196">Επιλέξτε **Αποθήκευση και κλείσιμο**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="f7d4b-197">Επιλέξτε τον χρήστη που μόλις δημιουργήσατε.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="f7d4b-198">Επιλέξτε **Διαχείριση ρόλων** στην επάνω γραμμή μενού.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="f7d4b-199">Επιλέξτε **Διαχειριστής συστήματος** και, στη συνέχεια, κάντε κλικ στο **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7d4b-199">Select **System Administrator**, then select **OK**.</span></span>
