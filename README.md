# 🌼 Marigold HR Assistant (Showcase)

**An offline, bilingual (English/Indonesian) HR chatbot built with RAG, LangChain, FAISS, and Ollama (Phi-3 Mini).**

Employees ask questions about a company handbook and get answers grounded in the handbook text. Everything runs locally, so no HR data leaves the machine.

> 🔒 This is a showcase repository: it contains the project overview, test results, and screenshots. The source code is kept private.
---

## 🚀 Key Features

- 🔒 **Fully local:** Ollama runs `phi3:mini` and `nomic-embed-text`; no cloud API.
- 🌐 **Bilingual:** one English and one Indonesian handbook, queried in either language.
- 📄 **RAG pipeline:** PDF → chunks (800 characters, 100 overlap) → embeddings → FAISS index → top-4 retrieval → answer.
- 🧪 **Evaluation suite:** 20 test questions with ground truth and page references.

## 🧰 Tech Stack

Python · Streamlit · LangChain · FAISS · Ollama (`phi3:mini`, `nomic-embed-text`)

## 🖼️ Screenshots
<img width="1202" height="670" alt="Marigold-HR-Assistant2" src="https://github.com/user-attachments/assets/fbaef7a0-44be-4e10-bfab-9ff68a4c083a" />


## 📊 Test Results

🎯 20 questions (11 English, 9 Indonesian, 3 "trap" questions whose answer is not in the handbook), graded strictly as Pass / Partial / Fail.

| Pass | Partial | Fail | Strict pass rate | Weighted* |
|------|---------|------|------------------|-----------|
| 14   | 4       | 2    | 70%              | 80%       |

*Partial counts as 0.5. English: 9/11 pass. Indonesian: 5/9 pass. Two of the 14 passes (pension match and grievance deadline) were found only after rewording the question to match the handbook wording.

## ⚠️ Known Limitations

- The small model sometimes invents details (for example, timing in the performance-review answer).
- Trap questions do not always get a clear "not found" reply.
- Retrieval is fragile when the question wording differs from the handbook.
- Indonesian answers are weaker than English ones.
- English questions are sometimes answered in Indonesian.

## 🔭 Next Steps

Detect the question language in code, test retrieval separately from generation, and keep the 20 questions as a regression suite.

## 👩‍💻 Author

Merry, S.Kom. 🌼

## 📬 Contact

[LinkedIn](https://www.linkedin.com/in/merry-s-kom-6b3ba3372/)

