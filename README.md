This adapted YOLOv11n framework performs end-to-end object detection and classification on **AgroPest-12 images**.
[Credit: Rupankar Majumdar, "AgroPest-12: A 12-Class Image Dataset of Crop Insects and Pests," Kaggle, 2025.](https://www.kaggle.com/datasets/rupankarmajumdar/crop-pests-dataset)

The provided data.yaml file defines the dataset configuration for training object detection models on the Crop Pests Dataset. It specifies the paths to the train, validation, and test images, sets the number of classes (nc=12), and lists the pest categories: Ants, Bees, Beetles, Caterpillars, Earthworms, Earwigs, Grasshoppers, Moths, Slugs, Snails, Wasps, and Weevils.

train: ../train/images
val: ../valid/images
test: ../test/images

nc: 12
names:
  [
    "Ants",
    "Bees",
    "Beetles",
    "Caterpillars",
    "Earthworms",
    "Earwigs",
    "Grasshoppers",
    "Moths",
    "Slugs",
    "Snails",
    "Wasps",
    "Weevils",
  ]
  

Evaluation metrics include mAP@0.5, mAP@0.5:0.95, precision, recall, and F1 score.
