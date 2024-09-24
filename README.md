# PDF Processing with Streamlit and Langchain

This project allows users to upload and process PDF files via a Streamlit web app, extracting and counting pages from uploaded documents using Langchain's `PyPDFLoader`. The app supports multiple PDF file uploads and safely handles temporary file storage to avoid conflicts.

## Features

- **Multiple PDF Uploads**: Users can upload multiple PDF files at once.
- **Page Extraction**: Extracts pages from uploaded PDF files using Langchain's `PyPDFLoader`.
- **Page Count**: Displays the total number of pages processed from all uploaded documents.
- **Temporary File Handling**: Uses unique identifiers to avoid filename conflicts during processing.
  
## Prerequisites

Before you begin, ensure you have the following installed:

- **Python 3.8+**
- **Streamlit** for the web interface
- **Langchain** for the PDF processing via `PyPDFLoader`

You can install the necessary dependencies with:

```bash
pip install streamlit langchain
```

# Embedding Client with Google Cloud Vertex AI

This project provides a Python class, `EmbeddingClient`, that interacts with Google Cloud's Vertex AI to retrieve text embeddings using Langchain's `VertexAIEmbeddings`. The class allows you to initialize an embedding client with specific configurations and retrieve embeddings for text queries or documents.

## Features

- **Text Query Embedding**: Embeds individual text queries using the Vertex AI Embeddings service.
- **Document Embedding**: Supports embedding multiple documents simultaneously.
- **Customizable Parameters**: Users can specify the model name, Google Cloud project ID, and location to configure the embedding client.

## Prerequisites

Before running the application, ensure that you have:

- **Google Cloud Account**: You need a Google Cloud project with Vertex AI enabled.
- **Langchain**: The library used to access Google Cloud's Vertex AI for embeddings.
  
To install the required Python libraries, use the following command:

```bash
pip install langchain-google-vertexai

