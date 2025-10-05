# 3clipse
                      ┌───────────────────────────────┐
                      │   NASA Publications Dataset    │
                      │   (CSV, OSDR, NASA Task Book)  │
                      └──────────────┬────────────────┘
                                     │
                        [Data Ingestion & Preprocessing]
                                     │
                      ┌──────────────▼────────────────┐
                      │   Text Extraction Pipeline     │
                      │  (requests, BeautifulSoup)     │
                      └──────────────┬────────────────┘
                                     │
                         [NLP & AI Processing Layer]
                                     │
 ┌────────────────────────────────────────────────────────────────────┐
 │   Summarization: transformers (BART/T5/GPT)                        │
 │   Entity Extraction: spaCy / scispaCy                              │
 │   Embeddings: sentence-transformers (semantic search)              │
 │   Knowledge Graph: NetworkX / Neo4j                                │
 └────────────────────────────────────────────────────────────────────┘
                                     │
                    ┌────────────────┴─────────────────┐
                    │                                  │
           [Embeddings DB / FAISS]           [Knowledge Graph Store]
                    │                                  │
                    └──────────────┬───────────────────┘
                                   │
                            [Backend API Layer]
                                   │
               ┌───────────────────┴────────────────────┐
               │           FastAPI / Flask              │
               │   (serves endpoints for search, graph, │
               │    and summaries via JSON)             │
               └───────────────────┬────────────────────┘
                                   │
                          [Frontend Dashboard Layer]
                                   │
     ┌──────────────────────────────────────────────────────────────┐
     │ React / Streamlit Frontend                                   │
     │  - Search Bar (semantic + keyword)                           │
     │  - Dynamic Summary Panel                                     │
     │  - Knowledge Graph Visualization (Plotly/D3.js)              │
     │  - Topic Trends & Timeline Charts                            │
     │  - Filters (organism, mission, year, etc.)                   │
     └──────────────────────────────────────────────────────────────┘
