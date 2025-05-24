# thermal-uav-animal-detection
Detection of animals in UAV thermal images using CNN-based features and Balanced Random Forest (BRF) classification
This project focuses on the **detection of animals in UAV thermal images** using a combination of **CNN-based feature extraction** and classification with a **Balanced Random Forest (BRF)** model.  
The solution was developed during a research internship and is accompanied by a peer-reviewed article describing the methodology.

---

## 📁 Project Structure

```text
thermal-uav-animal-detection/
├── 01_Feature_extraction.ipynb               # Extracts thermal, geometric & CNN-based features
├── 02_BRF_training.ipynb                     # Trains a Balanced Random Forest model
├── 03_BRF_prediction_and_visualization.ipynb # Applies model & visualizes results
├── requirements.txt                          # Python dependencies
├── README.md                                 # Project documentation (this file)
└── data/
    ├── thermal_images/       # 🔸 MUST BE CREATED MANUALLY
    │                           Thermal images (e.g. 00-01-01.tif)
    ├── cnn_model/            # Saved CNN model (optional)
    ├── cnn_activations/      # CNN feature maps (activations)
    ├── result_features/      # Extracted segment features
    ├── brf_model/            # Saved Balanced Random Forest model
    │   ├── optuna/           # Optuna optimization results
    │   └── results/          # Saved results on test and validation data
    └── predictions/          # Saved prediction results
```

## Image Folder Requirement
The folder data/thermal_images/ has to be created manually before running any notebook.
It is strongly recommended to name the thermal images using the HH-MM-SS pattern (e.g. 00-01-01.tif).
This prevents sorting issues such as 1, 10, 11, … 2, 20, 21 … and guarantees correct temporal order.

## Installation
### Python ≥ 3.10 is recommended
```bash
pip install -r requirements.txt
```

## How to Use
1. `01_Feature_extraction.ipynb`  
   Detects segments in thermal images, extracts geometric, thermal, and CNN features.

2. `02_BRF_training.ipynb`  
   Loads features, balances the dataset, trains a Balanced Random Forest classifier, and evaluates performance using cross-validation.

3. `03_BRF_prediction_and_visualization.ipynb`  
   Applies the trained BRF model to new image features and visualizes detection results on thermal image overlays.

## 📑 Article
This repository is accompanied by a scientific publication that details the dataset, methodology and evaluation.
Some parameters may differ slightly, but the core workflow remains unchanged.

Citation (in English):
> D. Włodarczyk, G. Jóźków *Hoofed animal detection in UAV thermal images using
Balanced Random Forest and CNN features* Reports on Geodesy and Geoinformatics, Submitted, 2025.

Not available yet

## License
Licensed under the Apache License 2.0.
See the LICENSE file for full details.
