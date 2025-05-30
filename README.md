# Implement a named entity recognition model to extract legal entities from accident reports.

This project extracts **legal entities and their values** (like aircraft name, airline, accident date, location, fatalities, etc.) from aviation accident report PDFs using OCR and Named Entity Recognition (NER).

---

## ✅ Features

- Converts scanned aviation PDF reports to text using **pdf2image** + **pytesseract**
  
- Extracts structured legal entities (like airline, date, location, aircraft, etc.)
  
- Uses SpaCy’s pretrained NER models
  
- Supports output analysis per document

---

## 🔧 Installation

Install dependencies:

```bash
apt-get install -y poppler-utils tesseract-ocr

pip install pytesseract pdf2image Pillow spacy

python -m spacy download en_core_web_sm  # or use 'en_core_web_trf' for better accuracy

🔍 Steps for Text Extraction and Named Entity Recognition (NER)
📝 1. Text Extraction (OCR)
File: ocr_extract.py

This script converts scanned aviation accident PDF reports into plain text using Tesseract OCR.

✅ What it does:
Converts each page of a PDF into an image

Uses OCR to extract text from each image

Saves the full text into output folder

🧠 2. Named Entity Recognition (NER)
File: ner_extract.py

This script uses SpaCy to extract meaningful legal entities (like organizations, dates, aircraft models, etc.) from the text.

✅ What it extracts:
ORG → Airline, NTSB

DATE → Accident date

GPE/LOC → City, airport

PRODUCT → Aircraft name

CARDINAL → Passenger numbers, fatalities

