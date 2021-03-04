---
title: Πειράματα εκμάθησης μηχανής Azure
description: Χρησιμοποιήστε μοντέλα που βασίζονται σε εκμάθηση μηχανών Azure στο Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267906"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="ed5c6-103">Χρησιμοποιήστε μοντέλα που βασίζονται σε εκμάθηση μηχανών Azure</span><span class="sxs-lookup"><span data-stu-id="ed5c6-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="ed5c6-104">Τα ενοποιημένα δεδομένα στο Dynamics 365 Customer Insights είναι μια προέλευση για τη δημιουργία μοντέλων εκμάθησης μηχανής που μπορούν να δημιουργήσουν πρόσθετες επιχειρηματικές πληροφορίες.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="ed5c6-105">Το Customer Insights ενσωματώνεται στο Στούντιο εκμάθησης μηχανής (κλασικό) και την Εκμάθηησ μηχανής Azure για να χρησιμοποιήσετε τα δικά σας προσαρμοσμένα μοντέλα.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="ed5c6-106">Ανατρέξτε στα [πειράματα Στούντιο εκμάθησης μηχανής (κλασικά)](machine-learning-studio-experiments.md) για παραδείγματα πειραμάτων που έχουν δομηθεί στο Στούντιο εκμάθησης μηχανής (κλασικό).</span><span class="sxs-lookup"><span data-stu-id="ed5c6-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ed5c6-107">Προϋποθέσεις</span><span class="sxs-lookup"><span data-stu-id="ed5c6-107">Prerequisites</span></span>

