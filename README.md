# Health-Info-Structuring-Verification
**Knowledge-Based Verification of Social Media Health Information**

## 📌 Overview
This project presents a **knowledge-based data pipeline** for structuring and verifying health-related information from social media videos.

With the rapid growth of online health content, misinformation has become a serious issue. This project focuses on **diabetes-related content** and proposes an automated framework that:

- Transforms unstructured video transcripts into structured knowledge  
- Aligns extracted information with authoritative medical sources  
- Evaluates the reliability of health information using Large Language Models (LLMs)

---

## 💡 Key Idea
The pipeline follows:

> **Unstructured Data → Structured Triplets → Knowledge Alignment → Semantic Verification**

Workflow:
1. Extract subtitles from social media videos (YouTube)  
2. Convert text into **(Subject–Predicate–Object) triplets**  
3. Align with **authoritative medical knowledge bases**  
4. Compute **semantic similarity & match rate**  
5. Perform **LLM-based verification**

---

## ⚙️ Methodology

### 1. Data Collection
- 330 diabetes-related YouTube videos  
- ASR-based transcription + manual cleaning  
- External knowledge sources:
  - Mayo Clinic  
  - WebMD  
  - PrimeKG (biomedical knowledge graph)

---

### 2. Triplet Extraction
- Rule-based extraction (baseline)  
- LLM-based extraction (main approach)

---

### 3. Prompt Engineering (Core Contribution)
Four strategies were evaluated:

- Basic Prompting  
- Chain-of-Thought (CoT)  
- Few-shot Learning  *(main performance driver)*  
- Self-Consistency  *(best stability)*  

---

### 4. Semantic Matching
- Triplets converted into embeddings  
- Cosine similarity for alignment  
- Threshold: **0.6**

---

### 5. Cross-Model Verification
Models compared:
- DeepSeek  
- OpenAI  
- Gemini  

---

## Results

### 🚀 Performance Highlights
- Rule-based method: **53.00% accuracy**  
- Best LLM setup: **76.98% match rate**  
- Few-shot learning improvement: **+3.15%**  
- Self-consistency variance reduced to **0.04**

---

### 🔍 Key Findings
- Few-shot learning significantly improves structured extraction  
- Extraction quality has more impact than verification model choice  
- Single-model pipelines show **self-validation bias**  
- Cross-model validation improves reliability  

---

## 🧩 Project Structure
```bash
health-info-pipeline/
│── data/                  # transcripts & knowledge base
│── src/
│   ├── extraction/        # triplet extraction
│   ├── verification/      # semantic matching
│   ├── prompts/           # prompt templates
│── results/               # experiment outputs
│── README.md
```
