## Demo

![Adobe Express - Video Project (1)](https://github.com/user-attachments/assets/94e980e1-d75d-4d10-896e-91c5ca4fcaf1)

**Analytics Dashboard:** The main interface provides detailed tabs for each lexical component.

## The Problem
Proficiency in English writing is crucial, but receiving high-quality feedback is challenging: Traditional Feedback: Methods like one-on-one meetings or written comments are often slow, subjective, and lack immediacy. Existing AWE Tools: Most Automated Writing Evaluation (AWE) systems (like Grammarly or e-rater) excel at finding grammar, spelling, and syntax errors. However, they largely ignore a key component of writing quality: lexical proficiency. This project addresses the gap by focusing specifically on the quality, variety, and sophistication of vocabulary.

## The Solution: ALICE

ALICE is an AWE system that analyzes a user's writing and provides specific, actionable feedback on three core components of Lexical Complexity (LC):

* **Lexical Density (LD):** The ratio of content words (nouns, verbs, adjectives) to function words (the, is, an, to). A higher density generally means more informational and less repetitive text.

* **Lexical Variety (LV):** The range of different words used. ALICE identifies over-used words and suggests alternatives to improve variety.

* **Lexical Sophistication (LS):** The use of more advanced, less frequent, and more precise vocabulary. ALICE suggests more sophisticated words to replace simpler ones.

The system evaluates the text against CEFR (Common European Framework of Reference) levels (A1-C1) to provide personalized and level-appropriate feedback.

## Key Features

* **Lexical Complexity Analysis:** Provides distinct scores and feedback for Lexical Density, Variety, and Sophistication.

* **CEFR-Based Evaluation:** Users can select their target CEFR level (A1-C1) for a tailored analysis.

* **Actionable Feedback:** Instead of just a score, ALICE provides specific suggestions, such as:

    * Identifying function/content word ratios (for LD).
    
    * Listing repeated words and offering synonyms (for LV).
    
    * Suggesting more advanced vocabulary replacements (for LS).

* **Simple Web Interface:** Built with Gradio for easy access and interaction.

## How It Works (Methodology)

The system is built on a 5-step NLP pipeline:

* **Corpus Construction:** The system's benchmarks were established by analyzing the EFCamDat dataset, a large corpus of 406,062 EFL writings categorized by CEFR level.

* **Text Preprocessing:** When a user submits text, it is processed using spaCy for:

    * Tokenization
    
    * Part-of-Speech (POS) Tagging
    
    * Lemmatization

* **Feature Extraction:** The system calculates 21 different lexical complexity features from the processed text.

* **Feature Selection & Analysis:** Through statistical analysis (ANOVA and Scheffé tests), the system identified the 3 most significant features for classifying writing quality:

    * Lexical Density
    
    * Corrected TTR (for LV)
    
    * Lexical Sophistication-I (for LS)

* **Feedback Generation:** The user's scores on these key features are compared to the CEFR benchmarks. The system then generates a detailed report with specific advice for improvement.

## Technology Stack

**Python**

  * spaCy: For core NLP preprocessing tasks (tokenization, POS-tagging, lemmatization).
  
  * scikit-learn: Used for the initial statistical analysis (ANOVA) to identify key features.
  
  * Gradio: To create and host the simple, interactive web interface.

**Feedback for LD:** Provides a breakdown of content words vs. function words.

**Feedback for LV:** Identifies overused words and suggests replacements.

**Feedback for LS:** Suggests more advanced vocabulary.
