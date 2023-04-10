---
title: "Python untuk Natural Language Processing"
description: "Beberapa library python yang berkaitan dengan Natural Language Processing disertai teori dan contoh penggunaannya."
pubDate: "Apr 08 2023"
# heroImage: "/placeholder-hero.jpg"
# draft: true
---

## Python Basic

Beberapa fitur python yang digunakan antara lain:
- File Writing / Reading

  contoh:
  ```python
    # contoh writing file
    with open('file.txt', 'w') as f:
        f.write('Hello World')
  
    # contoh reading file
    with open('file.txt', 'r') as f:
        print(f.read())
    ```

- PDF Writing / Reading

  contoh:
  ```python
    # contoh writing pdf
    from fpdf import FPDF
    pdf = FPDF()
    pdf.add_page()
    pdf.set_font("Arial", size=12)
    pdf.cell(200, 10, txt="Hello World", ln=1, align="C")
    pdf.output("file.pdf")
  
    # contoh reading pdf
    import PyPDF2
    pdfFileObj = open('file.pdf', 'rb')
    pdfReader = PyPDF2.PdfFileReader(pdfFileObj)
    print(pdfReader.numPages)
    pageObj = pdfReader.getPage(0)
    print(pageObj.extractText())
    pdfFileObj.close()
  ```

- Regular Expression

  contoh:
  ```python
    import re
  
    # contoh search
    text = 'Hello World'
    pattern = 'Hello'
    print(re.search(pattern, text))
  
    # contoh match, start, end
    text = 'Hello World'
    pattern = 'Hello'
    print(re.match(pattern, text))
    print(re.match(pattern, text).start())
    print(re.match(pattern, text).end())
  ```

## Libraries

Ada beberapa libraries python yang berkaitan dengan Natural Language Processing. Beberapa diantaranya adalah:
- NLTK
- Spacy
- SciKit Learn

### NLTK

NTLK adalah singkatan dari Natural Language Toolkit. NLTK merupakan library python yang digunakan untuk melakukan Natural Language Processing. NLTK memiliki beberapa fitur antara lain:
- Tokenization
- Stemming
- Lemmatization
- Stopwords
- Part of Speech Tagging

### Spacy

Spacy adalah library python yang digunakan untuk melakukan Natural Language Processing. Spacy memiliki beberapa fitur antara lain:
- Tokenization
- Stemming
- Lemmatization
- Stopwords

Spacy sering digunakan untuk Lemmatization karena lebih akurat dibandingkan dengan NLTK.

### SciKit Learn

SciKit Learn adalah library python yang digunakan untuk melakukan Natural Language Processing. Scikit Learn berisi algoritma-algoritma machine learning yang dapat digunakan untuk Natural Language Processing. 
SciKit Learn memiliki beberapa fitur antara lain:
- TF-IDF
- Count Vectorizer
- Train Test Split Dataset
- Confusion Matrix
- Classification Report

## Dasar-Dasar NLP

### Tokenization

### Stemming

### Lemmatization

### Stopwords

## Referensi
[NLP - Natural Language Processing with Python](https://www.udemy.com/course/nlp-natural-language-processing-with-python/)