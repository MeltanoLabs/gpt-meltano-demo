# Meltano GTP Demo

This Meltano project demonstrates how to apply Meltano's ELT+ processes to LLM, GPT and Chat applications.

## What does this project do?

1. `tap-beautifulsoup`
   1. Extract text content from a website using the BeautifulSoup web scraping library.
1. `map-gpt-embeddings`
   1. Split text content into smaller documents using the LangChain library.
   1. Calculate "Embeddings" for each text segment. These are calculated by making a call to the OpenAI Endpoint.
1. `target-chromadb`
   1. Store the extracted and mapped data into ChromaDB vectorstore, backed by DuckDB and Parquet.
1. `gpt:chat`
   1. Prompt for a question from the user.
   2. Use LangChain to find the document segments in ChromaDB which most closely match the prompt.
   3. Use LangChain to create a modified prompt to send to ChatGPT, prefixing all of the data we found when querying our vectorstore.
   4. Send the modified prompt to the ChatGPT API endpoints, and render the response to the user.

## Glossary of terms and tools

### Embeddings

In low-tech terms, an array of ~1,500 floats. More specifically, a numeric representation of text data with very high dimensionality. Embeddings allow similar things being mathematically adjacent to others.

### LangChain

[TODO]

### OpenAI

[TODO]
