# **Cat vs Dog Image Classification API**

This project offers an **API for classifying images of cats and dogs** using a pretrained deep learning model.

---

## **Getting Started**

### *Prerequisites*

Ensure you have the following installed:
- Python 3.7 or later
- Required Python libraries (listed in `requirements.txt`)

### **Installation**

  ### **1. Clone the Repository**
  ```bash
  git clone https://github.com/AdityaKhandelwal2306/ImageClassification.git
  cd ImageClassification
  ```
  
  ### **2. Create and Activate a Virtual Environment**
  ```bash
  python -m venv venv
  source venv/bin/activate  # For macOS/Linux
  venv\Scripts\activate   # For Windows
  ```
  
  ### **3. Install Required Dependencies**
  ```bash
  pip install -r requirements.txt
  ```
  
  ### **4. Launch the API**
  ```bash
  uvicorn app.main:app --reload
  ```
  
  ### **5. Access the API**
  * Open your browser at: `http://<localhostOrIP>:<port>`  
  * API Endpoint: `POST /predict`  
  * Example Request: Upload an image file to `/predict` to get a prediction.
  
  ---

## **Project Structure**

```
project-root/
│
├── api/
│   ├── routes.py       # Defines API routes
│   ├── schemas.py      # Defines API response schemas
│
├── app/
│   ├── main.py         # FastAPI application entry point
│
├── core/
│   ├── config.py       # Configuration settings
│   ├── prediction.py   # Logic for image preprocessing and prediction
│   ├── training.py     # Script for training the model
│
├── data/               # Directory for datasets
│   ├── cat/
│   ├── dog/
│
├── models/
│   ├── cat_dog_model.h5 # Pretrained Keras model
│
├── uploads/            # Stores uploaded test images
│
├── requirements.txt    # Dependencies for the project
├── README.md           # Documentation
└── venv/               # Virtual environment
```

---

## **Model Details**

* **Framework:** TensorFlow/Keras  
* **Input Size:** 128x128  
* **Classes:** Cat, Dog  
* **Training Script:** `core/training.py`  

### **Run the Training Script**
```bash
python core/training.py
```

---

## **API Example**

### **Request Example (Using cURL)**
```bash
curl -X POST "http://127.0.0.1:8000/predict" \
-H "accept: application/json" \
-H "Content-Type: multipart/form-data" \
-F "file=@path_to_image.jpg"
```

### **Response Example**
```json
{
  "file": "cat_2.jpg",
  "result": {
    "prediction": "Cat",
    "confidence": 0.98
  }
}
```

---

## **Contributing**

* Fork the repository.  
* Create a new branch:  
  ```bash
  git checkout -b feature-branch
  ```
* Implement your changes and commit:  
  ```bash
  git commit -m "Your changes"
  ```
* Push the changes to your branch:  
  ```bash
  git push origin feature-branch
  ```
* Submit a pull request.

---

## **License**

This project is licensed under the **MIT License**.

---
