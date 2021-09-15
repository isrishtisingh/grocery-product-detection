Grocery-Product-Detection:
This repository builds a product detection model to recognize products from grocery shelf images. Everything from data preparation to model training is done using Google Colab Notebooks so that no setup is required locally. All the relevant commentaries have been included inside the Colab Notebooks.


Repository organization:
|── Notebooks
   ├── grocery-dataset-preparation.ipynb: EDA and data preparation notebook. 
   ├── grocery-dataset-evaluation.ipynb: Runs evaluation on the test images with the trained model.
   ├── grocery-dataset-inference.ipynb: Performs inference with the trained model.
   └── grocery-dataset-model-training.ipynb: Trains an SSD MobileDet model using TFOD API.

├── Deliverables
   ├── image2products.json: Contains test image names as keys and the number of products contained in each image as values.
   └── metrics.json: mAP, precision and recall computed on test set.

├── Requirement Files
   ├── generate_tfrecord.py: Generates TFRecords from the provided dataset. 
   └── ssdlite_mobiledet_dsp_320x320_products_sync_4x4.config: Configuration file needed by the TFOD API. 

├── Images : screenshots of the notebook
└── README


Notes:
--The provided dataset is converted to TFRecords for easy compatibility with the TFOD API.
--Augmentation used:
	-Horizontal flips
	-Random crops
--Detection network used: SSD MobileDet.
--Training hyperparameters are available inside Requirements/ssdlite_mobiledet_dsp_320x320_products_sync_4x4.config file.
--Precision and recall reported in Deliverables/metrics.json are mean values computed over the precision_@0.5IOU and recall_@0.5IOU columns of Requirements/confusion_matrix.csv.
--A threshold of 0.6 was used in order to obtain the number of products per test image.