- <span data-ttu-id="ed5c6-108">Πρόσβαση στο Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ed5c6-108">Access to Customer Insights</span></span>
- <span data-ttu-id="ed5c6-109">Ενεργή συνδρομή Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="ed5c6-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="ed5c6-110">Ενοποιημένα προφίλ πελατών</span><span class="sxs-lookup"><span data-stu-id="ed5c6-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="ed5c6-111">[Η εξαγωγή οντότητας στον χώρο αποθήκευσης αντικειμένων BLOB Azure](export-azure-blob-storage.md) έχει ρυθμιστεί</span><span class="sxs-lookup"><span data-stu-id="ed5c6-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="ed5c6-112">Ρύθμιση χώρου εργασίας εκμάθησης μηχανής Azure</span><span class="sxs-lookup"><span data-stu-id="ed5c6-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="ed5c6-113">Ανατρέξτε στο θέμα [δημιουργία χώρου εργασίας εκμάθησης μηχανής Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) για διαφορετικές επιλογές για τη δημιουργία του χώρου εργασίας.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="ed5c6-114">Για βέλτιστη απόδοση, δημιουργήστε τον χώρο εργασίας σε μια περιοχή Azure που βρίσκεται πλησιέστερα γεωγραφικά στο περιβάλλον Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="ed5c6-115">Αποκτήστε πρόσβαση στον χώρο εργασίας σας μέσω του [Στούντιο εκμάθησης μηχανής Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="ed5c6-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="ed5c6-116">Υπάρχουν διάφοροι [τρόποι αλληλεπίδρασης](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) με τον χώρο εργασίας σας.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="ed5c6-117">Εργασία με τη σχεδίαση εκμάθησης μηχανής Azure</span><span class="sxs-lookup"><span data-stu-id="ed5c6-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="ed5c6-118">Η σχεδίαση Εκμάθησης μηχανής Azure παρέχει έναν οπτικό καμβά όπου μπορείτε να μεταφέρετε και να αποσύρετε σύνολα δεδομένων και λειτουργικές μονάδες, παρόμοιες με το Στούντιο εκμάθησης μηχανής (κλασικό).</span><span class="sxs-lookup"><span data-stu-id="ed5c6-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="ed5c6-119">Μια διοχέτευση δέσμης που έχει δημιουργηθεί από τη σχεδίαση μπορεί να ενσωματωθεί στο Customer Insights, εάν έχουν ρυθμιστεί ανάλογα.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="ed5c6-120">Εργασία με την Εκμάθηση μηχανής Azure SDK</span><span class="sxs-lookup"><span data-stu-id="ed5c6-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="ed5c6-121">Οι επιστήμονες δεδομένων και οι προγραμματιστές AI χρησιμοποιούν την [Εκμάθηση μηχανής Azure SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) για τη δημιουργία ροών εργασίας εκμάθησης μηχανής.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="ed5c6-122">Προς το παρόν, τα μοντέλα που εκπαιδεύονται με χρήση του SDK δεν είναι δυνατό να ενσωματωθούν απευθείας με στο Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="ed5c6-123">Μια διοχέτευση συμπερασματικής λογικής δέσμης που καταναλώνει αυτό το μοντέλο απαιτείται για την ενοποίηση με το Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="ed5c6-124">Απαιτήσεις διοχέτευσης δέσμης για ενοποίηση με το Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ed5c6-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="ed5c6-125">Ρύθμιση παραμέτρων συνόλου δεδομένων</span><span class="sxs-lookup"><span data-stu-id="ed5c6-125">Dataset Configuration</span></span>

<span data-ttu-id="ed5c6-126">Πρέπει να δημιουργήσετε σύνολα δεδομένων για να χρησιμοποιήσετε δεδομένα οντοτήτων από το Customer Insights στη διοχέτευση συμπερασματικής λογικής δέσμης.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="ed5c6-127">Αυτά τα σύνολα δεδομένων πρέπει να καταχωρηθούν στον χώρο εργασίας.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="ed5c6-128">Προς το παρόν, υποστηρίζουμε μόνο [σύνολα δεδομένων πινάκων](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) σε μορφή .csv.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="ed5c6-129">Τα σύνολα δεδομένων που αντιστοιχούν στα δεδομένα οντότητας πρέπει να παραμετροποιηθούν ως παράμετρος διοχέτευσης.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="ed5c6-130">Παράμετροι συνόλου δεδομένων στη σχεδίαση</span><span class="sxs-lookup"><span data-stu-id="ed5c6-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="ed5c6-131">Στη σχεδίαση, ανοίξτε το **Επιλογή στηλών στο σύνολο δεδομένων** και επιλέξτε **Ορισμός ως παραμέτρου διοχέτευσης** όπου παρέχετε ένα όνομα για την παράμετρο.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="ed5c6-132">![Παραμετροποίηση συνόλου δεδομένων στη σχεδίαση](media/intelligence-designer-dataset-parameters.png "Παραμετροποίηση συνόλου δεδομένων στη σχεδίαση")</span><span class="sxs-lookup"><span data-stu-id="ed5c6-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="ed5c6-133">Παράμετρος συνόλου δεδομένων στο SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="ed5c6-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="ed5c6-134">Διοχέτευση συμπερασματικής λογικής δέσμης</span><span class="sxs-lookup"><span data-stu-id="ed5c6-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="ed5c6-135">Στη σχεδίαση, μια διοχέτευση εκπαίδευσης μπορεί να χρησιμοποιηθεί για τη δημιουργία ή την ενημέρωση μιας διοχέτευσης συμπερασματικής λογικής.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="ed5c6-136">Προς το παρόν, υποστηρίζονται μόνο διοχετεύσεις συμπερασματικής λογικής δέσμης.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="ed5c6-137">Με τη χρήση του SDK, μπορείτε να δημοσιεύσετε τη διοχέτευση σε ένα τελικό σημείο.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="ed5c6-138">Προς το παρόν, το Customer Insights ενοποιείται με την προεπιλεγμένη διοχέτευση σε ένα τελικό σημείο διοχέτευσης δέσμης στον χώρο εργασίας Εκμάθηση μηχανής.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="ed5c6-139">Εισαγωγή δεδομένων διοχέτευσης στο Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ed5c6-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="ed5c6-140">Η σχεδίαση παρέχει τη [λειτουργική μονάδα δεδομένων εξαγωγής](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) που επιτρέπει την έξοδο μιας διοχέτευσης για εξαγωγή σε χώρο αποθήκευσης Azure.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="ed5c6-141">Προς το παρόν, η λειτουργική μονάδα πρέπει να χρησιμοποιεί τον τύπο χώρου αποθήκευσης δεδομένων **Χώρο αποθήκευσης αντικειμένων Blob Azure** και να παραμετροποιεί τον **Χώρο αποθήκευσης** και τη σχετική **διαδρομή**.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="ed5c6-142">Το Customer Insights παρακάμπτει και τις δύο αυτές παραμέτρους κατά την εκτέλεση διοχέτευσης με έναν χώρο αποθήκευσης και μια διαδρομή η οποία είναι προσβάσιμη στο προϊόν.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed5c6-143">![Εξαγωγή ρύθμισης παραμέτρων μονάδας δεδομένων](media/intelligence-designer-importdata.png "Εξαγωγή ρύθμισης παραμέτρων μονάδας δεδομένων")</span><span class="sxs-lookup"><span data-stu-id="ed5c6-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="ed5c6-144">Όταν συντάσσετε την έξοδο συμπερασματικής λογικής χρησιμοποιώντας κώδικα, μπορείτε να αποστείλετε την έξοδο στη διαδρομή σε έναν *καταχωρημένο χώρο αποθήκευσης δεδομένων* στον χώρο εργασίας.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="ed5c6-145">Εάν η διαδρομή και ο χώρος αποθήκευσης δεδομένων έχουν παραμετροποιηθεί στη διοχέτευση, το Customer insights θα μπορεί να διαβάσει και να εισαγάγει την έξοδο συμπερασματικής λογικής.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="ed5c6-146">Προς το παρόν, υποστηρίζεται μία μόνο εξόδος πίνακα σε μορφή CSV.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="ed5c6-147">Η διαδρομή πρέπει να περιλαμβάνει τον κατάλογο και το όνομα του αρχείου.</span><span class="sxs-lookup"><span data-stu-id="ed5c6-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]