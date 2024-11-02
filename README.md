# GuideGPT: Context-Aware Chatbot for MRONJ Clinical Questions

This project implements a context-aware chatbot using Retrieval-Augmented Generation (RAG) to provide evidence-based answers for questions related to Medication-related Osteonecrosis of the Jaw (MRONJ). The system compares the performance of generic chatbots versus context-aware chatbots informed by scientific literature.

## Abstract

Large language models show promise in medical applications, but their use in clinical settings is limited by data transparency and scientific accuracy concerns. This project evaluates GuideGPT, a context-aware chatbot integrated with a knowledge database of 449 scientific publications, designed to answer questions about MRONJ prevention, diagnosis, and treatment. When compared to a generic LLM across 30 MRONJ-related questions, GuideGPT showed significantly better performance in content quality, scientific explanation, and expert agreement.

## Using the Jupyter Notebook

1. Download the notebook file `Demo of GuideGPT.ipynb`
2. Upload the notebook to your preferred Jupyter environment
3. Set your OpenAI API key
4. Specify the folder path containing the MRONJ scientific publications
5. Execute the cells to initialize the vector store and launch the interface

## How It Works

The system utilizes several components to generate evidence-based responses:

* **Knowledge Database**: Created from 449 scientific publications referenced in 6 international MRONJ guidelines
* **Vector Store**: Uses Llama-Index to convert publications into searchable vectors
* **RAG Implementation**: Retrieves relevant content based on semantic similarity
* **Response Generation**: Uses GPT-4 with custom prompting templates
* **Source Tracking**: Provides hyperlinks to source documents for verification

## Setup Instructions

1. Set up your OpenAI API key:
```python
os.environ["OPENAI_API_KEY"] = 'your-api-key-here'
```

2. Specify the directory containing your scientific publications:
```python
FOLDER_PATH = "publications"
```

3. Install required dependencies:
```bash
pip install llama-index openai pandas numpy
```

4. Run the initialization script to create the vector store

## Technical Implementation

- Uses text-embedding-ada-002 model for generating dense vector representations
- Implements semantic similarity search using cosine distance
- Retrieves top 20 most relevant sentences per query
- Includes surrounding context (5 sentences before/after) for completeness
- Provides source metadata including file name and page number
- Uses GPT-4 (version gpt-4-0613) with temperature 0.4

## Performance

In evaluation by 10 international MRONJ experts, GuideGPT significantly outperformed the generic model in:
- Content quality (p=0.006)
- Scientific explanation (p=0.032)
- Expert agreement (p=0.008)


Note: OpenAI API access is required for using this implementation.

For more information, see the full publication: "Evaluation of a context-aware chatbot using Retrieval-Augmented Generation for answering clinical questions on Medication-related osteonecrosis of the jaw"
