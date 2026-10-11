# Extracting-Information-from-Legal-Documents-using-RAG
This repository processes and analyzes legal agreements to build a Retrieval-Augmented Generation (RAG) system. It features data cleaning, exploratory data analysis, and TF-IDF similarity evaluation using LangChain and FAISS to enhance automated legal research.

**Business Value & Use Cases**

Implementing RAG in the legal sector provides significant enhancements for businesses, law firms, and regulatory bodies. Key business objectives include:   
Faster Legal Research: Reduces the time lawyers and compliance officers spend searching for relevant case laws, precedents, statutes, or contract clauses.   
Improved Contract Analysis: Automatically extracts key terms, obligations, and risks from lengthy contracts.   
Regulatory Compliance Monitoring: Helps businesses stay updated with legal and regulatory changes by retrieving relevant legal updates.   
Enhanced Decision-Making: Provides accurate and context-aware legal insights to assist in risk assessment and legal strategy.  

*Primary Use Cases:*
Legal Chatbots   
Contract Review Automation   
Tracking Regulatory Changes and Compliance Monitoring   
Case Law Analysis of past judgments   
Due Diligence & Risk Assessment  

**Dataset Description**

The dataset consists of legal documents and contracts collected from various sources, stored as text files (.txt) within a designated corpus directory. The corpus is categorized into four main subfolders:   
contractnli: Various non-disclosure and confidentiality agreements.   
cuad: Contracts featuring annotated legal clauses.   
maud: Various merger/acquisition contracts and agreements.   
privacy_qa: A question-answering dataset containing privacy policies.   
Additionally, the project utilizes evaluation files (contractnli.json, cuad.json, maud.json) located in a benchmark folder. These JSON files contain evaluation queries, relevant source snippets with span positions (begin and end), and ground-truth answers.


**Project Pipeline**

Data Loading: Documents are ingested using LangChain's DirectoryLoader and TextLoader, with custom sequential handling for various file encodings (e.g., UTF-8, Latin-1) to ensure robust ingestion while tracking metadata like file names and directory paths.   
Data Preprocessing: Raw text undergoes rigorous cleaning to remove noise and prepare for analysis. This includes stripping email addresses, telephone numbers, and special characters, converting text to lowercase, and removing standard English stop words using NLTK. Missing or corrupted files are skipped and logged.
Exploratory Data Analysis (EDA): The cleaned data is analyzed to uncover relationships and trends. Key analyses include:   
Calculating document length statistics (average, maximum, and minimum word counts).   
Analyzing word frequency using Python's Counter to identify the top 20 most and least common terms.   
Generating TF-IDF vectors using scikit-learn and computing a cosine similarity matrix to analyze document similarity and detect duplicate or highly similar contract clauses. 

**Technologies & Libraries**

Core NLP & Data Processing: pandas, scikit-learn (TF-IDF, Cosine Similarity), nltk, re.   
LLM & RAG Frameworks: langchain, langchain-community, langchain-chroma, langchain-openai, langchain-google-vertexai, langchain-text-splitters, llama-cpp-python, FAISS.   
Evaluation: ragas, rouge_score, datasets
