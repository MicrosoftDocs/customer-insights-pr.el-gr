---
title: Σχέσεις μεταξύ οντοτήτων και διαδρομές οντοτήτων
description: Δημιουργήστε και διαχειριστείτε σχέσεις μεταξύ οντοτήτων από πολλαπλές προελεύσεις δεδομένων.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595212"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="bbc87-103">Σχέσεις μεταξύ οντοτήτων</span><span class="sxs-lookup"><span data-stu-id="bbc87-103">Relationships between entities</span></span>

<span data-ttu-id="bbc87-104">Οι σχέσεις σας βοηθήσουν να συνδέσετε οντότητες και να δημιουργήσετε ένα γράφημα των δεδομένων σας, όταν οι οντότητες κάνουν κοινή χρήση ενός κοινού αναγνωριστικού (εξωτερικού κλειδιού), το οποίο μπορεί να αναφέρεται από μια οντότητα σε μια άλλη.</span><span class="sxs-lookup"><span data-stu-id="bbc87-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="bbc87-105">Οι συνδεδεμένες οντότητες σάς δίνουν τη δυνατότητα να καθορίσετε τμήματα και μετρήσεις με βάση πολλαπλές προελεύσεις δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="bbc87-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="bbc87-106">Υπάρχουν δύο τύποι σχέσεων.</span><span class="sxs-lookup"><span data-stu-id="bbc87-106">There are two types of relationships.</span></span> <span data-ttu-id="bbc87-107">Σχέσεις συστήματος που δεν είναι επεξεργάσιμες, οι οποίες δημιουργούνται αυτόματα και προσαρμοσμένες σχέσεις που έχουν δημιουργηθεί και ρυθμιστεί από χρήστες.</span><span class="sxs-lookup"><span data-stu-id="bbc87-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="bbc87-108">Κατά τη διάρκεια των διεργασιών αντιστοίχισης και συγχώνευσης, οι σχέσεις συστήματος δημιουργούνται παρασκηνιακά με βάση ευφυή αντιστοίχιση.</span><span class="sxs-lookup"><span data-stu-id="bbc87-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="bbc87-109">Αυτές οι σχέσεις συμβάλουν στη συσχέτιση των καρτελών Προφίλ πελατών με άλλες καρτέλες αντίστοιχων οντοτήτων.</span><span class="sxs-lookup"><span data-stu-id="bbc87-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="bbc87-110">Στο ακόλουθο διάγραμμα απεικονίζεται η δημιουργία τριών συστημάτων σχέσεων, όταν η οντότητα πελάτη συνδυάζεται με πρόσθετες οντότητες για να δημιουργήσει την τελική οντότητα Προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="bbc87-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bbc87-111">![Δημιουργία σχέσης](media/relationships-entities-merge.png "Δημιουργία σχέσης")</span><span class="sxs-lookup"><span data-stu-id="bbc87-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="bbc87-112">Δημιουργήθηκε μια **σχέση *CustomerToContact*** μεταξύ της οντότητας Πελάτης και της οντότητας Επαφή.</span><span class="sxs-lookup"><span data-stu-id="bbc87-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="bbc87-113">Η οντότητα πελάτη λαμβάνει το πεδίο κλειδιού **Contact_contactId** που σχετίζεται με το πεδίο κλειδιού οντότητας Επαφής **contactId**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="bbc87-114">Δημιουργήθηκε μια **σχέση *CustomerToAccount*** μεταξύ της οντότητας Πελάτης και της οντότητας Λογαριασμός.</span><span class="sxs-lookup"><span data-stu-id="bbc87-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="bbc87-115">Η οντότητα πελάτη λαμβάνει το πεδίο κλειδιού **Account_accountId** που σχετίζεται με το πεδίο κλειδιού οντότητας Λογαριασμού **accountId**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="bbc87-116">Δημιουργήθηκε μια **σχέση *CustomerToWebAccount*** μεταξύ της οντότητας Πελάτης και της οντότητας WebAccount.</span><span class="sxs-lookup"><span data-stu-id="bbc87-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="bbc87-117">Η οντότητα πελάτη λαμβάνει το πεδίο κλειδιού **WebAccount_webaccountId** που σχετίζεται με το πεδίο κλειδιού οντότητας WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="bbc87-118">Δημιουργία σχέσης</span><span class="sxs-lookup"><span data-stu-id="bbc87-118">Create a relationship</span></span>

