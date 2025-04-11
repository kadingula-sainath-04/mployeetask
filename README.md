# Experience Extraction from Job Descriptions

## Objective
To extract the **total experience required** from 200 job descriptions (JDs) using multiple NLP models and compare their performance.

---

## Dataset
- Source: Excel file with 200 job descriptions.
- Column: Contains raw job description text.

---

## Techniques Implemented
We applied the following **6 experience extraction techniques**:

1. **spaCy NER**
2. **spaCy Dependency Parsing**
3. **BERT QA** (`deepset/bert-base-cased-squad2`)
4. **RoBERTa QA**
5. **Zero-Shot QA**


> Note: Regex was strictly avoided as per assignment instructions.

---

## Output
An output Excel file was generated containing:
- Original Job Description
- Extracted experience values from each of the 6 models
- (Optional) Ground truth column if available

---

## Best Model Recommendation

### Selected Model: **BERT QA (`deepset/bert-base-cased-squad2`)**

### Why It Performed Best:
- Accurately identifies experience in both structured and free-text JDs.
- Robust across variations (e.g., "at least 3 years", "minimum of 5 years").
- High consistency across the dataset.

### Challenges Faced:
- Other models picked up unrelated numbers (like dates or salaries).
- Zero-shot models hallucinated results when experience wasn't explicitly mentioned.
- Flair (TARS) sometimes underperformed on longer or vague descriptions.

---

## Deliverables

### Code:
- Reads the Excel file with JDs
- Applies 6 models to each JD
- Outputs results to a new Excel file

### Output Excel Sheet:
- One row per JD
- One column per model's extracted experience

### Write-up:
- Best model selected
- Justification
- Challenges and observations

---

## Tools and Libraries Used
- Python (pandas, openpyxl)
- Hugging Face Transformers
- spaCy
- Flair

---

## Summary
This project demonstrates how a combination of traditional and transformer-based NLP models can be used for accurate information extraction from unstructured text, particularly for experience requirements in job descriptions. BERT QA proved to be the most effective model for this specific task.

