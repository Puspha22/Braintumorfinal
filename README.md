# Brain Tumor Detection Web Application

[![Python Version](https://img.shields.io/badge/python-3.8%20%7C%203.9-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/framework-Flask%201.1.2-orange.svg)](https://flask.palletsprojects.com/)
[![Deep Learning](https://img.shields.io/badge/library-TensorFlow%202.6.0-red.svg)](https://www.tensorflow.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

An end-to-end, full-stack Flask web application integrated with a pre-trained Deep Learning binary classification model (Keras CNN) designed to analyze brain MRI scans and detect the presence of tumors.

---

## 🚀 Key Features

- **Deep Learning MRI Analysis**: Loads a pre-trained Keras convolutional neural network model (`project.h5`) to perform binary classification on brain MRI scans.
- **Interactive UI**: A simple, user-friendly web interface allowing users to upload brain MRI scans and view classification results instantly.
- **Dynamic Predictions**: Classifies images into two states:
  - **`It's a tumor`** (Class 0)
  - **`It's not a tumor`** (Class 1)
- **Robust File Validation**: Sanitizes and verifies user uploads, accepting only valid image formats (`.jpg`, `.jpeg`, `.png`, `.tif`, `.gif`).
- **Production Ready**: Fully pre-configured with a Heroku `Procfile` and WSGI execution schema utilizing `gunicorn` for robust web serving.

---

## 📂 Project Structure

```bash
├── static/
│   └── pics/          # Temp directory for user-uploaded MRI scans
├── templates/
│   ├── index.html     # Main landing page with the upload form
│   └── prediction.html# Display page for prediction results
├── app.py             # Main Flask backend (loads model, handles route, executes predictions)
├── project.h5         # Pre-trained Convolutional Neural Network model (Keras weights)
├── requirements.txt   # File containing all Python dependencies
├── Procfile           # Production WSGI server command (Gunicorn configuration)
└── README.md          # Project documentation
```

---

## 🛠️ Local Installation & Setup

Follow these instructions to set up the web application locally on your machine.

### 1. Prerequisites
Ensure you have **Python 3.8** or **Python 3.9** installed. 

### 2. Clone the Repository
```bash
git clone https://github.com/Puspha22/Braintumorfinal.git
cd Braintumorfinal
```

### 3. Create a Virtual Environment
It is highly recommended to isolate your project dependencies using a virtual environment:
```bash
# On Windows
python -m venv .venv
.venv\Scripts\activate

# On macOS/Linux
python3 -m venv .venv
source .venv/bin/activate
```

### 4. Install Dependencies
Install the required libraries listed in `requirements.txt`:
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Launch the Application
Run the Flask server locally:
```bash
python app.py
```
By default, the server will start at **`http://127.0.0.1:5000`** in your browser.

---

## 📦 Production Deployment

The project is pre-configured for web hosting. The included `Procfile` instructs standard application containers (like Heroku or custom Docker setups) to launch the app using `gunicorn` as the web gateway:

```bash
gunicorn app:app
```

---

## 📊 Model Information

The classifier model is saved in standard Keras format (`project.h5`). It takes a processed brain MRI scan as input, performs forward-pass convolution layers, and outputs a binary classification value representing either `tumor` or `healthy` brain tissues.

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
