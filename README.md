# Where's Wally Deep Learning Detector

This Depp Learning project used PyTorch's pre-trained model Coco(ResNet-50) with a Fast R-CNN algorithm.


## [Video of Where's Waldo Application with Streamlit](https://youtu.be/Kit9FLJ7C08)

## Training

During training, the Pareto algorithm was implemented to select and save the weights from the best epochs. This algorithm identifies epochs that perform well in both Accuracy and IOU (Intersection over Union). This was done By to optimize storage space by not needing to save all the weights from every epoch.

<img width="1033" alt="Screenshot 2023-07-23 at 15 26 05" src="https://github.com/AnabeatrizMacedo241/WheresWally_Detector/assets/84348494/da686767-4bb4-4a2f-9b89-f052b110cf63">

Model Classes: `Wally` and `Background`

## Metrics used to evaluate the problem:
- `Accuracy`: In this code, accuracy refers to the proportion of correctly predicted images out of the total number of images. It is calculated by dividing the number of correctly predicted images by the total number of images.

- `IOU` (Intersection over Union): IOU is a metric used to measure the overlap between predicted bounding boxes and ground truth bounding boxes. It quantifies how well the predicted bounding box aligns with the ground truth. In the given code, IOU is calculated for each predicted bounding box and the corresponding ground truth bounding boxes. The maximum IOU among the ground truth boxes for each predicted box is considered, and if it is above a specified threshold, it is considered a correct prediction.

So, accuracy measures the overall correctness of the predictions at the image level, while IOU assesses the alignment of predicted bounding boxes with the ground truth at the object level. Accuracy provides an overall view of the model's performance on the entire dataset, while IOU focuses specifically on the localization accuracy of the predicted bounding boxes.

It's important to note that accuracy and IOU are complementary metrics, and both are used to evaluate the effectiveness of object detection models, providing different perspectives on the model's performance.

## Results

From it, we identified that the best epoch for IOU was epoch 57 in the training with 4 batches. As for Accuracy, it was epoch 11 in the training with 7 batches. However, our choice was based on not significantly impairing either of the two metrics but giving higher weight to accuracy. Thus, the chosen epoch was 30 in the training with 4 batches.

Despite achieving good performance, there is still room for improvement, especially considering the evidence of overfitting. Some possible improvements could be:

- Testing another pre-trained model.
- Testing even more hyperparameters and optimizers.
- Acquiring more computational capacity to train even more batches.
- Expanding the dataset with data augmentation techniques or even new data.

<img width="900" alt="Screenshot 2023-07-23 at 15 22 13" src="https://github.com/AnabeatrizMacedo241/WheresWally_Detector/assets/84348494/d66bd486-fcb9-4bcd-be72-fb1cd6d08056">
