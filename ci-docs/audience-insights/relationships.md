---
title: Σχέσεις μεταξύ οντοτήτων και διαδρομές οντοτήτων
description: Δημιουργήστε και διαχειριστείτε σχέσεις μεταξύ οντοτήτων από πολλαπλές προελεύσεις δεδομένων.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171164"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="559b3-103">Σχέσεις μεταξύ οντοτήτων</span><span class="sxs-lookup"><span data-stu-id="559b3-103">Relationships between entities</span></span>

<span data-ttu-id="559b3-104">Οι σχέσεις συνδέουν οντότητες και ορίζουν ένα γράφημα των δεδομένων σας όταν οι οντότητες έχουν ένα κοινό αναγνωριστικό, ένα ξένο κλειδί.</span><span class="sxs-lookup"><span data-stu-id="559b3-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="559b3-105">Αυτό το ξένο κλειδί μπορεί να παραπέμπεται από τη μία οντότητα σε μια άλλη.</span><span class="sxs-lookup"><span data-stu-id="559b3-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="559b3-106">Οι συνδεδεμένες οντότητες επιτρέπουν τον καθορισμό τμημάτων και μετρήσεων με βάση πολλαπλές προελεύσεις δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="559b3-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="559b3-107">Υπάρχουν τρεις τύποι σχέσεων:</span><span class="sxs-lookup"><span data-stu-id="559b3-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="559b3-108">Μη επεξεργάσιμες σχέσεις συστήματος, που δημιουργήθηκαν από το σύστημα ως μέρος της διεργασίας ενοποίησης δεδομένων</span><span class="sxs-lookup"><span data-stu-id="559b3-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="559b3-109">Μη επεξεργάσιμες μεταβιβαζόμενες σχέσεις, οι οποίες δημιουργούνται αυτόματα από τη συγχώνευση προελεύσεων δεδομένων</span><span class="sxs-lookup"><span data-stu-id="559b3-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="559b3-110">Επεξεργάσιμες προσαρμοσμένες σχέσεις, που δημιουργούνται και ρυθμίζονται από τους χρήστες</span><span class="sxs-lookup"><span data-stu-id="559b3-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="559b3-111">Μη επεξεργάσιμες σχέσεις συστήματος</span><span class="sxs-lookup"><span data-stu-id="559b3-111">Non-editable system relationships</span></span>

<span data-ttu-id="559b3-112">Κατά τη διάρκεια της ενοποίησης δεδομένων, δημιουργούνται σχέσεις συστήματος αυτόματα με βάση την έξυπνη αντιστοίχιση.</span><span class="sxs-lookup"><span data-stu-id="559b3-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="559b3-113">Αυτές οι σχέσεις συμβάλουν στη συσχέτιση των καρτελών προφίλ πελατών με αντίστοιχες καρτέλες.</span><span class="sxs-lookup"><span data-stu-id="559b3-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="559b3-114">Το παρακάτω διάγραμμα παρουσιάζει τη δημιουργία τριών σχέσεων βάσει συστήματος.</span><span class="sxs-lookup"><span data-stu-id="559b3-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="559b3-115">Η οντότητα πελάτη αντιστοιχίζεται με άλλες οντότητες για την παραγωγή της ενοποιημένης οντότητας *Πελάτη*.</span><span class="sxs-lookup"><span data-stu-id="559b3-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Διάγραμμα με διαδρομές σχέσεων για την οντότητα του πελάτη με τρεις σχέσεις 1-n.":::

