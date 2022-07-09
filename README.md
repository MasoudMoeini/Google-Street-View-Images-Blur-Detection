# Google StreetView Images Blur Detection
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
# Training and Evaluation 
<img width="551" alt="Screenshot 2022-07-08 at 21 15 52" src="https://user-images.githubusercontent.com/43514418/178056585-62415625-e395-4424-aec4-3c4e9558fe66.png"><br/>
<img width="537" alt="Screenshot 2022-07-08 at 21 14 32" src="https://user-images.githubusercontent.com/43514418/178056620-3a3423b8-e431-428a-9706-2c89b7e86f00.png">
<img width="537" alt="Screenshot 2022-07-08 at 21 11 07" src="https://user-images.githubusercontent.com/43514418/178056680-cedee277-22a7-49d5-af1d-558e163a0ed1.png"><br/>
# Evaluation of Model with 1000 Images
- Confusion Matrix (Classification) <br/>
<img width="431" alt="Screenshot 2022-07-08 at 19 16 31" src="https://user-images.githubusercontent.com/43514418/178040259-f96dd881-613e-470a-a2b3-9fd925dca5e7.png"> <br/>
- Intersection over Union -IoU- (Segmentation ) <br/>
Average Intersection over Union for Blur Detection:  **0.917568**    <br/> 
- Input images <br/> 
<img width="743" alt="Screenshot 2022-07-01 at 08 20 54" src="https://user-images.githubusercontent.com/43514418/176836771-0430e134-f992-41a9-bd50-e24778f8a7bf.png"> <br>
- Predicted Labels <br/>
<img width="741" alt="Screenshot 2022-07-01 at 08 20 00" src="https://user-images.githubusercontent.com/43514418/176836818-6eb64ba7-a8c7-48b2-993e-05f2036f8253.png"> <br>
- Applying label to Input Images and high lighting blurred areas <br/>
<img width="743" alt="Screenshot 2022-07-01 at 08 18 03" src="https://user-images.githubusercontent.com/43514418/176836909-91d520dd-0e64-45fc-b876-6396503c33b7.png"> <br>
- Input images <br/> 
<img width="744" alt="Screenshot 2022-07-01 at 08 20 24" src="https://user-images.githubusercontent.com/43514418/176836987-a3193000-d408-4c5d-9aea-9165eb8e2f6a.png"> <br>
<img width="740" alt="Screenshot 2022-07-01 at 08 19 37" src="https://user-images.githubusercontent.com/43514418/176837046-1191dd81-790d-4cad-a8c1-ef0bbb975828.png"> <br>
<img width="743" alt="Screenshot 2022-07-01 at 08 18 58" src="https://user-images.githubusercontent.com/43514418/176837094-2b5905e7-dd7b-4f69-9c34-1aeeb92ae199.png"> <br/>
# Google Street View Images Blur Detection Web Application
To access Web Application repository and installation instruction click [here](https://github.com/MasoudMoeini/Google-Street-View-Images-Blur-Detection-Web-Application)








