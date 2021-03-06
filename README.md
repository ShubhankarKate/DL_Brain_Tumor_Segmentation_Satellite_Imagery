# DL_Brain_Tumor_Segmentation_Satellite_Imagery
Final Project Submission : CS F425 (Deep Learning)

**Group 16: Brain Tumor Segmentation and Satellite Imagery Segmentation using UNet Architecture**
| Name | ID |
|---|---|
| Aman Jain | 2018B5A70868G | 
| Atishay Jain | 2018B5A70908G | 
| Shubhankar Kate | 2018B4A70786G | 

## Project Description
Our project focuses on studying and implementing the U-Net Architecture famously used for Image Segmentation task. In the paper "[Optimized U-Net for Brain Tumor Segmentation](https://arxiv.org/pdf/2110.03352.pdf)", we learnt about various aspects of the U-Net architecture by looking at the implementations for these variations. After studying these, we decided to go forward with the vanilla implementation of this model because we wanted to show its scalability on a different dataset (Satellite Imagery). 

### Brain Tumor Segmentation Task (BraTS and LGG Segmentation task)
To get ourselves acclimatized to the Image segmentation problem, we explored different brain tumor datasets and found two which fit our problem the best. We found two powerful datasets: The [BraTS](https://www.kaggle.com/datasets/dschettler8845/brats-2021-task1) dataset and the [LGG Segmentation](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation) dataset. The BraTS dataset is a much superior dataset to the LGG dataset in various aspects (image quality, highly modal images, number of data points etc). From the two datasets presented above, it is clear that the amount of data present in even one MRI image is huge which requires great computation power to process. Further, in various implementations of BraTS challenge it was found that only one high contrast modal of image is sufficient to get good results.

### Satellite Imagery Segmentation Task (Road and Building Detection Datasets)
We then implemented the model on satellite images [dataset](https://www.cs.toronto.edu/~vmnih/data/) (Massachusetts Roads Dataset). Satellite Image Segmentation, as medical image segmentation, is a challenging task because both these tasks use high resolution multimodal images. In both these tasks, annotations usually require in-depth domain knowledge which require special tools for data analysis. The deep learning model tries to analyse and extract these features without any human intervention or use of any tool. In this work, we run our optimized UNet model specifically for segmentation of road. Obstruction from nearby trees, shadows of adjacent buildings, varying texture and color of roads, road class imbalance (due to relatively few road image pixels) are among other challenges that hinder present day models in segmenting sharp road boundaries that extend from one end of the image to the other. That would be something we would work on to fine tune our model for better results overall.

## Project Visualisation

### Brain Tumor Segmentation Task (BraTS and LGG Segmentation task)
|![](/images/brain_tumor_1.png)|
|:--:|
|<b>MRI Scan vs Annotated Mask</b>|

|![](/images/brain_tumor_2.png)|
|:--:|
|<b>Original vs Resized vs Contrast Changed</b>|

|![](/images/brain_tumor_3.png)|
|:--:|
|<b>Input vs Actual Mask vs Predicted mask</b>|

|![](/images/brain_loss.png)|
|:--:|
|<b>Loss vs Epoch</b>|

### Satellite Imagery Segmentation Task (Road and Building Detection Datasets)
|![](/images/satellite_1.png)|
|:--:|
|<b>Satellite Image vs Mask of roads</b>|

|![](/images/satellite_2.png)|
|:--:|
|<b>Original vs Resized vs Contrast Changed</b>|

|![](/images/satellite_3.png)|
|:--:|
|<b>Input vs Actual Mask vs Predicted mask</b>|

|![](/images/satellite_loss.png)|
|:--:|
|<b>Loss vs Epoch</b>|

For more detailed analysis, please refer to the report.

## Future Scope
Now that we have tackled both these segmentation tasks we can now properly comment on how these tasks were similar yet different. We used similar techniques on the Satellite imagery dataset as we have used on the Brain tumor segmentation and got decent results which works as a proof of concept. If we use more efficient preprocessing techniques for the satellite images, something which tackles that kind of data specifically, then we can fairly assume that it will give us better if not similar results as we have obtained.

One approach for handling big images is by creating smaller ???tiles??? that can be easier to process, yet encapsulate the data efficiently. While resizing would have caused some information loss, by tiling we can tackle the problem more efficiently with minimal information loss. 

Further we can use relatively new attention based U-Net model on time series data of images like Deforestation data (satellite) and longitudinal MRI data of brain scans to observe how the model behaves when the temporal aspect is added. This only showcases one of the few possible problem domains that can be experimented with efficiently.

## Contribution
In this work, we verified that UNet image segmentation model which was essentially designed for medical imagery can also be used for Satellite image segmentation task. It draws parallel between the two important tasks and shows that optimization made for one task can be used for the other.

## Useful Links
- [Google Colab Notebook](https://colab.research.google.com/drive/1TSZzebxKgndebXF3Q-oe4XQRq2lczZzy?usp=sharing) (We have also uploaded the .ipynb file in our repo)

## Steps to follow
- We have provided the Colab link that we used for our implementation, which properly documents our results. For the Brain tumor dataset, we need to upload a "kaggle.json" file (refer to this [link](https://medium.com/analytics-vidhya/how-to-fetch-kaggle-datasets-into-google-colab-ea682569851a) for the same) before we can call the dataset directly from kaggle into Colab.
