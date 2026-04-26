# Project: ALPR-UKR-BSc-Thesis

## Overview
This repository contains a Bachelor's Thesis in Computer Science focused on an **Automatic License Plate Recognition (ALPR)** system tailored for Ukrainian standards. It integrates vehicle type identification and license plate recognition using modern deep learning architectures and image preprocessing techniques.

## Core Technologies
- **Object Detection:** YOLOv11 (Nano configuration) for real-time localization of vehicles and license plates.
- **OCR:** EasyOCR for text extraction from detected plates.
- **Preprocessing:** 
    - Deskewing (using `galfar/deskew`) to correct perspective.
    - Adaptive Thresholding (OpenCV) for contrast enhancement.
- **Post-processing:** Heuristic error correction based on Ukrainian DSTU 4278:2019 standards and character substitution rules (e.g., O vs 0, I vs 1).

## Dataset
- **Source:** Auto.RIA (Ukrainian used car platform).
- **Size:** 467 images, manually annotated.
- **Classes:** `car`, `truck` (includes vans/pickups), `motorbike` (includes mopeds/quads), `licence_plate`.

## Key Performance Metrics (Competition Revision)
- **Detection (YOLOv11n):**
    - mAP@0.5: 96.3%
    - Licence Plate AP@0.5: 99.2%
    - Optimal F1-score: 0.92 at confidence threshold 0.682.
- **Recognition (OCR):**
    - Overall accuracy: 41.2%
    - Cars: 50.9%
    - Motorbikes: 10.3% (Challenges: sharp angles, multi-line formats, dirt).
    - Error Distribution: Most failures are within 1-2 symbols (Levenshtein distance).

## Project Structure & Citations
- `ВКР Санжаров.pdf`: Original thesis (Citation: **DSTU 8302:2015**).
- `Student Papers Competititon/`: Revised version with bug fixes (Citation: **IEEE**).
- `AI Journal Paper/`: Publication manuscript in Typst format (Citation: **Numbered APA**).
- `ocr.py`, `license_plate_pipeline.py`: Core implementation logic.
- `Model Training.ipynb`, `OCR evaluation.ipynb`: Notebooks for training and analysis.

## Engineering Standards & Session Context
- **Language:** Primary documentation and manuscripts are in **Ukrainian**.
- **Typesetting:** Scientific documents use **Typst** (`.typ`).
- **Verification:** Always reproduce bugs using existing evaluation notebooks before applying fixes. Note the discrepancy between the original thesis results and the revised competition results (bugs fixed in the pipeline).
