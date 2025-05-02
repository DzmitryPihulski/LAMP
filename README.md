<p align="center">
	<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54"/>
    <img src="https://img.shields.io/badge/langchain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white"/>
  <img src="https://img.shields.io/badge/langgraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white"/>
	<img src="https://img.shields.io/badge/fastapi-109989?style=for-the-badge&logo=FASTAPI&logoColor=white"/>
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white"/>
</p>

# LangGraph Agent for MongoDB Pipelines (LAMP)

LangGraph is a robust tool that manages LLM agents by introducing a graph structure connecting different stages (nodes) of the pipeline.

This agent enhances MongoDB by enabling efficient data retrieval using natural language.

The core idea is that users, who are aware of the type of information stored in the database, can query it in natural language instead of writing SQL or NoSQL queries. The agent interprets the request and performs the search.

The agent generates **full MongoDB pipeline**, which **allows** multi-collection iteractions within given database.

## Results

The agent works perfect with queries in format `Show me smth in the appartment that has something.`

For example:

1. `Input:` <mark>Show me all apartments with 7 bedrooms.</mark> <br>
   `Output:`

```json
[
  {
    "listing_url": "https://www.airbnb.com/rooms/14921505",
    "name": "BEACH ESCAPE",
    "bedrooms": "7"
  },
  ...
  {
    "listing_url": "https://www.airbnb.com/rooms/20955863",
    "name": "Most Beautiful Villa on Bosphorus Istanbul...",
    "bedrooms": "7"
  },
]
```

2. `Input:` <mark>Shom me the summary of property Ribeira Charming Duplex.</mark> <br>
   `Output:`

```json
[
  {
    "name": "Ribeira Charming Duplex",
    "summary": "Fantastic duplex apartment with three bedrooms, located in the historic area of Porto, Ribeira (Cube) - UNESCO World Heritage Site. Centenary building fully rehabilitated, without losing their original character."
  }
]
```

3. `Input:` <mark>How many night minimum can I book at Private Room in Bushwick.</mark> <br>
   `Output:`

```json
[
  {
    "minimum_nights": "14"
  }
]
```


## API

Run with `docker compose up -d --build` and access http://127.0.0.1:1234/docs

![](data/image.png)

## Installation

```bash
# Clone the repository
git clone https://github.com/DzmitryPihulski/LangGraph-agent-on-MongoDB
cd LangGraph-agent-on-MongoDB

# Run docker network with
docker compose up -d --build
```
