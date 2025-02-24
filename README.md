# Boxing Punch Detection and Analysis

![Jab](https://github.com/user-attachments/assets/4ce956c8-0d7f-4c49-b52c-303b6cceb1f7)

## Introduction
This project implements deep learning techniques to detect and classify boxing punches using YOLOv8, while integrating 2D pose estimation via MediaPipe to determine punch landing.

## Dataset Creation
- Videos were sourced from YouTube and converted into individual frames.
- Frames were manually selected and annotated using LabelImg.
- Defined four classes: "Jab", "Hook", "Uppercut", "Punching bag".
- Applied data augmentation techniques (rotations, flips, color adjustments).
- Training Set: 198 images (after augmentation), Test Set: 72 images.

## Model Implementation
### YOLOv8 Training
- Trained on Google Colab.
- Epochs: 100, Best Model Size: 6.2MB.
- Validation Metrics:
  - Precision: 0.986
  - Recall: 1.0
  - mAP50: 0.995
  - mAP50-95: 0.984

### Punch Detection & Pose Estimation
- YOLOv8 was used for punch and punching bag detection.
- MediaPipe was used for 2D pose estimation to track key joints.

## Punch Landing Detection
- Extracted wrist key points from MediaPipe.
- Defined bounding box regions around wrists.
- Classified punch as landed if wrist bounding box overlapped with the punching bag's bounding box.

## Evaluation Metrics
- Model Performance: Evaluated using precision, recall, and F1-score.
- Pose Estimation Accuracy: Verified correct keypoint tracking using MediaPipe.
- Punch Landing Accuracy: Estimated accuracy of punch landing detection.

## Results
- ![Hook](https://github.com/user-attachments/assets/6a3367f6-5268-4e7f-ae68-b457d06ab50a)
- ![Jab](https://github.com/user-attachments/assets/d517bad9-962a-4646-a969-072338a9ce03)
- ![Uppercut](https://github.com/user-attachments/assets/b0eab1f6-03c7-4cbf-94b0-ff072eb8aab6)

## Conclusion
This project successfully implemented YOLOv8 for punch classification and MediaPipe for 2D pose estimation, achieving high detection accuracy.

