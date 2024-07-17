# Drowsiness detection for DMS using Yolo V8

![DMS](output/val_batch2_pred)

### Training Losses:

train/box_loss: This loss measures the error in predicting the bounding boxes. The curve shows a steady decrease, indicating that the model is learning to predict bounding boxes more accurately over time.
train/cls_loss: This loss represents the classification error. The decreasing trend suggests the model is improving its ability to classify objects correctly.
train/dfl_loss: This is the distribution focal loss, used to refine the bounding box predictions. The decline in this loss indicates better refinement of bounding boxes.

### Validation Losses:

val/box_loss: Similar to the training box loss, this measures the error in bounding box predictions on the validation set. The decreasing trend shows that the model generalizes well to unseen data.
val/cls_loss: This is the classification loss on the validation set. The decrease indicates good generalization for classification.
val/dfl_loss: This loss on the validation set also shows a decline, confirming that the model refines bounding boxes well on unseen data.

### Metrics:

metrics/precision(B): Precision measures the proportion of true positive detections out of all positive detections. A high and stable precision curve indicates that the model makes fewer false positive predictions.
metrics/recall(B): Recall measures the proportion of true positive detections out of all actual positives. The high recall suggests the model successfully detects most of the drowsy states.
metrics/mAP50(B): Mean Average Precision at IoU threshold 0.5. This high value indicates good overall performance in object detection.
metrics/mAP50-95(B): Mean Average Precision across multiple IoU thresholds from 0.5 to 0.95. This metric being high indicates robustness and precision in the model's performance across various levels of overlap.

## Usage

1. **Running the Detector:**
   To run the traffic light detection on a video feed:
   ```bash
   yolo task=detect mode=predict model=models/best.pt source=drowsiness.mp4
   ```

![Loss plot1](metric/P_curve.png)

![Loss plot2](metric/confusion_matrix_normalized.png)

![Loss plot3](metric/val_batch1_labels.jpg)

![Loss plot4](metric/val_batch2_pred.jpg)

![Loss plot5](metric/val_batch2_labels.jpg)
