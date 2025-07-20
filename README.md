# Human-in-a-loop-Feedback-based-learning---Math-Routing-Agent
# 🧮 Math Routing Agent – Agentic RAG with Feedback

This project builds an AI-powered Math Assistant that behaves like a professor: it understands your math question, checks if it already knows the answer from a knowledge base (VectorDB), and if not, looks it up online using structured web search (via MCP). It gives step-by-step answers and even learns from human feedback. Built using FastAPI (backend) and React (frontend).

---

## 🛠️ What's Inside
- FastAPI backend with guardrails to ensure math-only input/output.
- Vector search using Qdrant + OpenAI embeddings.
- Web fallback using MCP (Model Context Protocol).
- Feedback system to learn from user corrections (DSPy ready).
- Optional benchmarking using JEE Bench questions.

---

## 🚀 Getting Started
1. **Install dependencies:**
   ```
   pip install fastapi uvicorn openai qdrant-client mcp-sdk
   ```
2. **Start Qdrant locally:**
   ```
   docker run -p 6333:6333 qdrant/qdrant
   ```
3. **Run the server:**
   ```
   uvicorn main:app --reload
   ```

---

## 📡 API Endpoints
- `POST /solve` – Submit a math question.
- `POST /feedback` – Log feedback on an answer.

---

## 📚 Example Questions
- **From KB**:  
  `Solve ∫x·eˣdx`, `Find derivative of sin(x²)`
  
- **From Web (MCP)**:  
  `Laplace transform of t²·e^{-3t}`, `∇²φ = 0 in spherical coordinates`

---

## 👨‍🏫 Human-in-the-Loop
If the system is unsure or makes a mistake, a human reviewer can correct it. The correction is logged and used to improve future answers—like teaching the AI over time.

---

## 📊 Benchmark (Bonus)
Use JEE Bench to test how well the system answers real exam questions. Compare accuracy with and without feedback.

---

## 📁 Folder Overview
```
math-agent/
├── backend/
│   ├── main.py         # FastAPI app
│   ├── guardrails.py   # Input/output checks
│   ├── retrieval.py    # VectorDB search logic
│   ├── web_search.py   # MCP search integration
│   ├── vector_db.py    # Embedding + Qdrant
│   └── feedback.py     # Feedback logger
```

---

## 👏 Contribute
Fork the repo, add features, and submit a pull request. Let’s make math tutoring better with AI!

---

## 📄 License
MIT License – free to use, improve, and share.
