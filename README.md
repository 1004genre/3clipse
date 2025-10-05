
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

nasa_bioscience_dashboard/
│
├── data/
│   ├── raw/
│   │   └── publications.csv            # Original NASA publication list
│   ├── processed/
│   │   ├── publications_clean.csv      # Cleaned and extracted data
│   │   └── embeddings.pkl              # Saved embeddings for search
│   └── summaries/
│       └── summaries.csv               # AI-generated summaries
│
├── backend/
│   ├── main.py                         # FastAPI entry point
│   ├── routes/
│   │   ├── search.py                   # Search endpoint (semantic + keyword)
│   │   ├── summaries.py                # Return paper summaries
│   │   ├── graph.py                    # Serve knowledge graph data
│   │   └── health.py                   # Simple health check
│   ├── utils/
│   │   ├── text_extraction.py          # Scraping & cleaning
│   │   ├── summarization.py            # AI model for text summarization
│   │   ├── entity_extraction.py        # spaCy / scispaCy pipeline
│   │   ├── embeddings.py               # Sentence transformer encoding
│   │   └── knowledge_graph.py          # Build graph (NetworkX/Neo4j)
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── SearchBar.jsx
│   │   │   ├── SummaryPanel.jsx
│   │   │   ├── GraphView.jsx
│   │   │   ├── TrendChart.jsx
│   │   │   └── Filters.jsx
│   │   ├── pages/
│   │   │   └── Dashboard.jsx
│   │   ├── App.jsx
│   │   └── index.js
│   ├── package.json
│   └── tailwind.config.js
│
├── models/
│   ├── summarizer/                     # fine-tuned summarization model (optional)
│   └── embeddings/                     # sentence-transformer model cache
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_summarization_testing.ipynb
│   ├── 03_entity_graph.ipynb
│   ├── 04_embedding_search.ipynb
│   └── 05_frontend_integration.ipynb
│
├── tests/
│   ├── test_summarization.py
│   ├── test_api_routes.py
│   └── test_graph_generation.py
│
├── .env                                # API keys / configs
├── README.md                           # documentation + usage guide
└── setup.sh                            # script to install and run project
