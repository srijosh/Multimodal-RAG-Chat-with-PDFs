# Multimodal RAG Chat with PDFs

This repository contains a project for building a Multimodal Retrieval-Augmented Generation (RAG) Chat application capable of extracting and analyzing content from PDFs, including text, images, and tables. The project leverages advanced AI tools and libraries such as LangChain, Groq, Unstructured and Hugging Face’s Transformers to provide multimodal data retrieval and processing.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Model](#model)

## Introduction

The Multimodal RAG Chat application is designed to extract meaningful insights from PDFs containing diverse content types such as text, images, and tables. The system leverages state-of-the-art AI models and vector-based retrieval systems to enable accurate document querying. The chat provides responses based on the extracted text from the PDFs, utilizing embeddings for efficient content retrieval. However, the chatbot currently supports only text-based queries, with responses generated from the PDF content and summaries.

## Features

- Multimodal Content Processing: Extracts and processes text, images, and tables from PDFs using Unstructured's partition_pdf tool..
- RAG Architecture: Combines retrieval and generation to provide accurate, contextual responses based on document content.
- Text and Table Summarization: Uses LangChain-Groq for generating summaries of text and tables within the PDF.
- Image Summarization: Uses Hugging Face's BlipForConditionalGeneration for generating summaries for images in the PDF.
- Text-Only Chat: The chatbot can answer text-based questions using Hugging Face's transformers pipeline.
- Chroma Vector Search: Leverages ChromaDB for storing and retrieving vectorized summaries of PDFs.
- Efficient Contextual Querying: Retrieves relevant PDF content via ChromaDB and combines it with generative models for chatbot responses.

## Installation

1. Clone the repository to your local machine:

```
   git clone https://github.com/srijosh/Multimodal-RAG-Chat-with-PDFs.git
```

2. Navigate to the project directory:

```
   cd Multimodal-RAG-Chat-with-PDFs
```

3. Set up environment variables by creating a .env file (Use .env.sample as a reference for setting up your .env file.)

## Usage

1. Open the langchain_multimodal.ipynb notebook in Jupyter and execute the cells to:

- Preprocess PDFs: Use unstructured.partition.pdf to extract text, tables, and images from the PDFs.
- Set up the RAG System: Initialize embeddings and vector search with ChromaDB for document retrieval.
- Query PDFs: Ask text-based questions related to the PDF content, and the chatbot will provide responses based on the retrieved text and summaries.

2. For Users with OpenAI API Key:
   If you have access to the OpenAI API, you can enable OpenAI-based processing by uncommenting the corresponding code in the notebook (the section is commented for users without an API key).

## Model

- BlipForConditionalGeneration: Used to generate summaries for images within the PDFs.
- LangChain-Groq: Used for generating summaries of text and tables in the PDFs.
- transformers pipeline: Utilized for text-based question answering, enabling the chatbot to respond to text-related queries.
- Hugging Face Embeddings (all-MiniLM-L6-v2): Used for generating dense vector representations of text, enabling efficient document retrieval from ChromaDB.
