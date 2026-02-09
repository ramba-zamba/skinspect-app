<img width="80" height="80" alt="logo" src="https://github.com/user-attachments/assets/e9e7fe95-9477-42b2-8748-00554092051d" /> # SkinSpect 


**SkinSpect** is an experimental, on-device Android app that provides **automated image analysis of skin lesion photos** for **awareness and screening support**.

The app uses convolutional neural networks (CNNs) to analyze a cropped image of a skin lesion and indicate whether it **may need medical attention** or shows **no immediate warning signs** in the provided image.

---

## What this repository contains

This repository currently **does not include source code**.

It contains:
-  **Pretrained TensorFlow Lite models**
-  **A signed Android release APK** for local installation and testing
-  No training code
-  No Flutter / Android source code (yet)

---

##  Included models

Two CNN models based on EfficientNet-B1 are provided. Both perform binary classification:

- **GOOD** → likely benign / no immediate concern detected  
- **BAD** → suspicious / may need medical review  

### effb1_stage6b_float32 (balanced)
**Download** → from Google Storage: https://storage.googleapis.com/skinspect-app/effb1_stage6b_float32.tflite

| Metric | Value |
|------|------|
| Sensitivity (Recall) | 0.815 |
| Specificity | 0.921 |
| Precision | 0.715 |
| Accuracy | 0.901 |
| Error rate | 0.099 |
| F1 score | 0.762 |

**Characteristics**
- Fewer false alarms
- Calmer user experience
- Higher risk of missing some suspicious lesions

---

### effb1_stage6_float32 (more sensitive)
**Download** → from Google Storage: https://storage.googleapis.com/skinspect-app/effb1_stage6_float32.tflite

| Metric | Value |
|------|------|
| Sensitivity (Recall) | 0.913 |
| Specificity | 0.863 |
| Precision | 0.618 |
| Accuracy | 0.873 |
| Error rate | 0.127 |
| F1 score | 0.737 |

**Characteristics**
- Flags more lesions as suspicious
- Higher false-positive rate
- Lower risk of missing suspicious cases

---

## Model comparison (plain language)

- **Stage6 (more sensitive)**  
  → Better at catching suspicious lesions  
  → More false alarms

- **Stage6b (balanced)**  
  → Fewer false alarms  
  → May miss more suspicious cases

For consumer skin-screening use, **higher sensitivity is generally safer**, as false reassurance can be more harmful than false alarms.

---

## APK

A signed Android **release APK** is included for local installation.

### Installation notes
-  Download from Google Storage (Account required): https://storage.googleapis.com/skinspect-app/app-release.apk 
- Android 5.0+ (minSdk 21)
- Enable **“Install unknown apps”** on your device
- If upgrading from a debug build, uninstall the old version first

---

## Medical & regulatory disclaimer

SkinSpect:
-  Does **not** diagnose skin cancer or any disease
-  Does **not** replace professional medical evaluation
-  Should **not** be used for treatment decisions

The app provides **automated image analysis** for **awareness and screening support only**.

---

## Privacy

- All analysis runs **entirely on-device**
- No internet connection required
- No images are uploaded or stored externally

---

##  Project status

- Experimental / research-oriented
- Actively evolving
- Source code may be released later

---

##  License

Model files and APK are provided for **evaluation and research purposes**.  
No warranty is provided.

---

## Contact

For questions, feedback, or research collaboration, please open an issue or contact the repository owner.

---

**Be curious — but stay safe.**
