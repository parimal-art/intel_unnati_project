# Project Title
Enhancing Customer Experience with AI-Driven Insights for Online Shopping
# Problem Statement
Offering a customized and interactive try-on experience is crucial in the quickly expanding online retail sector to increase customer satisfaction and conversion rates. The inability to virtually try on sunglasses and see how they would appear makes customers hesitant to buy them online. The difficulty lies in developing an AI-powered system that uses both real-time and customer-uploaded photos to facilitate a smooth virtual try-on process for sunglasses, thus enhancing the online shopping experience.
# Goal
The goal of this project is to create an AI-powered system that allows users to virtually try on sunglasses, improving the online shopping experience. The system is going to:

**Allow for two different operating modes:**

**Static Image Mode:** Let clients try on sunglasses and upload a previously taken picture.

**Real-Time Capture Mode:** Use the webcam to take a single picture (not a video) and then put on sunglasses to simulate wearing them.

Utilize customer behavior data and real-time image analytics to customize the try-on process.
To increase user engagement, create an intuitive user interface with features like file name display, side-by-side input and output image comparison, and a contemporary design.
# Overview of the Project
By allowing users to virtually try on sunglasses, this project, called "Sunglasses Try-On Studio," aims to improve the online shopping experience. It has two modes of operation:

**Static Image Mode:** To try on sunglasses, customers can upload a previously taken picture of their face.

**Real-Time Capture Mode:** customers can use their webcam to take a single picture, which is then processed to overlay sunglasses so they can try them on. Keep in mind that this isn't a live video feed; the system only takes one frame and processes it.

To customize the try-on experience, the system leverages AI-driven image analytics (through OpenVINO for facial recognition) and customer behavior data (through image uploads and captures). Important characteristics include:
**Background Removal:** To guarantee a smooth overlay, sunglasses photos' backgrounds are automatically eliminated.

**Face Detection:** Accurately align sunglasses and identify faces using OpenVINO's pre-trained model.

**Image Capture and Processing:** Takes a single webcam image and prepares it for try-on (not a live video feed).

**User-Friendly Interface:** Offers a contemporary user interface with responsive design, side-by-side comparison of input and output images, and file name display.

# Backend Development 
**Framework:** To manage HTTP requests and serve the application, a web server was built using Flask.

**Face Detection:** Faces in still photos and webcam frames were identified using OpenVINO's pre-trained face detection model (face-detection-adas-0001).

**Background Removal:** To remove the background of sunglasses images, the rembg library was utilized. For PNG images with transparent backgrounds, the removal process was skipped.

**Image processing:** The alpha channel was used to crop photos of sunglasses in order to eliminate extra space.

To maintain the sunglasses' original colors, color space conversions (RGB to BGR and vice versa) were managed.
Using the bounding box coordinates from OpenVINO, sunglasses were resized and superimposed on the identified face.

**API Endpoints:**
**/upload_sunglasses**: Removes the background, crops the image, and maintains the color of the sunglasses.

**/upload:** Overlays the sunglasses in a static photo (Static Image Mode).

**/webcam:** Uses the webcam to take a single picture and superimpose the sunglasses (Real-Time Capture Mode).

# Development of Frontends
**UI Design:** Using HTML and CSS, a contemporary, responsive user interface was developed that includes animations, hover effects, and gradient backgrounds to improve the online shopping experience.

**File Uploads:** File uploads, file names, and Static Image Mode previews were all handled by JavaScript.

**Integration of Webcams:** The webcam was accessed, a single image (not a video) was taken, and it was processed for the Real-Time Capture Mode using the navigator.mediaDevices.getUserMedia API.

Side-by-Side Comparison: To enable customers to compare the try-on outcomes, input and output images were presented side by side in a flexbox layout.

# Important Features and Solutions
**Background Removal Logic:** Added logic to verify that PNG images are truly transparent and to remove the background only when required.

**Color Preservation:** To avoid color shifts during processing, color space conversions were handled.

**Cropping:** To improve alignment, extra space around sunglasses was cropped using the alpha channel.

**UI Improvements:** To improve the user experience when shopping online, side-by-side comparison and file name display were added.
# Architecture Diagram
![graphviz](https://github.com/user-attachments/assets/90f20c5a-a1ce-4db9-9f8a-b2c857bf4e65)
# Output:
To make sure it worked for online shopping, the application was tested in a variety of scenarios. The expected results are listed below.

**Sunglasses Upload Input:** A solid-background PNG picture of sunglasses.

![image](https://github.com/user-attachments/assets/b39bd07b-fa12-47ec-81f7-84cad7159c0e) 

**After processing output:** The processed sunglasses image appears in the preview after the background is eliminated and extra space is cropped.

![image](https://github.com/user-attachments/assets/050e29d5-f0c1-412c-9e84-53cc594cd06f)
# Static Image Mode (Photo Upload)
**Input:** A previously captured photo of a customer’s face and a processed sunglasses image.

**Output:** The sunglasses are overlaid on the face, and the input and output images are displayed side by side.

![image](https://github.com/user-attachments/assets/e050624c-fc32-408a-8c81-071c3cd90d69)

# Real-Time Capture Mode (Webcam)
**Input:** A single image captured via webcam.

**Output:** The captured image with sunglasses overlaid, displayed side by side with the original captured image.
![image](https://github.com/user-attachments/assets/4ac872e3-03ef-4e3c-a83e-6ef43d5c12ca)

# Conclusion
A virtual try-on system for online shopping is successfully implemented by the "Sunglasses Try-On Studio" project, which allows for both static image uploads and real-time webcam image capture. Important characteristics include:

There are two modes: Real-Time Capture Mode for webcam-captured images (single image, not video) and Static Image Mode for previously taken pictures.
Logic-based automatic background removal for proper handling of PNG images.
OpenVINO face detection for precise sunglasses overlay.
Cropping and color preservation for improved alignment.
An easy-to-use interface featuring side-by-side comparison and file name display.








