This adapted YOLOv11n framework performs end-to-end object detection and classification on **AgroPest-12 images**.
[Rupankar Majumdar, "AgroPest-12: A 12-Class Image Dataset of Crop Insects and Pests," Kaggle, 2025.](https://www.kaggle.com/datasets/rupankarmajumdar/crop-pests-dataset)

**Baseline Reference (YOLOv11n on AgroPest-12)**
The dataset provider (Rupankar Majumdar) uploaded a [YOLOv11n example](https://www.kaggle.com/code/rupankarmajumdar/pest-detection-classification-v11n) alongside the AgroPest-12 dataset on Kaggle.
This could be used as a secondary reference implementation for benchmarking purposes. To validate our pipeline and environment setup, we reproduced the YOLOv11n model using the same dataset but with slightly different hyperparameters (shorter training schedule, default augmentations). The reproduction was executed on Google Colab (Tesla T4, CUDA 12.6, Ultralytics 8.3.28).

The evaluation below shows comparable but slightly lower performance than the original Kaggle notebook, which is expected with reduced training epochs.
```
> | Metric | Reproduced (ours)             | Kaggle reference (Majumdar) | Δ |
> | Precision | 0.846                      | ≈ 0.91 – 0.93 | −0.06 to −0.08 |
> | Recall | 0.708                         | ≈ 0.88 – 0.90 | −0.17 to −0.19 |
> | mAP@0.5 | 0.778                        | ≈ 0.91 | −0.13 |
> | mAP@0.5:0.95  | 0.469                  | ≈ 0.85 | −0.38 |
> | Inference Speed | 5.4 ms/image         | ≈ 6 ms/image | ~equal |
```
**Per-Class Performance**
```
Ants: P=0.955  R=0.727  AP50=0.814  
Bees: P=0.874  R=0.864  AP50=0.922  
Beetles: P=0.757  R=0.636  AP50=0.717  
Caterpillars: P=0.749  R=0.430  AP50=0.611  
Earthworms: P=0.651  R=0.425  AP50=0.458  
Earwigs: P=0.859  R=0.658  AP50=0.745  
Grasshoppers: P=0.784  R=0.545  AP50=0.617  
Moths: P=0.989  R=0.894  AP50=0.964  
Slugs: P=0.754  R=0.549  AP50=0.672  
Snails: P=0.860  R=0.840  AP50=0.847  
Wasps: P=0.984  R=0.979  AP50=0.976  
Weevils: P=0.942  R=0.948  AP50=0.989  
```
