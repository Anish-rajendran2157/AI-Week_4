# AI_RAG_IMPLEMENTATION

FastAPI RAG service plus the Week 4 retrieval-debugging evaluation.

## Week 4 evaluation

```bash
pip install -r requirements.txt
python -m scripts.ingest_corpus   # chunks data/corpus -> data/chunks.json (+ Pinecone if PINECONE_API_KEY set)
python -m scripts.run_eval        # dense vs hybrid, writes eval_output/ (answers generated if GROQ_API_KEY set)
```

Results and analysis: [results.md](results.md).

Config (env vars, see `.env.example`):
- `RETRIEVAL_MODE` = `dense` | `hybrid` (default `hybrid`, BM25 + dense fused with RRF)
- `DENSE_BACKEND` = `pinecone` | `local` (defaults to `pinecone` when a key is set)
- `PINECONE_NAMESPACE`

Run the API: `uvicorn app.main:app --reload`
