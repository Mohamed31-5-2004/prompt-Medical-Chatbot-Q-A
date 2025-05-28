# Medical-Chatbot-Using-NLP: Overview

# Setup and Execution Steps for Medical-Chatbot-Using-NLP

Follow these steps to set up and run the Medical Chatbot on your local machine.

---

## 1. Prerequisites

- **Python 3.7+**
- **pip** (Python package manager)
- **Git** (to clone the repository)
- **(Optional) GPU support** for faster NLP model processing

---

## 2. Clone the Repository

```bash
git clone https://github.com/Vaibhav0407/Medical-Chatbot-Using-NLP.git
cd Medical-Chatbot-Using-NLP
```

---

## 3. Install Required Python Packages

It is recommended to use a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate
```

Then install the dependencies:

```bash
pip install -r requirements.txt
```

If `requirements.txt` is not present, manually install the main dependencies:

```bash
pip install flask spacy transformers fuzzywuzzy scikit-learn
```

---

## 4. Download and Set Up spaCy Model

The project uses spaCy's English model for symptom extraction.

```bash
python -m spacy download en_core_web_sm
```

---

## 5. Prepare Data Files

- Ensure `Untitled-1.json` (or your diseases data JSON file) is present in the project directory.
- If needed, update the file path in the code to match your dataset location.

---

## 6. Run the Application

Start the Flask server:

```bash
python app.py
```
or, if the main file is named differently, replace with the appropriate filename.

---

## 7. Access the Chatbot

Once the server is running, open your web browser and navigate to:

```
http://127.0.0.1:5000/
```

You should see the chatbot interface.

---

## 8. Interact with the Chatbot

- Enter your medical queries or symptoms in the text field.
- The chatbot will process your input and reply with relevant medical information, possible conditions, and advice.

---

## 9. Stopping the Server

Press `Ctrl+C` in the terminal to stop the Flask server.

---

## 10. (Optional) Model Training

If you wish to retrain the NER or QA models:
- Prepare your dataset.
- Update and run the relevant scripts (`train_ner.py`, `train_qa.py`, etc.) as provided in the repository.

---

## Troubleshooting

- **ModuleNotFoundError:** Make sure all dependencies are installed and your virtual environment is activated.
- **Port Already in Use:** If port 5000 is busy, change the port in `app.py` (`app.run(port=YOUR_PORT)`).
- **Data File Not Found:** Check that all required data files (e.g., `Untitled-1.json`) are present and paths are correct.

---

## Notes

- This chatbot provides preliminary information and is not a substitute for professional medical advice.
- For deployment, consider using a production server (e.g., Gunicorn) and securing sensitive data.

Purpose
This project implements a chatbot designed to assist users with medical queries. It uses natural language processing (NLP) techniques to understand user input about symptoms, extract relevant medical information, and suggest possible diseases or conditions. It also provides explanations about diseases, symptoms, causes, treatments, and preventive measures.

Key Features
Symptom Extraction:
The chatbot can process free-form user input, identify symptoms mentioned in the text, and match them to known medical symptoms.

Disease Prediction:
By analyzing the extracted symptoms, the chatbot uses either trained models or a symptom database to present a list of possible diseases or conditions that match the user's input.

Medical Knowledge Base:
The chatbot contains information on:

Diseases
Symptoms
Causes
Treatments
Preventive measures
Conversational Interface:
Users interact with the bot in natural language, simulating a conversation with a virtual medical assistant.

NLP Techniques Used:

Text preprocessing (tokenization, stemming, etc.)
Named Entity Recognition (for symptom extraction)
Possibly intent recognition
Classification or matching algorithms for disease suggestion
Typical Workflow
User Input:
User types a medical question or describes symptoms in natural language.

NLP Pipeline:
The input is processed to extract meaningful information (e.g., symptoms).

Database/Model Query:
The bot consults its symptom-disease database or prediction model to find relevant information.

Response Generation:
The chatbot replies with possible diagnoses and explains details about the disease, symptoms, causes, etc.

Use Cases
Initial triage: Help users determine if they should see a doctor.
Medical education: Provide quick information about diseases.
Patient engagement: Answer questions about symptoms and treatments.
What This Repository Is (and Is Not)
Is: A proof-of-concept or educational implementation of an NLP-powered medical chatbot.
Is Not: A replacement for a real doctor or clinical decision support system. It is not intended for emergency or critical diagnostic use.
How to Explore the Repository
Check the README.md for setup instructions and features.
Review the code for modules handling NLP processing, symptom extraction, and response generation.
Look for data files (CSV/JSON) containing medical knowledge or symptom-disease mappings.
Explore sample conversations or demo scripts.
