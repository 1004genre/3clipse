
                              ┌────────────────────────────┐
                              │  NASA Publications Dataset │
                              │  (CSV, OSDR, Task Book)    │
                              └──────────────┬─────────────┘
                                             │
                          ┌──────────────────┴──────────────────┐
                          │   DATA INGESTION & PREPROCESSING    │
                          │  (pandas, requests, BeautifulSoup)  │
                          └──────────────────┬──────────────────┘
                                             │
                 ┌───────────────────────────┴─────────────────────────────┐
                 │                 NLP & AI PROCESSING LAYER               │
                 │-------------------------------------------------------- │
                 │ • Summarization (T5 / BART / GPT)                       │
                 │ • Entity Extraction (spaCy / scispaCy)                  │
                 │ • Embeddings for Semantic Search (sentence-transformers)│
                 │ • Knowledge Graph Construction (NetworkX / Neo4j)       │
                 └───────────────┬─────────────────────────────────────────┘
                                 │
               ┌────────────────┴────────────────┐
               │                                 │
     ┌─────────▼───────────┐         ┌───────────▼───────────┐
     │  EMBEDDINGS STORE   │         │  KNOWLEDGE GRAPH DB   │
     │  (FAISS / Pinecone) │         │  (NetworkX / Neo4j)   │
     └─────────┬───────────┘         └───────────┬───────────┘
               │                                 │
               └──────────────┬──────────────────┘
                              │
                  ┌───────────▼────────────────────┐
                  │     BACKEND API LAYER          │
                  │       (FastAPI)                │
                  │-------------------------       │
                  │ /search    → semantic search   │
                  │ /summary   → paper summaries   │
                  │ /graph     → graph data JSON   │
                  │ /trends    → topic analytics   │
                  └───────────┬────────────────────┘
                              │
                 ┌────────────▼────────────┐
                 │   FRONTEND DASHBOARD    │
                 │ (React / Streamlit UI)  │
                 │-------------------------│
                 │ Search Publications     │
                 │ View AI Summaries       │
                 │ Explore Knowledge Graph │
                 │ Visualize Topic Trends  │
                 │ Filter by Year          │
                 └────────────┬────────────┘
                              │
                  ┌───────────▼────────────┐
                  │        END USERS       │
                  │ Scientists, Managers,  │
                  │ Mission Architects     │
                  └────────────────────────┘
