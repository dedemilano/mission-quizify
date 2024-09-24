# Quiz Builder Application

## Overview

The **Quiz Builder** is an interactive application developed with **Streamlit** and **LangChain** that enables users to upload PDF documents, specify a quiz topic, and generate quizzes based on the content of those documents. This project incorporates several tasks, from document processing to quiz generation, leveraging **Google Vertex AI** for text embeddings and **ChromaDB** for efficient data retrieval.

## Features

- **Multiple PDF Uploads**: Users can upload multiple PDF files at once.
- **Content Extraction**: Utilizes the `DocumentProcessor` to extract content from PDFs by page.
- **Text Embedding**: Generates embeddings for queries and documents using `EmbeddingClient` connected to Google Cloud Vertex AI.
- **Chroma Collection Creation**: Creates an in-memory Chroma collection to index and search through the processed documents.
- **Dynamic Quiz Creation**: Users can specify a topic and select the number of questions for generating a quiz based on the document content.
- **Intuitive User Interface**: Built with Streamlit for a smooth and interactive user experience.
- **Feedback Mechanism**: Provides immediate feedback on user answers with explanations.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Python 3.8+**
- **Google Cloud Account** with Vertex AI enabled
- **Git** to clone the repository
- Other dependencies as listed in `requirements.txt`

## Installation

1. **Clone this repository**:

    ```bash
    git clone https://github.com/your-username/quiz-builder.git
    cd quiz-builder
    ```

2. **Install the required dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Set up Google Vertex AI credentials and configuration**:

    Ensure you have access to the **gemini-pro** model. Set your credentials:

    ```bash
    export GOOGLE_APPLICATION_CREDENTIALS=/path/to/your/service-account-file.json
    ```

4. **Update the embedding model configuration** in the code:

    ```python
    embed_config = {
        "model_name": "textembedding-gecko@003",
        "project": "your-google-cloud-project-id",
        "location": "us-central1"
    }
    ```

## Usage

1. **Run the Streamlit application**:

    ```bash
    streamlit run app.py
    ```

2. On the application interface:
   - Upload your PDF documents for ingestion.
   - Input the topic for the quiz in the **Topic for Generative Quiz** field.
   - Use the slider to select the number of quiz questions (up to 10).
   - Click **Submit** to generate the quiz.

3. View the generated quiz question with answer choices and an explanation.

## Code Structure

- **DocumentProcessor**: Handles the ingestion and embedding of PDF documents.
- **EmbeddingClient**: Manages the embedding service to transform documents into vector representations.
- **ChromaCollectionCreator**: Creates a vector database for efficient querying of embedded documents.
- **QuizGenerator**: Generates quiz questions based on a given topic and the embedded documents.
- **QuizManager**: Manages quiz state, including tracking current questions and navigating through them.

## Example Usage

Here's a quick example of how to generate a quiz:

```python
from quiz_builder import QuizGenerator

# Create a quiz generator
generator = QuizGenerator(topic="Quantum Computing", num_questions=5, vectorstore=chroma_vectorstore)

# Generate a quiz question
question = generator.generate()
