# Google Street View Images Blur Detection
**Dataset:**  <br/>
[UCF Google Street View dataset](https://www.crcv.ucf.edu/data/GMCP_Geolocalization/) contains 62,058 high quality Google Street View images.<br>
5000 images from UCF is used for creating of Street View Blur Image Dataset (SVBI).<br>
This repository presents "Street-view images Blur Detection Network (SBDNet) using SVBI dataset for training and evaluation.<br/>
<br>
**Milestones:**  
- Generating Street View Blur Image Dataset (SVBI). [Click](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SVIB_dataset_generating_with_object_detection.ipynb)<br/>
- Building Computer Vison Model for Street View Images Classification and Blurred Regions Segmentation using two architectures (Arc.1 using ResNet50, Arc.2 using GoogLeNet).<br/>
Click-> [SBDNet-ResNet50](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_ResNet_Exp_SVBI.ipynb)<br/>
Click-> [SBDNet-GoogLeNet](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_GoogleNet_Exp_SVBI.ipynb)<br/>
- Training and Evaluation using public blur detection datasets. <br/>
Click-> [SBDNet-ResNet50-Experiment-1](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_ResNet_Exp1_CHUK_DUT_SZU.ipynb)<br/>
Click-> [SBDNet-GoogLeNet-Experiment-1](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_GoogleNet_Exp1_CHUK_DUT_SZU.ipynb)<br/>
Click-> [SBDNet-ResNet50-Experiment-2](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_ResNet_Exp2_CHUK_DUT_SZU.ipynb)<br/>
Click-> [SBDNet-GoogLeNet-Experiment-2](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_GoogleNet_Exp2_CHUK_DUT_SZU.ipynb)<br/>
Click-> [SBDNet-GoogLeNet-Experiment-1-Precision-Recall-Comparison](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_GoogleNet_Exp__DBEFPNet_CHUK_SZU.ipynb)<br/>
- Using Implemented model in Production and Real World Web Application. [Click](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection-Web-Application) <br/><br/>  
**SBDNet Network Architecture using ResNet50 as a Classifier network**  <br/> 
![fig-sbdn-arc-svbi](https://user-images.githubusercontent.com/43514418/209338501-7185861a-a9cd-46ec-b63b-e5ca71062068.jpg)<br/>
Total params: 93,579,837 <br/>
Trainable params: 93,526,717 <br/>
Non-trainable params: 53,120 <br/><br/>   
**SBDNet Network Architecture using GoogLeNet as a Classifier network**  <br/> 
![fig-sbdnet-googlenet](https://user-images.githubusercontent.com/43514418/209336368-69c4180a-a3df-42b9-b80d-55f425bf3abc.jpg)
Total params: 19,439,381 <br/>
Trainable params: 19,438,869 <br/>
Non-trainable params: 512 <br/><br> 
**Identifier Network Architecture**  <br/>  
<img width="1088" alt="Screenshot 2022-11-16 at 12 04 17" src="https://user-images.githubusercontent.com/43514418/202164466-8d6f7cce-e85a-4ef6-b6a6-acf08f4d46dd.png"><br/>
# Generating Dataset
Original images from dataset
<img width="1097" alt="Screenshot 2022-06-16 at 22 29 09" src="https://user-images.githubusercontent.com/43514418/174158395-51cd6eab-512e-4f54-b413-b1e7365fcc88.png"> <br/>
Applying GaussianBlur filter to original images, randomly for different regions of images <br/>
<img width="1088" alt="Screenshot 2022-06-16 at 22 29 26" src="https://user-images.githubusercontent.com/43514418/174158430-d5d81c7e-192b-48cc-88a4-70eabdca234b.png"> <br/>
Generating ground-truth for blurred images 
<img width="1085" alt="Screenshot 2022-06-16 at 22 29 43" src="https://user-images.githubusercontent.com/43514418/174158476-56d6c248-0d27-413e-85b4-0b109895f396.png"><br>
# Revised Street View Blure Detection dataset using object detection algorithm
**Haar feature-based cascade classifiers**  [Ref](https://docs.opencv.org/3.4/dc/d88/tutorial_traincascade.html)<br>
[Rastogi et al. 2019](https://link.springer.com/content/pdf/10.1007/s12206-019-0339-5.pdf)<br>
![fig-SVIBdataset-total](https://user-images.githubusercontent.com/43514418/209407525-975ae6ce-bda8-483d-a777-fa3e9f65f967.jpg)
<br>
# Training and Validation
The model was trained and validated by using 2000 input images.<br/>
80% of the input photos were used for training, and 20% were utilized for validation.<br>
![Screenshot 2023-01-05 at 12 56 34](https://user-images.githubusercontent.com/43514418/210775488-03017e21-fcad-4c35-8622-c4e38cf7689a.png)<br/>
# Evaluation of Model with 1000 Images
The model was evaluated by using 1000 input images for classification and blur detection <br/>
- Confusion Matrix (Classification) <br/>
![Screenshot 2023-01-05 at 12 56 13](https://user-images.githubusercontent.com/43514418/210777661-bbf82311-a85b-43b0-948a-d561b50a1999.png)<br/>
- Intersection over Union (IoU)(Blur Map estimation) <br/>
Average Intersection over Union for Blur Detection: 0.9334 <br/> 
- Input images <br/> 
<img width="1057" alt="Screenshot 2022-07-09 at 22 43 22" src="https://user-images.githubusercontent.com/43514418/178122159-69beb9bd-4126-4cb6-8786-ceb033795499.png"> <br/> 
- Predicted Labels and Classification results: Predicted Class/True Class (0.0 bur, 1.0 no blur) <br/>
<img width="1058" alt="Screenshot 2022-07-09 at 22 44 54" src="https://user-images.githubusercontent.com/43514418/178122192-09b7fda9-1c7b-4e3d-bebb-8b3a4edcb87b.png"> <br/> 
- Applying predicted labels to Input Images and high lighting blurred areas <br/>
<img width="1059" alt="Screenshot 2022-07-09 at 22 42 31" src="https://user-images.githubusercontent.com/43514418/178122256-d5857491-407c-47e5-b0ea-d84c1cea2bab.png"><br>
- Input images <br/> 
<img width="1057" alt="Screenshot 2022-07-09 at 22 46 40" src="https://user-images.githubusercontent.com/43514418/178122277-c4781495-99f1-43ce-ad1c-ac056b8814c0.png"><br>
<img width="1057" alt="Screenshot 2022-07-09 at 22 47 33" src="https://user-images.githubusercontent.com/43514418/178122297-165ad5e2-3d13-4219-9888-b9ed585b28c5.png"><br>
<img width="1056" alt="Screenshot 2022-07-09 at 22 41 49" src="https://user-images.githubusercontent.com/43514418/178122332-40fd8058-f555-4c7d-be18-1f5dc4cfdb95.png"><br/>
- Implementing Class Activation Map-[CAM](https://towardsdatascience.com/class-activation-mapping-using-transfer-learning-of-resnet50-e8ca7cfd657e) 
To identify the specific regions that Classifier network is looking at while classifying an input images <br/>
![fig-final-demo](https://user-images.githubusercontent.com/43514418/210445743-229b755b-3de7-4877-874e-b1bd9c01ba4f.jpg)<br/>
# Comparison with other State of Art Methods(CHUK,DUT,SZU-BD) based-on Shi et al dataset
![fig-Comparison](https://user-images.githubusercontent.com/43514418/209339564-c94c0964-19b3-4a34-aadd-ab4f5ed39711.jpg)<br/>
![fig-sbdnet-eval-chuk](https://user-images.githubusercontent.com/43514418/210374952-690efe99-ba38-4078-886a-fdb54c72f6f1.jpg)<br/>
SBDNet best evaluation results on CHUK,DUT,SZU-BD datasets <br/>
<img width="733" alt="Screenshot 2023-01-03 at 14 31 49" src="https://user-images.githubusercontent.com/43514418/210367091-31f5c9ad-0b06-432d-8536-c1cc0947ab80.png"><br/>
Comparison with other methods on CHUK dataset based on collected results from [Sun et al.(DB-EFPN)](https://www.sciencedirect.com/science/article/abs/pii/S0925231220310560)<br/>
<img width="458" alt="Screenshot 2023-01-03 at 14 31 37" src="https://user-images.githubusercontent.com/43514418/210367805-8d333428-a8f9-4f49-af9a-9db85a177ae5.png"><br/>
# Google Street View Images Blur Detection Web Application
To access Web Application repository and installation instruction click [here](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection-Web-Application) 
<br>
# Resources
- [Keras - Computer Vision](https://keras.io/examples/vision/)
- [ResNet50](https://machinelearningknowledge.ai/keras-implementation-of-resnet-50-architecture-from-scratch/)
- [GoogLeNet](https://www.kaggle.com/code/luckscylla/googlenet-implementation/script)
- [UCF Google Street View Images dataset](https://www.crcv.ucf.edu/data/GMCP_Geolocalization/)
- [Flask Tutorial](https://roytuts.com/upload-and-display-image-using-python-flask/)










