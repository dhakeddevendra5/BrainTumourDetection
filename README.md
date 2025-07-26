# 🧠 Brain Tumor Detection Using CNN

## 🔍 Overview
![](https://github.com/dhakedevendra5/BrainTumourDetection/blob/main/Assets/AnimationBrain-min.gif)
![](https://github.com/dhakedevendra5/PROJECT-BRAIN-TUMOR-DETECTION/blob/main/Assets/an_overview_of_brain_tumours.png)

This project is a web-based application for automated **brain tumor detection** from MRI images using a Convolutional Neural Network (CNN). The goal is to assist medical professionals and patients by providing fast, AI-based preliminary diagnostics. The app is built using **Flask** as the web framework, **TensorFlow/Keras** for the deep learning model, and **MongoDB Atlas** to store patient records and prediction results.

---

## ⚙️ How It Works
![front](https://github.com/dhakedevendra5/PROJECT-BRAIN-TUMOR-DETECTION/blob/main/Assets/Brain.png)
![result](https://github.com/dhakedevendra5/PROJECT-BRAIN-TUMOR-DETECTION/blob/main/Assets/result.png)

1. **Image Upload**  
   Users input personal details and upload a brain MRI image through a web form.

2. **Image Preprocessing**  
   The uploaded image is resized to `128x128`, converted into an array, normalized, and reshaped to match the CNN model's input.

3. **Prediction**  
   The CNN model (`braintumor_binary.h5`) predicts whether a tumor is present.
   - If the output > 0.5 → **Tumor Detected**
   - If the output ≤ 0.5 → **No Tumor Detected**
   - A confidence score is also provided.

4. **Database Logging (MongoDB)**  
   Patient data and prediction results (including timestamp and confidence score) are stored in MongoDB Atlas.

5. **Results Display**  
   The result is displayed to the user, and an admin dashboard (`/dbresults`) shows:
   - Total Patients
   - Tumor Detected
   - No Tumor Detected

---

## 🧪 Model Details

- **Model Name:** `braintumor_binary.h5`  
- **Type:** Binary Classifier (Tumor / No Tumor)  
- **Input Size:** 128x128x3  
- **Output:** Probability between 0 and 1  
- **Framework:** Keras (TensorFlow backend)  

---

## 🛠️ Tech Stack

| Component           | Technology Used                     |
|---------------------|-------------------------------------|
| **Frontend**         | HTML, CSS, Jinja2 (via Flask)       |
| **Backend**          | Python (Flask Framework)            |
| **Deep Learning**    | TensorFlow, Keras (CNN model)       |
| **Database**         | MongoDB Atlas (Cloud NoSQL DB)      |
| **Image Processing** | OpenCV, PIL, NumPy, imutils         |
| **Deployment**       | Localhost / Docker / Cloud-ready    |

---

## 📦 Key Features

- Web UI for MRI upload and diagnosis
- Real-time prediction with confidence score
- MongoDB storage of patient records and results
- Admin dashboard for result analytics
- Secure file handling and cleanup

---

## 📈 Future Enhancements

- Add authentication for doctors/admins
- Improve CNN accuracy with advanced architectures (e.g., ResNet, EfficientNet)
- Add Grad-CAM visualizations for model interpretability
- Email diagnostic reports to patients
- Mobile app version (Flutter/React Native)

---

## 🧬 Sample Flow

1. Run the Flask server:
   ```bash
   python app.py
---

$env:FLASK_APP="app.py"  
flask --app main.py run
