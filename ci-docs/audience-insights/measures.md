---
title: Δημιουργία και επεξεργασία μετρήσεων
description: Καθορίστε μετρήσεις που σχετίζονται με πελάτες για να αναλύσετε και να απεικονίσετε την απόδοση ορισμένων επιχειρηματικών περιοχών.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405850"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="7d9f0-103">Καθορισμός και διαχείριση μέτρων</span><span class="sxs-lookup"><span data-stu-id="7d9f0-103">Define and manage measures</span></span>

<span data-ttu-id="7d9f0-104">Οι **Μετρήσεις** αντιπροσωπεύουν βασικούς δείκτες επιδόσεων (KPI) που αντικατοπτρίζουν την απόδοση και την υγεία συγκεκριμένων επιχειρηματικών περιοχών.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="7d9f0-105">Οι πληροφορίες κοινού παρέχουν μια διαισθητική εμπειρία για τη δημιουργία διαφορετικών τύπων μέτρων, χρησιμοποιώντας ένα εργαλείο δόμησης ερωτημάτων που δεν απαιτεί να κωδικοποιήσετε ή να επικυρώσετε τις μετρήσεις σας με μη αυτόματο τρόπο.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="7d9f0-106">Μπορείτε να παρακολουθήσετε τις επιχειρηματικές σας μετρήσεις στην **Αρχική** σελίδα, να δείτε μετρήσεις για συγκεκριμένους πελάτες **Καρτέλα πελάτη** και να χρησιμοποιήσετε μετρήσεις για να καθορίσετε τμήματα πελατών στη σελίδα **Τμήματα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="7d9f0-107">Δημιουργία νέας μέτρησης</span><span class="sxs-lookup"><span data-stu-id="7d9f0-107">Create a measure</span></span>

