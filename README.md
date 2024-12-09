# GuideGPT: Context-Aware Chatbot for MRONJ Clinical Questions

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## Overview

**GuideGPT** is a context-aware chatbot leveraging Retrieval-Augmented Generation (RAG) to deliver evidence-based answers to clinical questions related to Medication-related Osteonecrosis of the Jaw (MRONJ). This system contrasts the efficacy of generic chatbots with context-aware counterparts informed by scientific literature.

## Table of Contents

- [Abstract](#abstract)
- [Features](#features)
- [Installation](#installation)
- [Using the Jupyter Notebook](#using-the-jupyter-notebook)
- [How It Works](#how-it-works)
- [Technical Implementation](#technical-implementation)
- [Performance](#performance)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

## Abstract

Large language models (LLMs) hold significant potential in medical applications. However, their integration into clinical settings is often hindered by concerns over data transparency and scientific accuracy. **GuideGPT** addresses these challenges by integrating a knowledge database comprising  scientific publications aligned with international MRONJ guidelines. This chatbot is designed to answer questions pertaining to MRONJ prevention, diagnosis, and treatment. In a comparative analysis involving 30 MRONJ-related queries, **GuideGPT** demonstrated markedly superior performance over generic LLMs in areas such as content quality, scientific explanation, and expert agreement.

## Features

- **Context-Aware Responses**: Utilizes a comprehensive knowledge base to provide accurate and relevant answers.
- **Retrieval-Augmented Generation (RAG)**: Enhances response quality by retrieving pertinent information from scientific literature.
- **Source Tracking**: Offers the possiblity of creating hyperlinks to source documents for verification and further reading.
- **Easy Setup**: User-friendly Jupyter Notebook for quick initialization and usage.
- **Performance Verified**: Outperforms generic models in expert evaluations focusing on MRONJ-specific queries.

## Installation

### Prerequisites

- Python 3.10 or higher
- [Jupyter Notebook](https://jupyter.org/install)
- OpenAI API Key

### Steps

1. **Clone the Repository**
    ```bash
    git clone https://github.com/maxrusse/GuideGPT.git
    cd GuideGPT
    ```

2. **Create a Virtual Environment (Optional but Recommended)**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. **Install Required Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

## Using the Jupyter Notebook

1. **Download the Notebook**
    - [Demo of GuideGPT.ipynb](GuideGPT.ipynb)

2. **Launch Jupyter Notebook**
    ```bash
    jupyter notebook
    ```

3. **Upload the Notebook**
    - Navigate to the directory containing `GuideGPT.ipynb` and open it.

4. **Set Your OpenAI API Key**
    - In the first code cell, set your API key:
        ```python
        import os
        os.environ["OPENAI_API_KEY"] = 'your-api-key-here'
        ```

5. **Specify the Publications Directory**
    - Ensure your MRONJ scientific publications are in the specified folder (default is `publications`).

6. **Execute the Cells**
    - Run each cell sequentially to initialize the vector store and launch the chatbot interface.

## How It Works

The system comprises several key components:

1. **Knowledge Database**
    - Constructes a database from scientific publications.

2. **Vector Store**
    - Utilizes Llama-Index to convert publications into searchable vectors.

3. **Retrieval-Augmented Generation (RAG)**
    - Retrieves relevant content based on semantic similarity to the query.

4. **Response Generation**
    - Employs GPT-4 with custom prompting templates to generate accurate answers.

5. **Source Tracking**
    - Provides filenames and pages of source information to create hyperlinks to source documents for answer verification.

## Technical Implementation

- **Embedding Model**
    - Uses `text-embedding-ada-002` for generating dense vector representations.

- **Semantic Similarity Search**
    - Implements cosine distance for retrieving the top 20 most relevant sentences per query.

- **Contextual Completeness**
    - Includes surrounding context (5 sentences before and after) to ensure comprehensive responses.

- **Source Metadata**
    - Provides detailed metadata, including file names and page numbers of source documents.

- **Language Model**
    - Utilizes GPT-4 (version `gpt-4-0613`) with a temperature setting of 0.4 for response generation.

## Performance

In evaluations conducted by 10 international MRONJ experts, **GuideGPT** significantly outperformed generic language models in the following areas:

- **Content Quality** (p=0.006)
- **Scientific Explanation** (p=0.032)
- **Expert Agreement** (p=0.008)

*Note: Access to the OpenAI API is required to use this implementation.*

For detailed insights, refer to the full publication: 
> "Evaluation of a context-aware chatbot using Retrieval-Augmented Generation for answering clinical questions on Medication-related osteonecrosis of the jaw"

## Contributing

This project is finalized for publication, so contributions are not accepted. 
However, if you'd like to collaborate or use this as inspiration for a new project, feel free to reach out. 
We’d love to hear your ideas!

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgements

- **OpenAI** for providing the GPT-4 model.
- **Llama-Index** and **LangChain** for their powerful libraries facilitating the implementation.
- The MRONJ experts who participated in the evaluation study.

## Contact

For any inquiries or feedback, please contact:
- **GitHub**: [maxrusse](https://github.com/maxrusse)
- **LinkedIn**: [LinkedIn Profile]([https://www.linkedin.com/in/yourprofile](https://www.linkedin.com/in/maximilian-russe-3a83a42a6))

