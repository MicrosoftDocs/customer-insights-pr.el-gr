---
title: Επισκόπηση τμημάτων
description: Επισκόπηση των τμημάτων και τρόπος δημιουργίας και διαχείρισής τους.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304795"
---
# <a name="segments-overview"></a>Επισκόπηση τμημάτων

Τα τμήματα σάς επιτρέπουν να ομαδοποιήσετε τους πελάτες σας με βάση τα δημογραφικά, συναλλακτικά ή συμπεριφορικά χαρακτηριστικά. Μπορείτε να χρησιμοποιήσετε τμήματα αγοράς για να στοχεύσετε σε εκστρατείες προώθησης, δραστηριότητες πωλήσεων και ενέργειες υποστήριξης πελατών για να επιτύχετε τους επιχειρηματικούς σας στόχους.

Τα προφίλ πελατών ή επαφών που συμφωνούν με τα φίλτρα ενός ορισμού τμήματος αγοράς αναφέρονται ως *μέλη* ενός τμήματος. Ισχύουν ορισμένα [όρια εξυπηρέτησης](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Δημιουργία τμήματος

Επιλέξτε πώς να δημιουργήσετε ένα τμήμα με βάση το κοινό-στόχο σας.

# <a name="individual-consumers-b-to-c"></a>[Μεμονωμένοι πελάτες (B2C)](#tab/b2c)

- Σύνθετα τμήματα με εργαλείο δημιουργίας τμημάτων: [Φτιάξε το δικό σας](segment-builder.md)
- Απλά τμήματα με έναν τελεστή: [Γρήγορο τμήμα](segment-quick.md)
- Τρόπος τεχνητής νοημοσύνης για να βρείτε παρόμοιους πελάτες: [Παρόμοιοι πελάτες](find-similar-customer-segments.md)
- Προτάσεις με τεχνητή νοημοσύνη βασισμένες σε μέτρα ή χαρακτηριστικά: [Προτεινόμενα τμήματα με βάση μέτρα](suggested-segments.md)
- Προτάσεις βάσει δραστηριοτήτων: [Προτεινόμενα τμήματα αγοράς βάσει της δραστηριότητας του πελάτη](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Λογαριασμοί επιχειρήσεων (B2B)](#tab/b2b)

Τμήμα λογαριασμών ή τμήμα επαφών (έκδοση προεπισκόπησης) με το εργαλείο δόμησης τμημάτων: [Δημιουργήστε το δικό σας](segment-builder.md)

> [!NOTE]
> Οι περισσότεροι προορισμοί εξαγωγής απαιτούν πληροφορίες επικοινωνίας για λόγους μάρκετινγκ. Επομένως, δημιουργήστε τμήματα επαφών που θα χρησιμοποιήσετε για τις εν λόγω εξαγωγές.

---

## <a name="manage-existing-segments"></a>Διαχείριση υπαρχόντων τμημάτων αγοράς

Μεταβείτε στη σελίδα **Τμήματα** για να προβάλετε τα τμήματα που δημιουργήσατε και την κατάστασή τους καθώς και την τελευταία φορά που έγινε ανανέωση των δεδομένων. Μπορείτε να ταξινομήσετε τη λίστα των τμημάτων κατά οποιαδήποτε στήλη ή να χρησιμοποιήσετε το πλαίσιο αναζήτησης για να βρείτε το τμήμα που θέλετε να διαχειριστείτε.

> [!TIP]
> Στα περιβάλλοντα B2B, η στήλη **Τύπος κοινού** προσδιορίζει εάν ένα τμήμα βασίζεται σε λογαριασμούς ή επαφές.

Επιλέξτε ένα τμήμα για να δείτε τις διαθέσιμες ενέργειες.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Επιλεγμένο τμήμα με αναπτυσσόμενη λίστα επιλογών και διαθέσιμες επιλογές." lightbox="media/segments-selected-segment.png":::

- [**Προβάλετε**](#view-segment-details) τις λεπτομέρειες του τμήματος, συμπεριλαμβανομένης της τάσης του αριθμού μελών και μιας προεπισκόπησης των μελών του τμήματος.
- **Πραγματοποιήστε λήψη** της λίστας μελών ως αρχείο .CSV.
- **Επεξεργαστείτε** το τμήμα αγοράς για να αλλάξετε τις ιδιότητές του.
- **Δημιουργία διπλότυπου** του τμήματος. Μπορείτε να επιλέξετε να επεξεργαστείτε τις ιδιότητές του αμέσως ή να αποθηκεύσετε το διπλότυπο.
- [**Ανανεώστε**](#refresh-segments) το τμήμα για να περιλαμβάνει τα πιο πρόσφατα δεδομένα.
- Προβείτε σε **Ενεργοποίηση** ή **Απενεργοποίηση** του τμήματος. Τα ανενεργά τμήματα δεν θα ανανεωθούν κατά τη διάρκεια μιας [προγραμματισμένης ανανέωση](schedule-refresh.md) και να έχουν το **Κατάσταση** παρατίθεται ως **Παράλειψη**, υποδεικνύοντας ότι δεν επιχειρήθηκε καν ανανέωση. Τα ενεργά τμήματα ανανεώνονται με βάση τον τύπο τους: στατικά ή δυναμικά.
- **Κάντε στατικό** ή **Κάντε δυναμικό** τον τύπο του τμήματος. Τα στατικά τμήματα πρέπει να ανανεωθούν χειροκίνητα. Τα δυναμικά τμήματα ανανεώνονται αυτόματα κατά την ανανέωση του συστήματος.
- [**Βρείτε παρόμοιους πελάτες**](find-similar-customer-segments.md) από το τμήμα.
- Κάντε **Μετονομασία** του τμήματος.
- **Προσθέστε ετικέτες** για τη [διαχείριση ετικετών](work-with-tags-columns.md#manage-tags) για το τμήμα.
- [**Διαχειριστείτε τις εξαγωγές**](#export-segments) για να δείτε τμήματα που σχετίζονται με τις εξαγωγές και να τα διαχειριστείτε. [Μάθετε περισσότερα σχετικά με τις εξαγωγές.](export-destinations.md)
- Κάντε **Διαγραφή** του τμήματος.
- **Στήλες** για [προσαρμογή των στηλών](work-with-tags-columns.md#customize-columns) που εμφανίζονται.
- **Φιλτράρετε** για να [φιλτράρετε τις ετικέτες](work-with-tags-columns.md#filter-on-tags).
- **Αναζητήστε το όνομα** για αναζήτηση κατά όνομα τμήματος.

## <a name="view-segment-details"></a>Προβολή λεπτομερειών τμήματος

Στη σελίδα **Τμήματα**, επιλέξτε ένα τμήμα για να δείτε το ιστορικό επεξεργασίας και τα μέλη τμήματος.

Το επάνω μέρος της σελίδας περιλαμβάνει ένα γράφημα τάσεων που απεικονίζει τις αλλαγές στο πλήθος μελών. Τοποθετήστε το δείκτη του ποντικιού πάνω από τα σημεία δεδομένων για να δείτε το πλήθος μελών σε μια συγκεκριμένη ημερομηνία. Αλλάξτε το χρονικό πλαίσιο της απεικόνισης.

:::image type="content" source="media/segment-time-range.png" alt-text="Εύρος χρόνου τμήματος αγοράς.":::

Το κάτω μέρος περιέχει μια λίστα με τα μέλη του τμήματος αγοράς.

> [!NOTE]
> Τα πεδία που εμφανίζονται σε αυτήν τη λίστα βασίζονται στα χαρακτηριστικά των οντοτήτων του τμήματος αγοράς σας.
>
> Η λίστα είναι μια προεπισκόπηση των μελών του αντίστοιχου τμήματος και εμφανίζει τις πρώτες 100 καρτέλες του τμήματος αγοράς σας, ώστε να μπορείτε να τις αξιολογήσετε γρήγορα και να ελέγξετε τους ορισμούς της, εάν είναι απαραίτητο. Για να δείτε όλες τις καρτέλες που συμφωνούν, επιλέξτε **Δείτε περισσότερα** τα οποία ανοίγουν τη σελίδα [**Οντότητες**](entities.md) ή [εξαγάγετε το τμήμα](export-destinations.md).

## <a name="refresh-segments"></a>Ανανέωση τμημάτων

Τα τμήματα μπορούν να ανανεωθούν σε αυτόματο χρονοδιάγραμμα ή να ανανεωθούν χειροκίνητα κατόπιν αιτήματος. Για να ανανεώσετε μη αυτόματα ένα ή περισσότερα τμήματα, επιλέξτε τα και επιλέξτε **Ανανέωση**.

Για να [προγραμματίσετε την αυτόματη ανανέωση](schedule-refresh.md), μεταβείτε στην επιλογή **Χρονοδιάγραμμα** > **Σύστημα** > **Χρονοδιάγραμμα**. Ισχύουν οι ακόλουθοι κανόνες:

- Όλα τα τμήματα με τύπο **Δυναμικός** ή **Ανάπτυξη** θα ανανεώνονται αυτόματα στον συγκεκριμένο ρυθμό. Μόλις ολοκληρωθεί η ανανέωση, το **Κατάσταση** υποδεικνύει εάν υπήρχαν προβλήματα με την ανανέωση του τμήματος. Η **Τελευταία ανανέωση** εμφανίζει μια χρονική σήμανση της τελευταίας επιτυχημένης ανανέωσης. Εάν παρουσιαστεί σφάλμα, επιλέξτε το σφάλμα για να δείτε τις λεπτομέρειες σχετικά με το τι συνέβη.
- Τα τμήματα με τύπο **Στατικός** *δεν* θα ανανεώνονται αυτόματα. Η **Τελευταία ανανέωση** εμφανίζει μια χρονική σήμανση της τελευταίας φοράς που εκτελέστηκε ή ανανέωση ενός στατικού τμήματος μη αυτόματα.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Εξαγωγή τμημάτων

Εξαγωγή τμημάτων σε άλλες εφαρμογές για περαιτέρω χρήση των δεδομένων. Εξαγωγή τμήματος από τη σελίδα τμημάτων ή από τη [σελίδα εξαγωγών](export-destinations.md).

1. μεταβείτε στο σελίδα **Τμήματα** και επιλέξτε το τμήμα που θέλετε να εξαγάγετε.

1. Επιλέγω το **Διαχειριστείτε τις εξαγωγές**. Ανοίγει η σελίδα **Εξαγωγές (προεπισκόπηση) για τμήμα**. Δείτε όλες τις διαμορφωμένες εξαγωγές ομαδοποιημένες ανάλογα με το εάν περιέχουν το τρέχον τμήμα ή όχι.

   1. Για να προσθέσετε το επιλεγμένο τμήμα σε μια εξαγωγή, **επεξεργαστείτε** την αντίστοιχη εξαγωγή για να επιλέξετε το αντίστοιχο τμήμα και, στη συνέχεια, αποθηκεύστε το. Σε περιβάλλοντα για μεμονωμένους πελάτες, επιλέξτε την εξαγωγή στη λίστα και επιλέξτε **Προσθήκη τμήματος** για να επιτευχθεί το ίδιο αποτέλεσμα.

   1. Για να δημιουργήσετε μια νέα εξαγωγή με το επιλεγμένο τμήμα, επιλέξτε **Προσθήκη εξαγωγής**. Για περισσότερες πληροφορίες σχετικά με τη δημιουργία εξαγωγής, ανατρέξτε στο θέμα [Δημιουργία νέας εξαγωγής](export-destinations.md#set-up-a-new-export).

1. Επιλέξτε **Πίσω** για να επιστρέψετε στην κύρια σελίδα για τα τμήματα.

## <a name="track-usage-of-a-segment"></a>Παρακολούθηση της χρήσης ενός τμήματος

Εάν χρησιμοποιείτε τμήματα σε εφαρμογές που βασίζονται στον ίδιο οργανισμό Microsoft Dataverse που συνδέεται με το Customer Insights, μπορείτε να παρακολουθείτε τη χρήση ενός τμήματος. Για [τα τμήματα του Customer Insights που χρησιμοποιούνται σε διαδρομές πελατών του Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), το σύστημα σας ενημερώνει σχετικά με τη χρήση αυτού του τμήματος.

Κατά την επεξεργασία ενός τμήματος που χρησιμοποιείται στο περιβάλλον Customer Insights ή σε μια διαδρομή πελάτη στο Μάρκετινγκ, ένα διαφημιστικό πλαίσιο στο [εργαλείο δόμησης τμήματος](segment-builder.md) σας ενημερώνει σχετικά με τις εξαρτήσεις. Επιθεωρήστε τα στοιχεία εξάρτησης απευθείας από το banner ή επιλέγοντας το **Χρήση** στο εργαλείο δημιουργίας τμημάτων.

Η σελίδα **Χρήση τμήματος** εμφανίζει τις λεπτομέρειες σχετικά με τη χρήση αυτού του τμήματος σε εφαρμογές που βασίζονται σε Dataverse. Για τα τμήματα που χρησιμοποιούνται σε διαδρομές πελατών, θα βρείτε μια σύνδεση για να ελέγξετε τη διαδρομή στο Μάρκετινγκ, όπου χρησιμοποιείται αυτό το τμήμα. Εάν έχετε δικαιώματα πρόσβασης στην εφαρμογή Μάρκετινγκ, δείτε περισσότερες λεπτομέρειες εκεί.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Πλαϊνό παράθυρο με λεπτομέρειες σχετικά με τη χρήση του τμήματος στο εργαλείο δόμησης τμημάτων.":::

Το σύστημα σάς ενημερώνει σχετικά με τη χρήση ενός τμήματος που παρακολουθείται όταν προσπαθείτε να το διαγράψετε. Αν το τμήμα που πρόκειται να διαγράψετε χρησιμοποιείται σε μια διαδρομή πελάτη στο Μάρκετινγκ, αυτή η διαδρομή θα σταματήσει για όλους τους χρήστες του τμήματος. Εάν η διαδρομή αποτελεί μέρος μιας εκστρατείας μάρκετινγκ, η διαγραφή θα επηρεάσει την ίδια την εκστρατεία. Ωστόσο, μπορείτε ακόμα να διαγράψετε το τμήμα παρά τις προειδοποιήσεις.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Παράθυρο διαλόγου για επιβεβαίωση της διαγραφής τμήματος, όταν ένα τμήμα χρησιμοποιείται σε μια εφαρμογή Dataverse.":::

### <a name="supported-apps"></a>Υποστηριζόμενες εφαρμογές

Προς το παρόν, η χρήση παρακολουθείται στις ακόλουθες εφαρμογές που βασίζονται σε Dataverse:

- [Διαδρομές πελατών στο Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]