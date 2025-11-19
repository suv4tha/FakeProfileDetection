# FakeProfileDetection — Instagram Account Authenticity Prediction System

[![Repo size](https://img.shields.io/badge/repo-ready-brightgreen)]()
[![Python](https://img.shields.io/badge/python-3.8%2B-blue)]()
[![License](https://img.shields.io/badge/license-MIT-lightgrey)]()

> Automated system to evaluate public Instagram profiles and produce a **suspicion score** indicating whether an account is likely real or fake.

This repository contains the code, data, and model artifacts for the Instagram Account Authenticity Prediction System. 

---

## Table of contents

- [Project Overview](#project-overview)  
- [Features](#features)   
- [Installation](#installation)  
- [Usage](#usage)  
- [Dataset](#dataset)  
- [Model & Inference](#model--inference)  
- [Evaluation & Example Results](#evaluation--example-results)  
- [Screenshots / Images](#screenshots--images)  
- [Contributing](#contributing)  
- [License](#license)  
- [Contact](#contact)

---

## Project Overview

The system programmatically extracts public Instagram profile metadata, computes engineered features, and uses a pre-trained ML classifier to generate a **suspicion score** (0 — likely real, 1 — likely fake). The pipeline supports username or profile URL input, automatic scraping using `instagrapi`, feature alignment, model inference, and human-friendly explanations.

More details and the design rationale are in the project report: **PROJECT REPORT.pdf**. :contentReference[oaicite:2]{index=2}

---

## Features

- Authenticated scraping of public Instagram profile metadata (via `instagrapi`)
- Deterministic feature engineering (profile picture, bio length, follower/following ratio, etc.)
- Pre-trained classifier for binary probability output with simple interpretation thresholds:
  - `< 0.30` — Low suspicion (Likely real)  
  - `0.30–0.60` — Medium suspicion (Needs review)  
  - `> 0.60` — High suspicion (Likely fake)
- Command-line and programmatic prediction interfaces
- Explanation snippets to justify predictions (e.g., “No profile picture”, “External link in bio”)

---

## 🔧 Installation

```bash
git clone https://github.com/suv4tha/FakeProfileDetection.git
cd FakeProfileDetection
pip install -r requirements.txt
```
▶️ Usage

Run the notebook:
```
jupyter notebook notebooks/analysis.ipynb

```
If using the model programmatically:
```
import joblib
model = joblib.load("model.pkl")
score = model.predict_proba([features])[0][1]
print("Suspicion Score:", score)
```
## 📊 Dataset

The dataset consists of two CSV files containing public Instagram profile metadata used for:

Model training

Feature engineering

Validation

## 🖼️ Screenshots

![Prediction (Real)](Screenshots/Prediction(Real).png)
![Prediction (Fake)](Screenshots/Prediction(Fake).png)

## 📘 Project Report

📄 **[Download Full Project Report](Report/PROJECT%20REPORT.pdf)**


## 👩‍💻 Author

Suvetha O , Carolrebecca M , Monisha C
Instagram Fake Profile Detection — ML Project (2025)

