# SmartQuizGen: AI-Powered Question Generator

SmartQuizGen is a modular and extensible project that automates the creation of multiple-choice questions from unstructured text. Built with the power of T5 Transformers and classical NLP techniques, the system extracts meaningful information from text, converts it into structured quiz questions, and enriches them with contextually relevant distractors.

## 📌 Overview

This project aims to simplify the process of quiz generation by breaking down the complex task into smaller, manageable steps:

• Extract potential answer candidates (keywords or phrases) from the input text  
• Mask the identified answers to build cloze-style (fill-in-the-blank) templates  
• Transform the masked sentence into a natural question  
• Generate plausible but incorrect options (distractors) using semantic similarity  

The system is ideal for educational platforms, exam preparation tools, and AI-driven tutoring systems.

---

## ✨ Key Features

• Extracts key answer-worthy entities using NLP tagging  
• Creates fill-in-the-blank questions and naturalizes them  
• Leverages word embeddings for generating realistic distractors  
• Includes data exploration modules to understand question patterns  
• Lightweight, modular, and easy to integrate with other ML pipelines

---

## ⚙️ Installation

It's recommended to use a virtual environment for cleaner dependency management.

### Create and activate a virtual environment:

```bash
python -m venv venv
```

**Activate it:**

• On Windows:

```bash
.\venv\Scripts\activate
```

• On macOS/Linux:

```bash
source venv/bin/activate
```

### Install dependencies:

```bash
pip install -r requirements.txt
```

### Optional but recommended:

```bash
pip install jupyterlab
ipython kernel install --user --name=.venv
```

---

## 🚀 How It Works

### 1. Data Exploration

Begin with understanding question structure using datasets such as SQuAD. The `Data Exploration` notebook provides insights into common answer types and their linguistic features.

### 2. Answer Identification

The system identifies potential answers from input text using a classification model. Features used include:

• Part-of-speech tags  
• Named entity recognition  
• Word shape and position  
• Sentence-level heuristics  

A Gaussian Naive Bayes classifier filters the most likely answer candidates.

### 3. Question Formation

Once an answer is selected, the sentence is converted into a cloze-style question:

**Example**  
_Text:_ Oxygen is a chemical element with symbol O and atomic number 8.  
_Answer:_ Oxygen  
_Question:_ \_\_\_\_\_ is a chemical element with symbol O and atomic number 8.

Advanced users can expand this using a T5 model or a sequence-to-sequence network to make the sentence more question-like.

### 4. Distractor Generation

Using word embeddings and cosine similarity, the system finds semantically similar words to serve as distractors. Filters ensure that:

• Distractors match the part of speech  
• Distractors are not obvious or misleading  
• Basic semantic and syntactic checks are applied

---

## 🧪 Running the Demo

A unified Jupyter Notebook (`Demo.ipynb`) is provided to showcase the complete pipeline. Simply input your paragraph and let the system generate a multiple-choice question.

```bash
jupyter lab
```

Then open the notebook and run the cells sequentially.

---

## 📈 Future Enhancements

• Incorporate a more powerful classification model with contextual embeddings  
• Add fine-tuned transformers for improved question naturalization  
• Integrate grammar correction for cleaner output  
• Expand to support multiple languages and domain-specific content  

---

## 📚 Use Cases

• Educators automating test content  
• Developers building intelligent quiz modules  
• EdTech platforms enabling interactive learning  
• Students creating self-assessment tools  

---

## 📬 Contribution

Feel free to contribute! Whether it's improving the model, expanding functionality, or cleaning up code, your help is welcome.

---

## 📜 License

This project is released under the MIT License. Please review the LICENSE file for details.