<span data-ttu-id="7d9f0-108">Αυτή η ενότητα περιέχει οδηγίες για τη δημιουργία μιας μέτρησης από την αρχή.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="7d9f0-109">Μπορείτε να δομήσετε μετρήσεις με δεδομένα από πολλαπλές προελεύσεις δεδομένων που είναι συνδεδεμένες μέσω της οντότητας Πελάτης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="7d9f0-110">Ισχύουν ορισμένα [όρια εξυπηρέτησης](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="7d9f0-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="7d9f0-111">Στις πληροφορίες κοινού, μεταβείτε στις **Μετρήσεις**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="7d9f0-112">Επιλέξτε **Νέα μέτρηση**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-112">Select **New measure**.</span></span>

3. <span data-ttu-id="7d9f0-113">Επιλέξτε τη μέτρηση **Τύπος**:</span><span class="sxs-lookup"><span data-stu-id="7d9f0-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="7d9f0-114">**Χαρακτηριστικό πελάτη**: Ένα μεμονωμένο πεδίο ανά πελάτη που αντικατοπτρίζει μια βαθμολογία, μια τιμή ή μια κατάσταση για τον πελάτη.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="7d9f0-115">Τα χαρακτηριστικά πελατών δημιουργούνται ως χαρακτηριστικά σε μια νέα οντότητα που δημιουργείται από το σύστημα και ονομάζεται **Μέτρηση πελάτη**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="7d9f0-116">**Μέτρηση πελάτη**: Γνώσεις για τη συμπεριφορά πελατών με κατανομή ανά επιλεγμένες διαστάσεις.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="7d9f0-117">Δημιουργείται μια νέα οντότητα για κάθε μέτρηση, ενδεχομένως με πολλές καρτέλες ανά πελάτη.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="7d9f0-118">**Μέτρηση επιχείρησης**: Παρακολουθεί την επιχειρηματική σας απόδοση και την εύρυθμη λειτουργία της επιχείρησης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="7d9f0-119">Οι επιχειρηματικές μετρήσεις μπορεί να έχουν δύο διαφορετικές εξόδους: μια αριθμητική έξοδο που εμφανίζεται στην **Αρχική** σελίδα ή μια νέα οντότητα που βρίσκετε στη σελίδα **Οντότητες**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="7d9f0-120">δώστε ένα **Όνομα** και ένα προαιρετικό **Εμφανιζόμενο όνομα** και στη συνέχεια επιλέξτε **Επόμενο**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="7d9f0-121">Στην ενότητα **Οντότητες**, επιλέξτε την πρώτη οντότητα από την αναπτυσσόμενη λίστα.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="7d9f0-122">Σε αυτό το σημείο, θα πρέπει να αποφασίσετε εάν απαιτούνται πρόσθετες οντότητες ως μέρος του ορισμού της μέτρησης σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d9f0-123">![Ορισμός μέτρησης](media/measure-definition.png "Ορισμός μέτρησης")</span><span class="sxs-lookup"><span data-stu-id="7d9f0-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="7d9f0-124">Για να προσθέσετε και άλλες οντότητες, επιλέξτε **Προσθήκη οντότητας** και επιλέξτε οντότητες που θέλετε να χρησιμοποιήσετε για τη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7d9f0-125">Μπορείτε να επιλέξετε μόνο τις οντότητες που έχουν σχέσεις με την αρχική σας οντότητα.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="7d9f0-126">Για περισσότερες πληροφορίες σχετικά με τον καθορισμό σχέσεων ανατρέξτε στις [Σχέσεις](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="7d9f0-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="7d9f0-127">Προαιρετικά, μπορείτε να ρυθμίσετε τις παραμέτρους των μεταβλητών.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="7d9f0-128">Στην ενότητα **Μεταβλητές** επιλέξτε **Νέα μεταβλητή**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="7d9f0-129">Οι μεταβλητές είναι υπολογισμοί που πραγματοποιούνται σε κάθε μία από τις επιλεγμένες καρτέλες σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="7d9f0-130">Για παράδειγμα, η άθροιση του σημείου πώλησης (POS) και οι ηλεκτρονικές πωλήσεις για κάθε μία από τις καρτέλες των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="7d9f0-131">Καταχωρήστε ένα **Όνομα** για τη μεταβλητή.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="7d9f0-132">Στην περιοχή **Έκφραση** επιλέξτε ένα πεδίο για να ξεκινήσετε τον υπολογισμό σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="7d9f0-133">Πληκτρολογήστε μια έκφραση στην περιοχή **Έκφραση** ενώ επιλέγετε περισσότερα πεδία που θα συμπεριληφθούν στον υπολογισμό σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7d9f0-134">Προς το παρόν, υποστηρίζονται μόνο αριθμητικές παραστάσεις.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="7d9f0-135">Επιπλέον, ο υπολογισμός μεταβλητών δεν υποστηρίζεται για οντότητες από διαφορετικές [διαδρομές οντοτήτων](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="7d9f0-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="7d9f0-136">Επιλέξτε **Τέλος**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-136">Select **Done**.</span></span>

11. <span data-ttu-id="7d9f0-137">Στην ενότητα **"Ορισμός μέτρησης** θα καθορίσετε τον τρόπο με τον οποίο οι επιλεγμένες οντότητες και οι υπολογιζόμενες μεταβλητές θα ομαδοποιηθούν σε μια νέα οντότητα ή χαρακτηριστικό μέτρησης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="7d9f0-138">Επιλέξτε **Νέα διάσταση**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-138">Select **New dimension**.</span></span> <span data-ttu-id="7d9f0-139">Μπορείτε να θεωρήσετε την διάσταση ως μια συνάρτηση *ομαδοποίηση κατά*.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="7d9f0-140">Η έξοδος δεδομένων της οντότητας ή του χαρακτηριστικού Μέτρησης θα ομαδοποιηθεί κατά όλες τις καθορισμένες διαστάσεις σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7d9f0-141">![Επιλέξτε κύκλο συγκέντρωσης](media/measures-businessreport-measure-definition2.png "Επιλέξτε κύκλο συγκέντρωσης")</span><span class="sxs-lookup"><span data-stu-id="7d9f0-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="7d9f0-142">Επιλέξτε ή καταχωρήστε τις παρακάτω πληροφορίες ως μέρος του ορισμού της διάστασης σας:</span><span class="sxs-lookup"><span data-stu-id="7d9f0-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="7d9f0-143">**Οντότητα**: Εάν καθορίσετε μια οντότητα Μέτρηση, θα πρέπει να περιλαμβάνει τουλάχιστον ένα χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="7d9f0-144">Εάν καθορίσετε ένα χαρακτηριστικό Μέτρησης, αυτό θα περιλαμβάνει εξ ορισμού μόνο ένα χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="7d9f0-145">Αυτή η επιλογή αφορά στην επιλογή της οντότητας που περιλαμβάνει αυτό το χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="7d9f0-146">**Πεδίο**: Επιλέξτε το συγκεκριμένο χαρακτηριστικό που θα συμπεριληφθεί είτε στην οντότητα είτε στο χαρακτηριστικό Μέτρησης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="7d9f0-147">**Κάδος**: Επιλέξτε εάν θέλετε να αθροίσετε δεδομένα σε ημερήσια, μηνιαία ή ετήσια βάση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="7d9f0-148">Πρόκειται για μια απαιτούμενη επιλογή μόνο εάν έχετε επιλέξει ένα χαρακτηριστικό τύπου ημερομηνίας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="7d9f0-149">**Ως**: Καθορίζει το όνομα του νέου πεδίου σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="7d9f0-150">**Εμφανιζόμενο όνομα**: Καθορίζει τη εμφανιζόμενο όνομα του πεδίου σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d9f0-151">Το μέτρο της επιχείρησής σας θα αποθηκευτεί ως οντότητα με ένα και μόνο αριθμό και θα εμφανιστεί στην **Αρχική** σελίδα, εκτός εάν προσθέσετε περισσότερες διαστάσεις στη μέτρησή σας.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="7d9f0-152">Αφού προσθέσετε περισσότερες διαστάσεις, η μέτρηση *δεν* θα εμφανιστεί στην **Αρχική** σελίδα.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="7d9f0-153">Προαιρετικά, προσθέστε συναρτήσεις συνάθροισης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="7d9f0-154">Κάθε συνάθροιση που δημιουργείτε έχει ως αποτέλεσμα μια νέα τιμή εντός της οντότητας ή του χαρακτηριστικού Μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="7d9f0-155">Οι υποστηριζόμενες συναρτήσεις συνάθροισης: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (λαμβάνει την πρώτη καρτέλα μιας τιμής διάστασης), και **Last** (λαμβάνει την τελευταία καρτέλα που προστίθεται σε μια τιμή διάστασης).</span><span class="sxs-lookup"><span data-stu-id="7d9f0-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="7d9f0-156">Επιλέξτε **Αποθήκευση** για να εφαρμόσετε τις αλλαγές στη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="7d9f0-157">Διαχείριση των μετρήσεών σας</span><span class="sxs-lookup"><span data-stu-id="7d9f0-157">Manage your measures</span></span>

<span data-ttu-id="7d9f0-158">Αφού δημιουργήσετε τουλάχιστον μία μέτρηση, θα δείτε μια λίστα μετρήσεων στη σελίδα **Μετρήσεις**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="7d9f0-159">Θα βρείτε πληροφορίες σχετικά με τον τύπο της μέτρησης, το δημιουργό, την ημερομηνία και την ώρα δημιουργίας, την ημερομηνία και την ώρα τελευταίας επεξεργασίας, την κατάσταση (εάν η μέτρηση είναι ενεργή, ανενεργή ή αποτυχημένη) και την ημερομηνία και την ώρα τελευταίας ανανέωσης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="7d9f0-160">Όταν επιλέγετε ένα μια μέτρηση από τη λίστα, μπορείτε να δείτε μια προεπισκόπηση του αποτελέσματος.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="7d9f0-161">Για να ανανεώσετε ταυτόχρονα όλες τις μετρήσεις σας, επιλέξτε **Ανανέωση όλων** χωρίς να επιλέξετε μια συγκεκριμένη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7d9f0-162">![Ενέργειες για τη διαχείριση μεμονωμένων μετρήσεων](media/measure-actions.png "Ενέργειες για τη διαχείριση μεμονωμένων μετρήσεων")</span><span class="sxs-lookup"><span data-stu-id="7d9f0-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="7d9f0-163">Εναλλακτικά, επιλέξτε μια μέτρηση από τη λίστα και εκτελέστε μία από τις ακόλουθες ενέργειες:</span><span class="sxs-lookup"><span data-stu-id="7d9f0-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="7d9f0-164">Επιλέξτε το όνομα της μέτρησης για να δείτε τις λεπτομέρειές της.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="7d9f0-165">**Επεξεργαστείτε** τη ρύθμιση παραμέτρων της μέτρησης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="7d9f0-166">**Μετονομάστε** τη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-166">**Rename** the measure.</span></span>
- <span data-ttu-id="7d9f0-167">**Διαγράψτε** τη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-167">**Delete** the measure.</span></span>
- <span data-ttu-id="7d9f0-168">Επιλέξτε την έλλειψη (...) και, στη συνέχεια, κάντε **Ανανέωση** για να ξεκινήσετε τη διεργασία ανανέωσης για τη μέτρηση.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="7d9f0-169">Επιλέξτε την έλλειψη (...) και, στη συνέχεια, κάντε **Λήψη** για να λάβετε ένα αρχείο .CSV της μέτρησης.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="7d9f0-170">Υπάρχουν [έξι τύποι κατάστασης](system.md#status-types) για εργασίες/διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7d9f0-171">Επιπλέον, οι περισσότερες διεργασίες [εξαρτώνται από άλλες διεργασίες κατάντη](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7d9f0-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7d9f0-172">Μπορείτε να επιλέξετε την κατάσταση μιας διεργασίας για να δείτε λεπτομέρειες σχετικά με την πρόοδο ολόκληρου του έργου.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7d9f0-173">Αφού επιλέξετε **Προβολή λεπτομερειών** για μία από τις εργασίες του έργου, μπορείτε να βρείτε πρόσθετες πληροφορίες: χρόνος επεξεργασίας, ημερομηνία τελευταίας επεξεργασίας και όλα τα σφάλματα και τις προειδοποιήσεις που σχετίζονται με την εργασία.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="7d9f0-174">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="7d9f0-174">Next step</span></span>

<span data-ttu-id="7d9f0-175">Μπορείτε να χρησιμοποιήσετε υπάρχουσες μετρήσεις για τη δημιουργία του πρώτου τμήματος πελατών σας στη σελίδα **Τμήματα αγοράς**.</span><span class="sxs-lookup"><span data-stu-id="7d9f0-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="7d9f0-176">Για περισσότερες πληροφορίες, δείτε [Τμήματα αγοράς](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7d9f0-176">For more information, see [Segments](segments.md).</span></span>
