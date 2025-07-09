# Face-Mask-Detection

This project uses a Convolutional Neural Network (CNN) with **MobileNetV2** architecture to detect whether people are wearing face masks in real-time via webcam feed.

## 🧠 Overview

The system is built using:

* **TensorFlow / Keras** for training the model
* **OpenCV** and **imutils** for video stream processing
* **MobileNetV2** as the backbone of the model
* Real-time detection via webcam with bounding boxes and labels

---

## 📁 File Structure

```
.
├── detect_mask_video.py         # Real-time face mask detection using webcam
├── train_mask_detector.py       # Script to train the mask detection model
├── face_detector/               # Contains deploy.prototxt and res10_300x300_ssd_iter_140000.caffemodel
├── dataset/                     # Contains 'with_mask' and 'without_mask' image folders
├── mask_detector.model          # Trained face mask detection model (output)
├── plot.png                     # Training loss and accuracy plot
└── README.md                    # Project documentation
```

---

## 🛠️ Setup

### 1. Install Dependencies

```bash
pip install tensorflow opencv-python imutils matplotlib sklearn
```

### 2. Dataset Preparation

Organize your dataset folder as:

```
dataset/
├── with_mask/
├── without_mask/
```

Each folder should contain images of people **with** and **without** masks respectively.

---

## 🧪 Training the Model

Run the following to train the model and generate `mask_detector.model`:

```bash
python train_mask_detector.py
```

This will also output a training graph `plot.png` and save the model to disk.

---

## 📷 Real-Time Detection

Once trained, run the following script to start the webcam and perform live detection:

```bash
python detect_mask_video.py
```

Make sure the following files are present:

* `mask_detector.model`
* Face detection model files in `face_detector/`:

  * `deploy.prototxt`
  * `res10_300x300_ssd_iter_140000.caffemodel`

---

## 📈 Results

* Labels shown on webcam: **"Mask"** (green) or **"No Mask"** (red)
* Confidence score is displayed next to each detection

---

## 🧑‍💻 Author

Developed by **\[Your Name Here]**
Feel free to fork and contribute!

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
