# Google Street View Images Blur Detection
**Dataset:**  <br/>
[UCF Google Street View dataset](https://www.crcv.ucf.edu/data/GMCP_Geolocalization/) contains 62,058 high quality Google Street View images, 10000 images is used to train and evaluate "Street View Images Blur Dtection Network - SVIBDN"<br/>
<br>
**Milestones:**  
- Generating Google Street View Images Blur Dataset. [Click](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/google_street_view_images_generating_dataset.ipynb)<br/>
- Building Computer Vison Model for Street View Images Classification and Blurred Regions Segmentation. [Click](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection/blob/main/New_SVIBDN.ipynb)<br/>
- Training and Evaluation <br/>
- Using Implemented model in Production and Real World Web Application. [Click](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection-Web-Application) <br/>
<img width="810" alt="Screenshot 2022-07-08 at 21 28 25" src="https://user-images.githubusercontent.com/43514418/178058213-aa229f2c-5ea7-47a4-8564-839bdbaacaa1.png"> <br/>
Total params: 79,826,048 <br/>
Trainable params: 79,772,928 <br/>
Non-trainable params: 53,120 
# Generating Dataset
Original images from dataset
<img width="1097" alt="Screenshot 2022-06-16 at 22 29 09" src="https://user-images.githubusercontent.com/43514418/174158395-51cd6eab-512e-4f54-b413-b1e7365fcc88.png"> <br/>
Applying GaussianBlur filter to original images, randomly for different regions of images <br/>
<img width="1088" alt="Screenshot 2022-06-16 at 22 29 26" src="https://user-images.githubusercontent.com/43514418/174158430-d5d81c7e-192b-48cc-88a4-70eabdca234b.png"> <br/>
Generating ground-truth for blurred images 
<img width="1085" alt="Screenshot 2022-06-16 at 22 29 43" src="https://user-images.githubusercontent.com/43514418/174158476-56d6c248-0d27-413e-85b4-0b109895f396.png"><br/>
# Training and Validation
80% of the input photos(7000 images) were used for training, and 20% were utilized for validation. <br/>
<img width="551" alt="Screenshot 2022-07-08 at 21 15 52" src="https://user-images.githubusercontent.com/43514418/178056585-62415625-e395-4424-aec4-3c4e9558fe66.png"><br/>
<img width="537" alt="Screenshot 2022-07-08 at 21 14 32" src="https://user-images.githubusercontent.com/43514418/178056620-3a3423b8-e431-428a-9706-2c89b7e86f00.png">
<img width="537" alt="Screenshot 2022-07-08 at 21 11 07" src="https://user-images.githubusercontent.com/43514418/178056680-cedee277-22a7-49d5-af1d-558e163a0ed1.png"><br/>
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
# Google Street View Images Blur Detection Web Application
To access Web Application repository and installation instruction click [here](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection-Web-Application)








