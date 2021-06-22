---
title: Επισκόπηση σχετικά με τα υποστηριζόμενα σενάρια πρόβλεψης
description: Σενάρια πρόβλεψης και επιλογές που καλύπτονται από την εφαρμογή Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095711"
---
# <a name="predictions-overview"></a><span data-ttu-id="dced3-103">Επισκόπηση προβλέψεων</span><span class="sxs-lookup"><span data-stu-id="dced3-103">Predictions overview</span></span>

<span data-ttu-id="dced3-104">Το Dynamics 365 Customer Insights συνοδεύεται από διάφορες επιλογές που αξιοποιούν το AI και την εκμάθηση μηχανής για την πρόβλεψη δεδομένων.</span><span class="sxs-lookup"><span data-stu-id="dced3-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="dced3-105">Έτοιμα προς χρήση μοντέλα</span><span class="sxs-lookup"><span data-stu-id="dced3-105">Out-of-box models</span></span>

<span data-ttu-id="dced3-106">Ο πιο εύκολος τρόπος για να ξεκινήσετε την πρόβλεψη δεδομένων είναι τα προκαθορισμένα μοντέλα, τα οποία συχνά αναφέρονται ως έτοιμα για χρήση μοντέλα.</span><span class="sxs-lookup"><span data-stu-id="dced3-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="dced3-107">Απαιτούν μόνο συγκεκριμένα δεδομένα και δομή για να δημιουργήσουν γρήγορα πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="dced3-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="dced3-108">Προς το παρόν, διατίθενται τα παρακάτω μοντέλα:</span><span class="sxs-lookup"><span data-stu-id="dced3-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="dced3-109">[Αξία διάρκειας ζωής πελάτη](predict-customer-lifetime-value.md): Μπορεί να αποτιμά τα πιθανά έσοδα ενός πελάτη σε ολόκληρη τη διάρκεια της αλληλεπίδρασης με μια επιχείρηση.</span><span class="sxs-lookup"><span data-stu-id="dced3-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="dced3-110">[Σύσταση προϊόντος](predict-product-recommendation.md): Προτείνει σύνολα συστάσεων πρόβλεψης προϊόντων με βάση τη συμπεριφορά αγοράς και πελάτες με παρόμοια μοτίβα αγοράς.</span><span class="sxs-lookup"><span data-stu-id="dced3-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="dced3-111">[Απώλεια συνδρομής](predict-subscription-churn.md): Προβλέπει εάν ένας πελάτης κινδυνεύει να μην χρησιμοποιεί πλέον τα συνδρομητικά προϊόντα ή τις υπηρεσίες της εταιρείας σας.</span><span class="sxs-lookup"><span data-stu-id="dced3-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="dced3-112">[Απώλεια συναλλαγής](predict-transactional-churn.md): Προβλέπει κατά πόσο ένας πελάτης θα σταματήσει να αγοράζει τα προϊόντα ή τις υπηρεσίες σας εντός καθορισμένου χρονικού πλαισίου.</span><span class="sxs-lookup"><span data-stu-id="dced3-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="dced3-113">Ενσωμάτωση εκμάθησης μηχανής Azure</span><span class="sxs-lookup"><span data-stu-id="dced3-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="dced3-114">Αν ένας οργανισμός χρησιμοποιεί ήδη σενάρια εκμάθησηςμηχανής βάσει πειραματισμού εκμάθησης μηχανής Azure, η δυνατότητα προσαρμοσμένων μοντέλων στο Customer Insights βοηθάει στη δημιουργία συνοχής.</span><span class="sxs-lookup"><span data-stu-id="dced3-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="dced3-115">Δημιουργήστε ροές εργασιών που σας βοηθούν να επιλέξετε τα δεδομένα από τα οποία θέλετε να δημιουργήσετε πληροφορίες και αντιστοιχίστε τα αποτελέσματα στα ενοποιημένα προφίλ πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="dced3-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="dced3-116">Για περισσότερες πληροφορίες, ανατρέξτε στην ενότητα [Προσαρμοσμένα μοντέλα εκμάθηση μηχανής](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="dced3-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="dced3-117">Πρόβλεψη AI Builder</span><span class="sxs-lookup"><span data-stu-id="dced3-117">AI Builder prediction</span></span>

<span data-ttu-id="dced3-118">Ορισμένες φορές, τα σύνολα δεδομένων είναι ατελή και ορισμένες τιμές λείπουν.</span><span class="sxs-lookup"><span data-stu-id="dced3-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="dced3-119">Το Customer Insights μπορεί να βοηθήσει στην κατανόηση των τιμών που λείπουν για την οντότητα Πελάτη και τα τμήματα.</span><span class="sxs-lookup"><span data-stu-id="dced3-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="dced3-120">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Συμπλήρωση ημιτελών δεδομένων με προβλέψεις](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="dced3-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
