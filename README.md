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
