---
title: Αντιστοίχιση οντοτήτων για ενοποίηση δεδομένων
description: Αντιστοίχιση δεδομένων για τη δημιουργία ενοποιημένων προφίλ πελατών.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267035"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="c9102-103">Αντιστοίχιση οντοτήτων και χαρακτηριστικών</span><span class="sxs-lookup"><span data-stu-id="c9102-103">Map entities and attributes</span></span>

<span data-ttu-id="c9102-104">**Η αντιστοίχιση** είναι το πρώτο στάδιο στη διαδικασία ενοποίησης δεδομένων πληροφοριών κοινού.</span><span class="sxs-lookup"><span data-stu-id="c9102-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="c9102-105">Η αντιστοίχιση αποτελείται από τρεις φάσεις:</span><span class="sxs-lookup"><span data-stu-id="c9102-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="c9102-106">*Επιλογή οντότητας*: Προσδιορίστε τις συνδυαζόμενες οντότητες που οδηγούν σε μια σύνολο δεδομένων με πληρέστερες πληροφορίες σχετικά με τους πελάτες σας.</span><span class="sxs-lookup"><span data-stu-id="c9102-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="c9102-107">*Επιλογή χαρακτηριστικού*: Για κάθε οντότητα, προσδιορίστε τις στήλες που θέλετε να συνδυάσετε και συμψηφίσετε στις φάσεις *αντιστοίχισης* και *συγχώνευσης*.</span><span class="sxs-lookup"><span data-stu-id="c9102-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="c9102-108">Αυτές οι στήλες ονομάζονται *Χαρακτηριστικά*.</span><span class="sxs-lookup"><span data-stu-id="c9102-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="c9102-109">*Επιλογή πρωτεύοντος κλειδιού και τύπου σημασιολογίας*: για κάθε οντότητα, προσδιορίστε ένα χαρακτηριστικό που θέλετε να ορίσετε ως πρωτεύον κλειδί για αυτήν την οντότητα και για κάθε χαρακτηριστικό, προσδιορίστε έναν τύπο σημασιολογίας που περιγράφει καλύτερα αυτό το χαρακτηριστικό.</span><span class="sxs-lookup"><span data-stu-id="c9102-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="c9102-110">Για περισσότερες πληροφορίες σχετικά με τη γενική ροή της ενοποίησης δεδομένων, ανατρέξτε στο [Ενοποίηση](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c9102-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="c9102-111">Επιλέξτε τις πρώτες οντότητες</span><span class="sxs-lookup"><span data-stu-id="c9102-111">Select the first entities</span></span>

1. <span data-ttu-id="c9102-112">Στις πληροφορίες κοινού, μεταβείτε στα **Δεδομένα** > **Ενοποίηση** > **Χάρτης**.</span><span class="sxs-lookup"><span data-stu-id="c9102-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="c9102-113">Ξεκινήστε τη φάση του χάρτη επιλέγοντας **Επιλογή οντοτήτων**.</span><span class="sxs-lookup"><span data-stu-id="c9102-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="c9102-114">Επιλέξτε τις οντότητες και τα χαρακτηριστικά που θέλετε να χρησιμοποιήσετε στις φράσεις *αντιστοίχιση* και *συγχώνευση*.</span><span class="sxs-lookup"><span data-stu-id="c9102-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="c9102-115">Μπορείτε να επιλέξετε τα απαιτούμενα χαρακτηριστικά μεμονωμένα από μια οντότητα ή να συμπεριλάβετε όλα τα χαρακτηριστικά από μια οντότητα επιλέγοντας το πλαίσιο ελέγχου **Συμπερίληψη όλων των πεδίων** στο επίπεδο οντότητας.</span><span class="sxs-lookup"><span data-stu-id="c9102-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="c9102-116">Συνιστούμε να επιλέξετε τουλάχιστον δύο οντότητες για να επωφεληθείτε από τη διεργασία ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="c9102-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9102-117">![Παράδειγμα προσθήκης οντοτήτων](media/data-manager-configure-map-add-entities-example.png "Παράδειγμα προσθήκης οντοτήτων")</span><span class="sxs-lookup"><span data-stu-id="c9102-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="c9102-118">Σε αυτό το παράδειγμα, προσθέτουμε τις οντότητες **eCommerceContacts** και **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c9102-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="c9102-119">Επιλέγοντας αυτές τις οντότητες, μπορείτε να αντλήσετε πληροφορίες σχετικά με το ποιοι από τους ηλεκτρονικούς πελάτες της επιχείρησης είναι μέλη του προγράμματος αφοσίωσης.</span><span class="sxs-lookup"><span data-stu-id="c9102-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="c9102-120">Μπορείτε να αναζητήσετε λέξεις - κλειδιά σε όλα τα χαρακτηριστικά και τις οντότητες για να επιλέξετε τα απαιτούμενα χαρακτηριστικά που θέλετε να αντιστοιχίσετε.</span><span class="sxs-lookup"><span data-stu-id="c9102-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9102-121">![Παράδειγμα πεδίων αναζήτησης](media/data-manager-configure-map-search-fields-example.png "Παράδειγμα πεδίων αναζήτησης")</span><span class="sxs-lookup"><span data-stu-id="c9102-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="c9102-122">Επιλέξτε **Εφαρμογή** για να επιβεβαιώσετε τις επιλογές σας.</span><span class="sxs-lookup"><span data-stu-id="c9102-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="c9102-123">Επιλογή πρωτεύοντος κλειδιού και τύπου σημασιολογίας για χαρακτηριστικά</span><span class="sxs-lookup"><span data-stu-id="c9102-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="c9102-124">Αφού επιλέξετε τις οντότητες σας, η σελίδα **Αντιστοίχιση** απαριθμεί τις επιλεγμένες οντότητες για την κριτική σας.</span><span class="sxs-lookup"><span data-stu-id="c9102-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="c9102-125">Καθορίστε το πρωτεύον κλειδί για μια οντότητα και προσδιορίστε τον τύπο σημασιολογίας για ένα χαρακτηριστικό στην οντότητα.</span><span class="sxs-lookup"><span data-stu-id="c9102-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="c9102-126">**Πρωτεύον κλειδί**: Επιλέξτε ένα χαρακτηριστικό ως πρωτεύον κλειδί για κάθε μία από τις οντότητες σας.</span><span class="sxs-lookup"><span data-stu-id="c9102-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="c9102-127">Για να είναι ένα χαρακτηριστικό έγκυρο πρωτεύον κλειδί, δεν πρέπει να περιλαμβάνει διπλότυπες τιμές, τιμές που λείπουν ή τιμές null.</span><span class="sxs-lookup"><span data-stu-id="c9102-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="c9102-128">Τα χαρακτηριστικά τύπου συμβολοσειράς, ακέραιου και δεδομένων GUID υποστηρίζονται ως πρωτεύοντα κλειδιά και θα εμφανίζονται σε ένα πεδίο από το οποίο θα μπορείτε να επιλέξετε.</span><span class="sxs-lookup"><span data-stu-id="c9102-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="c9102-129">**Σημασιολογικός τύπος χαρακτηριστικού**: κατηγορίες των χαρακτηριστικών σας, όπως διεύθυνση ηλεκτρονικού ταχυδρομείου ή όνομα.</span><span class="sxs-lookup"><span data-stu-id="c9102-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="c9102-130">Για να χρησιμοποιήσετε μοντέλα AI για έξυπνη πρόβλεψη σημασιολογίας, για να εξοικονομήσετε χρόνο και να βελτιώσετε την ακρίβεια, ορίστε την **Ευφυή αντιστοίχιση** σε **Ενεργό**.</span><span class="sxs-lookup"><span data-stu-id="c9102-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="c9102-131">Η ευφυής αντιστοίχιση επισημαίνει τη σημασιολογική σύσταση που βασίζεται στο AI στο πεδίο **Τύπος**.</span><span class="sxs-lookup"><span data-stu-id="c9102-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="c9102-132">Εάν την ορίσετε ως **Ανενεργή**, θα δείτε τις συνήθεις προτάσεις αντιστοίχισης.</span><span class="sxs-lookup"><span data-stu-id="c9102-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="c9102-133">Μπορείτε να επιλέξετε οποιοδήποτε τύπο σημασιολογίας από τη διαθέσιμη λίστα επιλογών και να αντικαταστήσετε την προτεινόμενη επιλογή.</span><span class="sxs-lookup"><span data-stu-id="c9102-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9102-134">![Τύπος χαρακτηριστικού και σημασιολογική πρόβλεψη](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Τύπος χαρακτηριστικού και σημασιολογική πρόβλεψη")</span><span class="sxs-lookup"><span data-stu-id="c9102-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="c9102-135">Επίσης, είναι δυνατή η προσθήκη ενός προσαρμοσμένου σημασιολογικού τύπου.</span><span class="sxs-lookup"><span data-stu-id="c9102-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="c9102-136">Επιλέξτε το πεδίο τύπου για ένα χαρακτηριστικό και πληκτρολογήστε το όνομα του σημασιολογικού τύπου χαρακτηριστικού σας.</span><span class="sxs-lookup"><span data-stu-id="c9102-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="c9102-137">Μπορείτε επίσης να αλλάξετε τους τύπους χαρακτηριστικών που αναγνωρίστηκαν από το σύστημα.</span><span class="sxs-lookup"><span data-stu-id="c9102-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="c9102-138">Όλα τα χαρακτηριστικά για τα οποία προσδιορίζεται αυτόματα ένας σημασιολογικός τύπος ομαδοποιούνται στην ενότητα **Κριτική αντιστοιχισμένων πεδίων**.</span><span class="sxs-lookup"><span data-stu-id="c9102-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="c9102-139">Εξετάστε αυτά τα χαρακτηριστικά και τους σημασιολογικούς τύπους τους, επειδή θα χρησιμοποιηθούν για το συνδυασμό των οντοτήτων σας στο βήμα συγχώνευσης της ενοποίησης δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="c9102-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="c9102-140">Τα χαρακτηριστικά που δεν αντιστοιχίζονται αυτόματα σε έναν σημασιολογικό τύπο ομαδοποιούνται στην ενότητα **Ορισμός των δεδομένων στα μη αντιστοιχισμένα πεδία**.</span><span class="sxs-lookup"><span data-stu-id="c9102-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="c9102-141">Επιλέξτε το πεδίο σημασιολογικού τύπου για τα μη αντιστοιχισμένα χαρακτηριστικά ή εισαγάγετε το προσαρμοσμένο όνομα τύπου χαρακτηριστικού.</span><span class="sxs-lookup"><span data-stu-id="c9102-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9102-142">![Πρωτεύον κλειδί και τύπος χαρακτηριστικού](media/data-manager-configure-map-add-attributes.png "Πρωτεύον κλειδί και τύπος χαρακτηριστικού")</span><span class="sxs-lookup"><span data-stu-id="c9102-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="c9102-143">Ένα πεδίο θα πρέπει να αντιστοιχεί στον σημασιολογικό τύπο Person.FullName για τη συμπλήρωση του ονόματος πελάτη στην καρτέλα πελάτη.</span><span class="sxs-lookup"><span data-stu-id="c9102-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="c9102-144">Διαφορετικά, οι καρτέλες του πελάτη θα εμφανίζονται ανώνυμες.</span><span class="sxs-lookup"><span data-stu-id="c9102-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="c9102-145">Προσθήκη και κατάργηση χαρακτηριστικών και οντοτήτων</span><span class="sxs-lookup"><span data-stu-id="c9102-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="c9102-146">Στην **Ενοποίηση** > **Αντιστοίχιση**, επιλέξτε **Επεξεργασία πεδίων**.</span><span class="sxs-lookup"><span data-stu-id="c9102-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="c9102-147">Στο τμήμα παραθύρου **Επεξεργασία πεδίων**, προσθέστε ή καταργήστε χαρακτηριστικά και οντότητες.</span><span class="sxs-lookup"><span data-stu-id="c9102-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="c9102-148">Χρησιμοποιήστε την αναζήτηση ή κάντε κύλιση για να βρείτε και να επιλέξετε τα χαρακτηριστικά και τις οντότητες που σας ενδιαφέρουν.</span><span class="sxs-lookup"><span data-stu-id="c9102-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="c9102-149">Δεν μπορείτε να καταργήσετε ένα χαρακτηριστικό ή μια οντότητα εάν έχουν ήδη αντιστοιχιστεί.</span><span class="sxs-lookup"><span data-stu-id="c9102-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9102-150">![Προσθήκη ή κατάργηση χαρακτηριστικών](media/configure-data-map-edit.png "Προσθήκη ή κατάργηση χαρακτηριστικών")</span><span class="sxs-lookup"><span data-stu-id="c9102-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="c9102-151">Επιλέξτε **Εφαρμογή**.</span><span class="sxs-lookup"><span data-stu-id="c9102-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="c9102-152">Προσθήκη εικόνων σε προφίλ</span><span class="sxs-lookup"><span data-stu-id="c9102-152">Add images to profiles</span></span>

<span data-ttu-id="c9102-153">Εάν μια οντότητα περιέχει διευθύνσεις URL για εικόνες ή λογότυπα με δημόσια διαθέσιμα προφίλ, μπορείτε να τα προσθέσετε στο Ενοποιημένο προφίλ πελάτη.</span><span class="sxs-lookup"><span data-stu-id="c9102-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="c9102-154">Επιλέξτε την οντότητα και βρείτε το πεδίο που περιέχει τη διεύθυνση URL για την εικόνα προφίλ.</span><span class="sxs-lookup"><span data-stu-id="c9102-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="c9102-155">Στο πεδίο **Τύπος**, πληκτρολογήστε μια προεπιλεγμένη τιμή για το πεδίο εισόδου:</span><span class="sxs-lookup"><span data-stu-id="c9102-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="c9102-156">Για ένα άτομο: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="c9102-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="c9102-157">Για έναν οργανισμό: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="c9102-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="c9102-158">Συνεχίστε με τα βήματα ενοποίησης και διασφαλίστε ότι το χαρακτηριστικό που περιέχει τη διεύθυνση URL εικόνας προστίθεται επίσης και στο βήμα [Συγχώνευση](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="c9102-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="c9102-159">Ορισμός χαρακτηριστικών για οργανισμούς</span><span class="sxs-lookup"><span data-stu-id="c9102-159">Set attributes for organizations</span></span>

<span data-ttu-id="c9102-160">Για οργανισμούς (προεπισκόπηση), ο τύπος χαρακτηριστικού πρέπει να αντιστοιχιστεί σε «Organization.Name»</span><span class="sxs-lookup"><span data-stu-id="c9102-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9102-161">![Πρωτεύον κλειδί και τύπος χαρακτηριστικού B2B](media/configure-data-map-edit-b2b.png "Πρωτεύον κλειδί και τύπος χαρακτηριστικού B2B")</span><span class="sxs-lookup"><span data-stu-id="c9102-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="c9102-162">Επόμενο βήμα</span><span class="sxs-lookup"><span data-stu-id="c9102-162">Next step</span></span>

<span data-ttu-id="c9102-163">Στο πλαίσιο της διαδικασίας ενοποίησης δεδομένων, μεταβείτε στη σελίδα **Αντιστοιχία**.</span><span class="sxs-lookup"><span data-stu-id="c9102-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="c9102-164">Επισκεφθείτε την [**Αντιστοιχία**](match-entities.md) για να μάθετε σχετικά με αυτήν τη φάση.</span><span class="sxs-lookup"><span data-stu-id="c9102-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="c9102-165">Δείτε το παρακάτω βίντεο: [Γρήγορα αποτελέσματα: Δημιουργία Ενοποιημένου προφίλ πελάτη](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="c9102-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]