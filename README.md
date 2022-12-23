# Google Street View Images Blur Detection
**Dataset:**  <br/>
[UCF Google Street View dataset](https://www.crcv.ucf.edu/data/GMCP_Geolocalization/) contains 62,058 high quality Google Street View images, 10000 images is used to train and evaluate "Street View Images Blur Dtection Network"<br/>
<br>
**Milestones:**  
- Generating Street View Blur Image Dataset (SVBI). [Click](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SVIB_dataset_generating_with_object_detection.ipynb)<br/>
- Building Computer Vison Model for Street View Images Classification and Blurred Regions Segmentation using two architectures (ResNet50, GoogLeNet).<br/>
Click-> [SBDNet-ResNet50](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_ResNet_Exp_SVBI.ipynb)<br/>
Click-> [SBDNet-GoogLeNet](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/SBDN_GoogleNet_Exp_SVBI.ipynb)<br/>
- Training and Evaluation <br/>
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
The model was trained and validated by using 7000 input images. <br/>
80% of the input photos were used for training, and 20% were utilized for validation. <br>
<br>
<img width="551" alt="Screenshot 2022-07-08 at 21 15 52" src="https://user-images.githubusercontent.com/43514418/178056585-62415625-e395-4424-aec4-3c4e9558fe66.png"><br/>
<img width="734" alt="Screenshot 2022-12-03 at 01 28 08" src="https://user-images.githubusercontent.com/43514418/205412878-a4471512-1438-4992-963b-c11d0d49b46a.png">
<br/>
# Evaluation of Model with 1000 Images
- Confusion Matrix (Classification) <br/>
<img width="431" alt="Screenshot 2022-07-08 at 19 16 31" src="https://user-images.githubusercontent.com/43514418/178040259-f96dd881-613e-470a-a2b3-9fd925dca5e7.png"> <br/>
- Intersection over Union -IoU- (Segmentation) <br/>
Average Intersection over Union for Blur Detection:  **0.917568**    <br/> 
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
# Comparison with other State of Art Methods based-on Shi et al dataset
![fig-Comparison](https://user-images.githubusercontent.com/43514418/209339564-c94c0964-19b3-4a34-aadd-ab4f5ed39711.jpg)<br/>
<img width="388" alt="Screenshot 2022-10-07 at 12 01 03" src="https://user-images.githubusercontent.com/43514418/194530188-ea26f588-15aa-4ca4-bd0b-9f7aac33ab2b.png"><br/>
<img width="361" alt="Screenshot 2022-10-07 at 12 01 19" src="https://user-images.githubusercontent.com/43514418/194530484-feb13a31-7ec2-419d-a0fe-b17ddf0dd7f9.png"><br/>
<img width="811" alt="Screenshot 2022-10-07 at 12 09 04" src="https://user-images.githubusercontent.com/43514418/194530588-6220cbc7-8520-420f-99a7-1fea4cf6a79b.png"><br>
<img width="525" alt="Screenshot 2022-10-07 at 12 25 12" src="https://user-images.githubusercontent.com/43514418/194532958-9a6d0cb1-5455-499d-9dab-cb1846246691.png"><br>
<img width="884" alt="Screenshot 2022-11-15 at 18 07 26" src="https://user-images.githubusercontent.com/43514418/201982509-7d04eca2-2f7e-48c0-be0d-4dfccab851f0.png"><br>
<img width="447" alt="Screenshot 2022-12-02 at 14 23 12" src="https://user-images.githubusercontent.com/43514418/205302551-a7227df7-1858-4da3-952d-a538585c86b2.png"><br>
Implementing Class Activation Map 
To identify the region a CNN is looking at while classifying an image [Ref](https://towardsdatascience.com/class-activation-mapping-using-transfer-learning-of-resnet50-e8ca7cfd657e)
<img width="825" alt="Screenshot 2022-10-21 at 12 48 41" src="https://user-images.githubusercontent.com/43514418/197180570-275bac85-bc31-423f-bce1-fb68a74f86a8.png"> <br>
# Google Street View Images Blur Detection Web Application
To access Web Application repository and installation instruction click [here](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection-Web-Application) 
<br>
# Resources
- [Keras - Computer Vision](https://keras.io/examples/vision/)
- [ResNet50](https://machinelearningknowledge.ai/keras-implementation-of-resnet-50-architecture-from-scratch/)
- [GoogLeNet](https://www.kaggle.com/code/luckscylla/googlenet-implementation/script)
- [UCF Google Street View Images dataset](https://www.crcv.ucf.edu/data/GMCP_Geolocalization/)
- [Flask Tutorial](https://roytuts.com/upload-and-display-image-using-python-flask/)