- <span data-ttu-id="559b3-117">Η **σχέση *CustomerToContact*** δημιουργήθηκε μεταξύ της οντότητας *Πελάτη* και της οντότητας *Επαφή*.</span><span class="sxs-lookup"><span data-stu-id="559b3-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="559b3-118">Η οντότητα *Πελάτης* λαμβάνει το πεδίο κλειδιού **Contact_contactID** για τη συσχέτιση με την οντότητα *Επαφή* στο πεδίο κλειδιού **contactID**.</span><span class="sxs-lookup"><span data-stu-id="559b3-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="559b3-119">Η **σχέση *CustomerToAccount*** δημιουργήθηκε μεταξύ της οντότητας *Πελάτης* και της οντότητας *Λογαριασμός*.</span><span class="sxs-lookup"><span data-stu-id="559b3-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="559b3-120">Η οντότητα *Πελάτης* λαμβάνει το πεδίο κλειδιού **Account_accountID** που σχετίζεται με την οντότητα *Account* στο πεδίο κλειδιού **accountID**.</span><span class="sxs-lookup"><span data-stu-id="559b3-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="559b3-121">Η **σχέση *CustomerToWebAccount*** δημιουργήθηκε μεταξύ της οντότητας *Πελάτη* και της οντότητας *Λογαριασμός Web*.</span><span class="sxs-lookup"><span data-stu-id="559b3-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="559b3-122">Η οντότητα *Πελάτη* λαμβάνει το πεδίο κλειδιού **WebAccount_webaccountID** για τη συσχέτιση με την οντότητα *Λογαριασμός Web* στο πεδίο κλειδιού **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="559b3-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="559b3-123">Μη επεξεργάσιμες μεταβιβαζόμενες σχέσεις</span><span class="sxs-lookup"><span data-stu-id="559b3-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="559b3-124">Κατά τη διεργασία ενσωμάτωσης δεδομένων, το σύστημα ελέγχει τις προελεύσεις δεδομένων για υπάρχουσες σχέσεις.</span><span class="sxs-lookup"><span data-stu-id="559b3-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="559b3-125">Εάν δεν υπάρχει σχέση, το σύστημα τις δημιουργεί αυτόματα.</span><span class="sxs-lookup"><span data-stu-id="559b3-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="559b3-126">Αυτές οι σχέσεις χρησιμοποιούνται επίσης στις κατάντη διεργασίες.</span><span class="sxs-lookup"><span data-stu-id="559b3-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="559b3-127">Δημιουργία προσαρμοσμένης σχέσης</span><span class="sxs-lookup"><span data-stu-id="559b3-127">Create a custom relationship</span></span>