<span data-ttu-id="bbc87-119">Καθορίστε τις προσαρμοσμένες σχέσεις στη σελίδα **Σχέσεις**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="bbc87-120">Κάθε σχέση αποτελείται από μια οντότητα Προέλευσης (την οντότητα που έχει το εξωτερικό κλειδί) και μια οντότητα Στόχο (την οντότητα στην οποία παραπέμπει το εξωτερικό κλειδί της οντότητας προέλευσης).</span><span class="sxs-lookup"><span data-stu-id="bbc87-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="bbc87-121">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Σχέσεις**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="bbc87-122">Επιλέξτε **Νέα σχέση**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="bbc87-123">Στο παράθυρο **Προσθήκη σχέσης**, δώστε τις εξής πληροφορίες:</span><span class="sxs-lookup"><span data-stu-id="bbc87-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbc87-124">![Εισαγάγετε λεπτομέρειες σχέσης](media/relationships-add.png "Εισαγάγετε λεπτομέρειες σχέσης")</span><span class="sxs-lookup"><span data-stu-id="bbc87-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="bbc87-125">**Όνομα σχέσης**: Όνομα που αντικατοπτρίζει το σκοπό της σχέσης (για παράδειγμα, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="bbc87-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="bbc87-126">**Περιγραφή**: Περιγραφή της σχέσης.</span><span class="sxs-lookup"><span data-stu-id="bbc87-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="bbc87-127">**Οντότητα προέλευσης**: Επιλέξτε την οντότητα που χρησιμοποιείται ως προέλευση στη σχέση (για παράδειγμα, WebLog).</span><span class="sxs-lookup"><span data-stu-id="bbc87-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="bbc87-128">**Προτεραιότητα**: Επιλέξτε την προτεραιότητα των καρτελών της οντότητας προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="bbc87-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="bbc87-129">Για παράδειγμα, "πολλοί" σημαίνει ότι πολλές καρτέλες Weblog σχετίζονται με ένα WebAccount.</span><span class="sxs-lookup"><span data-stu-id="bbc87-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="bbc87-130">**Πεδίο κλειδιού προέλευσης**: Αυτό αντιπροσωπεύει το πεδίο εξωτερικού ξένου κλειδιού στην οντότητα προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="bbc87-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="bbc87-131">Για παράδειγμα, το WebLog έχει το πεδίο εξωτερικού κλειδιού **accountId**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="bbc87-132">**Οντότητα στόχου**: Επιλέξτε την οντότητα που χρησιμοποιείται ως στόχος στη σχέση (για παράδειγμα, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="bbc87-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="bbc87-133">**Προτεραιότητα στόχου**: Επιλέξτε την προτεραιότητα των καρτελών της οντότητας στόχου.</span><span class="sxs-lookup"><span data-stu-id="bbc87-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="bbc87-134">Για παράδειγμα, "ένα" σημαίνει ότι πολλές καρτέλες Weblog σχετίζονται με ένα WebAccount.</span><span class="sxs-lookup"><span data-stu-id="bbc87-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="bbc87-135">**Πεδίο κλειδιού προορισμού**: Αυτό το πεδίο αντιπροσωπεύει το πεδίο κλειδιού της οντότητας στόχου.</span><span class="sxs-lookup"><span data-stu-id="bbc87-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="bbc87-136">Για παράδειγμα, το WebAccount έχει το πεδίο κλειδιού **accountId**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc87-137">Υποστηρίζονται μόνο σχέσεις πολλά προς ένα και ένα προς ένα.</span><span class="sxs-lookup"><span data-stu-id="bbc87-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="bbc87-138">Είναι δυνατή η δημιουργία σχέσεων πολλά προς πολλά με χρήση δύο σχέσεις πολλά προς ένα και μια οντότητα σύνδεσης (μια οντότητα που χρησιμοποιείται για τη σύνδεση της οντότητας προέλευσης και της οντότητας στόχου).</span><span class="sxs-lookup"><span data-stu-id="bbc87-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="bbc87-139">Διαγραφή μιας σχέσης</span><span class="sxs-lookup"><span data-stu-id="bbc87-139">Delete a relationship</span></span>

1. <span data-ttu-id="bbc87-140">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Σχέσεις**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="bbc87-141">Επιλέξτε τα πλαίσια ελέγχου για τις σχέσεις που θέλετε να διαγράψετε.</span><span class="sxs-lookup"><span data-stu-id="bbc87-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="bbc87-142">Επιλέξτε **Διαγραφή** στο επάνω μέρος του πίνακα **Σχέσεις**.</span><span class="sxs-lookup"><span data-stu-id="bbc87-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="bbc87-143">Επιβεβαιώστε τη διαγραφή.</span><span class="sxs-lookup"><span data-stu-id="bbc87-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="bbc87-144">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="bbc87-144">Next step</span></span>

<span data-ttu-id="bbc87-145">Οι σχέσεις συστήματος και οι προσαρμοσμένες χρησιμοποιούνται για τη δημιουργία τμημάτων αγοράς που βασίζονται σε πολλαπλές προελεύσεις δεδομένων, οι οποίες δεν είναι πλέον διαθέσιμες σε σιλό.</span><span class="sxs-lookup"><span data-stu-id="bbc87-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="bbc87-146">Για περισσότερες πληροφορίες, δείτε [Τμήματα αγοράς](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bbc87-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]