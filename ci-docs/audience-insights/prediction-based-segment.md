---
title: Τμήματα με βάση έξοδο πρόβλεψης
description: Δημιουργήστε τμήματα με βάση την οντότητα εξόδου ενός μοντέλου πρόβλεψης.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741429"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="8f871-103">Δημιουργία τμήματος με βάση μοντέλο πρόβλεψης (έκδοση προεπισκόπησης)</span><span class="sxs-lookup"><span data-stu-id="8f871-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="8f871-104">Τα αποτελέσματα των προβλέψεις μερικές φορές ισχύουν μόνο για ένα υποσύνολο των πελατών σας.</span><span class="sxs-lookup"><span data-stu-id="8f871-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="8f871-105">Αυξήστε την εξατομίκευση των προτάσεων δημιουργώντας τμήματα από τα αποτελέσματα μοντέλων πρόβλεψης.</span><span class="sxs-lookup"><span data-stu-id="8f871-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="8f871-106">Για παράδειγμα, μπορεί να θέλετε να κάνετε συγκεκριμένες προτάσεις στους πελάτες σας που προτιμούν έναν συγκεκριμένο τύπο εξυπηρέτησης.</span><span class="sxs-lookup"><span data-stu-id="8f871-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8f871-107">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="8f871-107">Prerequisites</span></span>

- <span data-ttu-id="8f871-108">Τουλάχιστον [Δικαιώματα συμμετέχοντα](permissions.md) στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8f871-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="8f871-109">Ένα μοντέλο προτάσεων προϊόντων, απώλειας συναλλαγών, απώλειας συνδρομών ή δια βίου αξίας πελάτη που έχει ρυθμιστεί στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8f871-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="8f871-110">Εξετάστε τις απαιτήσεις για τη ρύθμιση των διαφορετικών μοντέλων:</span><span class="sxs-lookup"><span data-stu-id="8f871-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="8f871-111">Μοντέλο πρότασης προϊόντος</span><span class="sxs-lookup"><span data-stu-id="8f871-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="8f871-112">Μοντέλο απώλειας συνδρομών</span><span class="sxs-lookup"><span data-stu-id="8f871-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="8f871-113">Μοντέλο απώλειας συναλλαγών</span><span class="sxs-lookup"><span data-stu-id="8f871-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="8f871-114">Μοντέλο δια βίου αξίας πελατών</span><span class="sxs-lookup"><span data-stu-id="8f871-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="8f871-115">Δημιουργία τμήματος πελάτη με βάση προβλέψεις</span><span class="sxs-lookup"><span data-stu-id="8f871-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="8f871-116">Μεταβείτε στην **Ευφυΐα** > **Προβλέψεις** και επιλέξτε την καρτέλα **Οι προβλέψεις μου**.</span><span class="sxs-lookup"><span data-stu-id="8f871-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8f871-117">Επιλέξτε τα κατακόρυφα αποσιωπητικά δίπλα στο μοντέλο που θέλετε να αναθεωρήσετε και επιλέξτε **Προβολή**.</span><span class="sxs-lookup"><span data-stu-id="8f871-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="8f871-118">Στη σελίδα αποτελεσμάτων, επιλέξτε **Δημιουργία τμήματος**.</span><span class="sxs-lookup"><span data-stu-id="8f871-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="8f871-119">Για περισσότερες πληροφορίες σχετικά με τη σελίδα αποτελεσμάτων, διαβάστε το άρθρο σχετικά με το μοντέλο.</span><span class="sxs-lookup"><span data-stu-id="8f871-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Στιγμιότυπο οθόνης των αποτελεσμάτων πρόβλεψης με το επισήμανση στην ενέργεια &quot;Δημιουργία τμήματος&quot;.":::

1. <span data-ttu-id="8f871-121">Δημιουργήστε ένα νέο τμήμα με βάση την οντότητα εξόδου του επιλεγμένου μοντέλου.</span><span class="sxs-lookup"><span data-stu-id="8f871-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="8f871-122">Για περισσότερες πληροφορίες, ανατρέξτε στο θέμα [Δημιουργία και διαχείριση τμημάτων](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8f871-122">For more information, see [Create and manage segments](segments.md).</span></span>