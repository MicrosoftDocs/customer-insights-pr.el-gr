---
title: Χρησιμοποιήστε μοντέλα που βασίζονται σε εκμάθηση μηχανών Azure
description: Χρησιμοποιήστε μοντέλα που βασίζονται σε εκμάθηση μηχανών Azure στο Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: el-GR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609825"
---
# <a name="use-azure-machine-learning-based-models"></a>Χρησιμοποιήστε μοντέλα που βασίζονται σε εκμάθηση μηχανών Azure

Τα ενοποιημένα δεδομένα στο Dynamics 365 Customer Insights είναι μια προέλευση για τη δημιουργία μοντέλων εκμάθησης μηχανής που μπορούν να δημιουργήσουν πρόσθετες επιχειρηματικές πληροφορίες. Το Customer Insights ενσωματώνεται στο Azure Machine Learning για να χρησιμοποιήσει τα δικά σας προσαρμοσμένα μοντέλα.

## <a name="prerequisites"></a>Προαπαιτούμενα στοιχεία

- Πρόσβαση στο Customer Insights
- Ενεργή συνδρομή Azure Enterprise
- [Ενοποιημένα προφίλ πελατών](data-unification.md)
- [Η εξαγωγή οντότητας στον χώρο αποθήκευσης αντικειμένων BLOB Azure](export-azure-blob-storage.md) έχει ρυθμιστεί

## <a name="set-up-azure-machine-learning-workspace"></a>Ρύθμιση χώρου εργασίας εκμάθησης μηχανής Azure

1. Ανατρέξτε στο θέμα [δημιουργία χώρου εργασίας εκμάθησης μηχανής Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) για διαφορετικές επιλογές για τη δημιουργία του χώρου εργασίας. Για βέλτιστη απόδοση, δημιουργήστε τον χώρο εργασίας σε μια περιοχή Azure που βρίσκεται πλησιέστερα γεωγραφικά στο περιβάλλον Customer Insights.

1. Αποκτήστε πρόσβαση στον χώρο εργασίας σας μέσω του [Στούντιο εκμάθησης μηχανής Azure](https://ml.azure.com/). Υπάρχουν διάφοροι [τρόποι αλληλεπίδρασης](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) με τον χώρο εργασίας σας.

## <a name="work-with-azure-machine-learning-designer"></a>Εργασία με τη σχεδίαση εκμάθησης μηχανής Azure

Η Εκμάθηση μηχανής Azure παρέχει έναν οπτικό καμβά όπου μπορείτε να μεταφέρετε και να αποθέσετε σύνολα δεδομένων και μονάδες. Μια διοχέτευση δέσμης που έχει δημιουργηθεί από τη σχεδίαση μπορεί να ενσωματωθεί στο Customer Insights, εάν έχουν ρυθμιστεί ανάλογα. 

## <a name="working-with-azure-machine-learning-sdk"></a>Εργασία με την Εκμάθηση μηχανής Azure SDK

Οι επιστήμονες δεδομένων και οι προγραμματιστές AI χρησιμοποιούν την [Εκμάθηση μηχανής Azure SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) για τη δημιουργία ροών εργασίας εκμάθησης μηχανής. Προς το παρόν, τα μοντέλα που εκπαιδεύονται με χρήση του SDK δεν είναι δυνατό να ενσωματωθούν απευθείας με στο Customer Insights. Μια διοχέτευση συμπερασματικής λογικής δέσμης που καταναλώνει αυτό το μοντέλο απαιτείται για την ενοποίηση με το Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Απαιτήσεις διοχέτευσης δέσμης για ενοποίηση με το Customer Insights

### <a name="dataset-configuration"></a>Ρύθμιση παραμέτρων συνόλου δεδομένων

Δημιουργήστε σύνολα δεδομένων για να χρησιμοποιήσετε δεδομένα οντοτήτων από το Customer Insights για τη διοχέτευση συμπερασματικής λογικής δέσμης. Καταχωρίστε αυτά τα σύνολα δεδομένων στον χώρο εργασίας. Προς το παρόν, υποστηρίζουμε μόνο [σύνολα δεδομένων πινάκων](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) σε μορφή .csv. Παραμετροποιήστε τα σύνολα δεδομένων που αντιστοιχούν στα δεδομένα οντότητας ως παράμετρο διοχέτευσης.

- Παράμετροι συνόλου δεδομένων στη σχεδίαση

  Στη σχεδίαση, ανοίξτε το **Επιλογή στηλών στο σύνολο δεδομένων** και επιλέξτε **Ορισμός ως παραμέτρου διοχέτευσης** όπου παρέχετε ένα όνομα για την παράμετρο.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Παραμετροποίηση συνόλου δεδομένων στη σχεδίαση.":::

- Παράμετρος συνόλου δεδομένων στο SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Διοχέτευση συμπερασματικής λογικής δέσμης
  
- Στη σχεδίαση, χρησιμοποιήστε μια διοχέτευση εκπαίδευσης για τη δημιουργία ή την ενημέρωση μιας διοχέτευσης συμπερασματικής λογικής. Προς το παρόν, υποστηρίζονται μόνο διοχετεύσεις συμπερασματικής λογικής δέσμης.

- Με τη χρήση του SDK, δημοσιεύστε τη διοχέτευση σε ένα τελικό σημείο. Προς το παρόν, το Customer Insights ενοποιείται με την προεπιλεγμένη διοχέτευση σε ένα τελικό σημείο διοχέτευσης δέσμης στον χώρο εργασίας Εκμάθηση μηχανής.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Εισαγωγή δεδομένων διοχέτευσης στο Customer Insights

- Η σχεδίαση παρέχει τη [λειτουργική μονάδα δεδομένων εξαγωγής](/azure/machine-learning/algorithm-module-reference/export-data) που επιτρέπει την έξοδο μιας διοχέτευσης για εξαγωγή σε χώρο αποθήκευσης Azure. Προς το παρόν, η λειτουργική μονάδα πρέπει να χρησιμοποιεί τον τύπο χώρου αποθήκευσης δεδομένων **Χώρο αποθήκευσης αντικειμένων Blob Azure** και να παραμετροποιεί τον **Χώρο αποθήκευσης** και τη σχετική **διαδρομή**. Το Customer Insights παρακάμπτει και τις δύο αυτές παραμέτρους κατά την εκτέλεση διοχέτευσης με έναν χώρο αποθήκευσης και μια διαδρομή η οποία είναι προσβάσιμη στο προϊόν.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Εξαγωγή ρύθμισης παραμέτρων μονάδας δεδομένων.":::

- Όταν συντάσσετε την έξοδο συμπερασματικής λογικής χρησιμοποιώντας κώδικα, αποστείλετε την έξοδο στη διαδρομή σε έναν *καταχωρημένο χώρο αποθήκευσης δεδομένων* στον χώρο εργασίας. Εάν η διαδρομή και ο χώρος αποθήκευσης δεδομένων έχουν παραμετροποιηθεί στη διοχέτευση, το Customer insights θα μπορεί να διαβάσει και να εισαγάγει την έξοδο συμπερασματικής λογικής. Προς το παρόν, υποστηρίζεται μία μόνο εξόδος πίνακα σε μορφή CSV. Η διαδρομή πρέπει να περιλαμβάνει τον κατάλογο και το όνομα του αρχείου.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]