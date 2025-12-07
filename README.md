
# 🏀 Basketball CV & OCR Pipeline

**Automated Detection of Symbols, Names & Numbers from Basketball Scoresheets**

This repository contains a **computer vision (CV) and optical character recognition (OCR)** system designed to extract structured data from scanned or photographed **basketball scoresheets**. The goal is to automate the traditionally manual and time-consuming task of **basketball game data tagging**, enabling faster analytics, enhanced accuracy, and real-time data ingestion for stats platforms.

---

## 🚀 Project Overview

Basketball scoresheets often include:

* Player names
* Jersey numbers
* Fouls and foul types
* Timeouts
* Points scored
* Quarter-by-quarter breakdown
* Team information
* Referee or table notes
* Special symbols (e.g., X, //, ⧫, triangles, circles)

Manually transcribing and digitizing this information is error-prone.
This project provides a **robust automated pipeline** to read these sheets using modern computer vision techniques.

---

## 🧠 Key Features

### ✔ Symbol Detection

Detects handwritten or printed symbols commonly found on scoresheets:

* Fouls (P, U, T, etc.)
* Crosses, slashes, triangles, circles
* Checkmarks and special annotations

### ✔ Name & Number OCR

Uses OCR models fine-tuned for:

* Player names (often handwritten or stylized)
* Jersey numbers (printed bold or handwritten)
* Coach/staff names
* Team identifiers

### ✔ Layout Parsing

Automatically localizes:

* Player rows
* Score grids
* Fouls table
* Points-by-quarter blocks
* Metadata regions

### ✔ Multi-model Ensemble

Combines:

* **Object detection** for symbols
* **OCR models** for text regions
* **Post-processing rules** for alignment and consistency checking
* **Layout analysis** (e.g., YOLO, Detectron2, or custom segmentation)

---

## 🛠️ Tech Stack

This project may include combinations of the following (customize depending on your repo):

* **OpenCV** — preprocessing, thresholding, line detection
* **RFDETR** - object detection for symbols & regions
* **YOLOv8/YOLOv11** — object detection for symbols & regions
* **Tesseract / EasyOCR / PaddleOCR** — text recognition
* **NumPy / Pandas** — data structuring


---

## 📂 Pipeline Overview

```
1. Image Preprocessing  
    • Deskew, denoise, binarize  
    • Detect and crop table regions

2. Region Detection (CV/ML)
    • Player rows and score columns  
    • Symbol bounding boxes  
    • Name/number fields  

3. RF DETR/ Yolo/ OCR Pass
    • Recognize names, numbers, labels  
    • Validate with dictionaries / team rosters  

4. Symbol Classification
    • Detect fouls, timeouts, scoring markings  

5. Post-Processing
    • Resolve conflicts  
    • Align rows & columns  
    • Reconstruct complete scoresheet data  

6. Output
    • JSON / CSV structured format  
    • Ready for automated tagging or ingestion  
```


## 🎯 Use Cases

* Automated basketball data entry
* Real-time stat generation
* Digitizing historical gamesheets
* Team analytics platforms
* Referee and table official workflow tools