<span data-ttu-id="559b3-128">Η σχέση αποτελείται από μια *οντότητα προέλευσης* που περιέχει το ξένο κλειδί και μια *οντότητα προορισμού* στην οποία παραπέμπει το ξένο κλειδί της οντότητας προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="559b3-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="559b3-129">Στις πληροφορίες κοινού, μεταβείτε στην επιλογή **Δεδομένα** > **Σχέσεις**.</span><span class="sxs-lookup"><span data-stu-id="559b3-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="559b3-130">Επιλέξτε **Νέα σχέση**.</span><span class="sxs-lookup"><span data-stu-id="559b3-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="559b3-131">Στο τμήμα παραθύρου **Νέα σχέση**, δώστε τις εξής πληροφορίες:</span><span class="sxs-lookup"><span data-stu-id="559b3-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Πλαϊνό παράθυρο νέας σχέσης με κενά πεδία εισαγωγής.":::

   - <span data-ttu-id="559b3-133">**Όνομα σχέσης**: Όνομα που απεικονίζει το σκοπό της σχέσης.</span><span class="sxs-lookup"><span data-stu-id="559b3-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="559b3-134">Παράδειγμα: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="559b3-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="559b3-135">**Περιγραφή**: Περιγραφή της σχέσης.</span><span class="sxs-lookup"><span data-stu-id="559b3-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="559b3-136">**Οντότητα προέλευσης**: Οντότητα που χρησιμοποιείται ως προέλευση στη σχέση.</span><span class="sxs-lookup"><span data-stu-id="559b3-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="559b3-137">Παράδειγμα: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="559b3-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="559b3-138">**Οντότητα προορισμού**: Οντότητα που χρησιμοποιείται ως προορισμός στη σχέση.</span><span class="sxs-lookup"><span data-stu-id="559b3-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="559b3-139">Παράδειγμα: Πελάτης.</span><span class="sxs-lookup"><span data-stu-id="559b3-139">Example: Customer.</span></span>
   - <span data-ttu-id="559b3-140">**Πληθάριθμος προέλευσης**: Καθορίστε τον πληθάριθμο της οντότητας προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="559b3-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="559b3-141">Ο πληθάριθμος περιγράφει τον αριθμό των πιθανών στοιχείων σε ένα σύνολο.</span><span class="sxs-lookup"><span data-stu-id="559b3-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="559b3-142">Σχετίζεται πάντα με τον πληθάριθμο προορισμού.</span><span class="sxs-lookup"><span data-stu-id="559b3-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="559b3-143">Μπορείτε να επιλέξετε μεταξύ **Ένα** και **Πολλά**.</span><span class="sxs-lookup"><span data-stu-id="559b3-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="559b3-144">Υποστηρίζονται μόνο σχέσεις πολλά προς ένα και ένα προς ένα.</span><span class="sxs-lookup"><span data-stu-id="559b3-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="559b3-145">Πολλά προς ένα: Πολλές καρτέλες προέλευσης μπορούν να συσχετιστούν με μία καρτέλα προορισμού.</span><span class="sxs-lookup"><span data-stu-id="559b3-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="559b3-146">Παράδειγμα: Πολλαπλές υποθέσεις υποστήριξης από έναν μεμονωμένο πελάτη.</span><span class="sxs-lookup"><span data-stu-id="559b3-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="559b3-147">Ένα προς ένα: Μια μεμονωμένη καρτέλα προέλευσης σχετίζεται με μια καρτέλα προορισμού.</span><span class="sxs-lookup"><span data-stu-id="559b3-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="559b3-148">Παράδειγμα: Ένα αναγνωριστικό αφοσίωσης για έναν μεμονωμένο πελάτη.</span><span class="sxs-lookup"><span data-stu-id="559b3-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="559b3-149">Οι σχέσεις πολλά προς πολλά μπορούν να δημιουργηθούν με τη χρήση δύο σχέσεων πολλά προς ένα και μιας οντότητας σύνδεσης, η οποία συνδέει την οντότητα προέλευσης και την οντότητα προορισμού.</span><span class="sxs-lookup"><span data-stu-id="559b3-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="559b3-150">**Προτεραιότητα στόχου**: Επιλέξτε την προτεραιότητα των καρτελών της οντότητας στόχου.</span><span class="sxs-lookup"><span data-stu-id="559b3-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="559b3-151">**Πεδίο κλειδιού προέλευσης**: Το πεδίο εξωτερικού κλειδιού στην οντότητα προέλευσης.</span><span class="sxs-lookup"><span data-stu-id="559b3-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="559b3-152">Παράδειγμα: Το SupportCase θα μπορούσε να χρησιμοποιήσει το CaseID ως πεδίο εξωτερικού κλειδιού.</span><span class="sxs-lookup"><span data-stu-id="559b3-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="559b3-153">**Πεδίο κλειδιού προορισμού**: Το πεδίο κλειδιού της οντότητας προορισμού.</span><span class="sxs-lookup"><span data-stu-id="559b3-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="559b3-154">Παράδειγμα ο Πελάτης θα μπορούσε να χρησιμοποιήσει το πεδίο κλειδιού **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="559b3-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="559b3-155">Επιλέξτε **Αποθήκευση** για να αποθηκεύσετε την προσαρμοσμένη σχέση.</span><span class="sxs-lookup"><span data-stu-id="559b3-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="559b3-156">Προβολή σχέσεων</span><span class="sxs-lookup"><span data-stu-id="559b3-156">View relationships</span></span>

<span data-ttu-id="559b3-157">Η σελίδα Σχέσεις παραθέτει όλες τις σχέσεις που έχουν δημιουργηθεί.</span><span class="sxs-lookup"><span data-stu-id="559b3-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="559b3-158">Κάθε γραμμή αντιπροσωπεύει μια σχέση, η οποία περιλαμβάνει επίσης λεπτομέρειες σχετικά με την οντότητα προέλευσης, την οντότητα προορισμού και τον πληθάριθμο.</span><span class="sxs-lookup"><span data-stu-id="559b3-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Λίστα των σχέσεων και των επιλογών στη γραμμή ενεργειών της σελίδας Σχέσεις.":::

