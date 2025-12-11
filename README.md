# SmartHire-NLP

# Overview
SmartHire NLP is an end-to-end automated resume screening and job-matching tool built with NLP. It processes PDF resumes to extract skills, education, and other key information, then semantically compares candidates to job descriptions to find the best fits. The system leverages advanced NLP techniques to streamline recruitment: it automatically parses resumes and ranks candidates by matching them to job postings. SmartHire NLP aims to help recruiters quickly identify the most qualified applicants by their content, not just keywords.

# Features

Skills & Education Extraction: Automatically parses PDF resumes to extract relevant details like technical skills, certifications, and education history. Resume Classification: Categorizes resumes by industry or job function to organize candidate pools.
Job Description Parsing: Analyzes job description text to identify required skills, experience levels, and keywords.
Candidate Ranking: Encodes resumes and job descriptions into semantic vectors using Sentence-Transformers, then scores them via cosine similarity. Candidates are ranked by how closely their resume embeddings match the job description embedding.

# Tech Stack

Python – Core programming language.
PyMuPDF – Extracts text from PDF resumes.
pandas – Data handling and preprocessing.
sentence-transformers (SBERT) – Pre-trained models for embedding text.
PyTorch (torch) – Backend for transformer models.
scikit-learn – Utility functions (e.g. cosine similarity).
seaborn & matplotlib – Visualization of data and results.

# Visualizations

SmartHire NLP includes visual analytics to help understand the candidate pool. It generates category distribution plots (bar charts, pie charts, etc.) showing how resumes are categorized (e.g., by skill or industry). These plots use seaborn and matplotlib to reveal insights like dominant skills or the spread of experience levels among applicants.

The system leverages pre-trained SentenceTransformer models to encode text. For example, it might use models like all-MiniLM-L6-v2 that map sentences to high-dimensional vectors. These embeddings capture semantic meaning so that, for instance, “ML model development” and “machine learning” have similar vector representations. By embedding both resumes and job descriptions this way, SmartHire NLP can compute their cosine similarity, enabling context-aware matching beyond keyword overlap.

# Project Structure

extract_resume.py – Extracts text and key fields (skills, education) from PDF resumes.
classify_resumes.py – Classifies/categorizes resumes into predefined labels.
parse_job.py – Processes job description text to extract requirements.
match_candidates.py – Generates embeddings for resumes and jobs, then ranks candidates by similarity.
visualize.py – Creates plots (using seaborn/matplotlib) to show data distributions.
requirements.txt – Lists Python package dependencies.
