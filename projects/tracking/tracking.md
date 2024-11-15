# Overview
The purpose of the POC is to detect and recognize the barcode on the moving vehicle. Additionally, the text on the barcode sticker is also required to be detected using OCR methods.

# Features
The steps involved in the bar code recognition and tracking are as follows:
1. Real-time raw frame 
2. Bar code detector 
3. Crop Barcode as ROI
4. OCR + PYZ (recognition) --> OCR is for the character recognition and PYZ is for the barcode recognition.
5. Recognized ID is used as a tracking ID. If a car is appeared in two cameras, the bar code will be same. Therefore, it is convenient to use the bar code as a tracking ID which resolved ID switch issue in real-time problem.
6. Conclude results

# Challenges
Running Yolov5 + OCR + PYZ sequentialy take too much time. This will lead to loosing frame issues even with multi-threading (due to Python and multi-threading compatibility). Therefore, breaking this process down to Yolov5 and OCR + PYZ. Execute the code in two different terminals.

Note that multi-processing and using seperate terminals are different concepts. Improving the speed by considering multi-processing for both the tasks.