<span data-ttu-id="559b3-160">Αυτή η σελίδα προσφέρει ένα σύνολο επιλογών για υπάρχουσες και νέες σχέσεις:</span><span class="sxs-lookup"><span data-stu-id="559b3-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="559b3-161">**Νέα σχέση**: [Δημιουργία μιας προσαρμοσμένης σχέσης](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="559b3-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="559b3-162">**Οπτικοποίηση**: [Εξερευνήστε τη σχέση οπτικοποίησης](#explore-the-relationship-visualizer) για να δείτε ένα διάγραμμα δικτύου των υπαρχόντων σχέσεων και του πληθάριθμού τους.</span><span class="sxs-lookup"><span data-stu-id="559b3-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="559b3-163">**Φιλτράρισμα κατά**: Επιλέξτε τον τύπο των σχέσεων που θα εμφανίζονται στη λίστα.</span><span class="sxs-lookup"><span data-stu-id="559b3-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="559b3-164">**Αναζήτηση σχέσεων**: Χρησιμοποιήστε μια αναζήτηση που βασίζεται σε κείμενο στις ιδιότητες των σχέσεων.</span><span class="sxs-lookup"><span data-stu-id="559b3-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="559b3-165">Εξερεύνηση της οπτικοποίησης σχέσεων</span><span class="sxs-lookup"><span data-stu-id="559b3-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="559b3-166">Η οπτικοποίηση σχέσεων εμφανίζει ένα διάγραμμα δικτύου των υπαρχόντων σχέσεων μεταξύ συνδεδεμένων οντοτήτων και του πληθάριθμού τους.</span><span class="sxs-lookup"><span data-stu-id="559b3-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="559b3-167">Για να προσαρμόσετε την προβολή, μπορείτε να αλλάξετε τη θέση των πλαισίων σύροντάς τα στον καμβά.</span><span class="sxs-lookup"><span data-stu-id="559b3-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Στιγμιότυπο οθόνης του διαγράμματος δικτύου οπτικοποίησης σχέσεων με τις συνδέσεις μεταξύ σχετικών οντοτήτων.":::

<span data-ttu-id="559b3-169">Διαθέσιμες επιλογές:</span><span class="sxs-lookup"><span data-stu-id="559b3-169">Available options:</span></span> 
- <span data-ttu-id="559b3-170">**Εξαγωγή ως εικόνα**: Αποθηκεύστε την τρέχουσα προβολή ως αρχείο εικόνας.</span><span class="sxs-lookup"><span data-stu-id="559b3-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="559b3-171">**Αλλαγή σε οριζόντια/κατακόρυφη διάταξη**: Αλλάξτε τη στοίχιση των οντοτήτων και των σχέσεων.</span><span class="sxs-lookup"><span data-stu-id="559b3-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="559b3-172">**Επεξεργασία**: Ενημερώστε τις ιδιότητες των προσαρμοσμένων σχέσεων στο παράθυρο επεξεργασίας και αποθηκεύστε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="559b3-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="559b3-173">Διαχείριση υπαρχουσών σχέσεων</span><span class="sxs-lookup"><span data-stu-id="559b3-173">Manage existing relationships</span></span> 

<span data-ttu-id="559b3-174">Στη σελίδα Σχέσεις, κάθε σχέση αντιπροσωπεύεται από μια γραμμή.</span><span class="sxs-lookup"><span data-stu-id="559b3-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="559b3-175">Επιλέξτε μια σχέση και επιλέξτε μία από τις ακόλουθες επιλογές:</span><span class="sxs-lookup"><span data-stu-id="559b3-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="559b3-176">**Επεξεργασία**: Ενημερώστε τις ιδιότητες των προσαρμοσμένων σχέσεων στο παράθυρο επεξεργασίας και αποθηκεύστε τις αλλαγές.</span><span class="sxs-lookup"><span data-stu-id="559b3-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="559b3-177">**Διαγραφή**: Διαγραφή προσαρμοσμένων σχέσεων.</span><span class="sxs-lookup"><span data-stu-id="559b3-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="559b3-178">**Προβολή**: Προβάλετε τις σχέσεις που έχουν δημιουργηθεί από το σύστημα και τις μεταβιβαζόμενες σχέσεις.</span><span class="sxs-lookup"><span data-stu-id="559b3-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="559b3-179">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="559b3-179">Next step</span></span>

<span data-ttu-id="559b3-180">Οι σχέσεις συστήματος και οι προσαρμοσμένες χρησιμοποιούνται για τη [δημιουργία τμημάτων](segments.md) που βασίζονται σε πολλαπλές προελεύσεις δεδομένων, οι οποίες δεν είναι πλέον διαθέσιμες σε σιλό.</span><span class="sxs-lookup"><span data-stu-id="559b3-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
