# Document Retrieval: Leveraging Sparse and Dense Representations

## Overview
SPARC (Sparse and Dense Representations for Answering Questions) is a document retrieval system that combines the strengths of both sparse and dense representations to effectively rank documents based on their relevance to a given query. This approach enhances the ability to retrieve relevant documents in response to user queries by leveraging the rich contextual embeddings from BERT and the informative attention scores.

For more in-depth understanding, refer to the original paper: [SPARC: Sparse and Dense Representations for Answering Questions](https://arxiv.org/pdf/1911.02896).

## Features
- **Dense Representations**: The system utilizes BERT embeddings to capture the semantic meaning of both the queries and the documents. This allows for a nuanced understanding of the context, improving the retrieval of semantically relevant documents.

- **Sparse Representations**: By employing TF-IDF to generate sparse embeddings, SPARC highlights important terms and phrases that contribute to document relevance. This helps in identifying features essential for ranking documents.

- **Hybrid Scoring Mechanism**: The implementation employs a hybrid scoring strategy that combines the dense and sparse similarity scores. This weighted approach allows for a more robust ranking of documents, ensuring that both semantic similarity and key feature relevance are considered.

## Implementation Details

### Model Initialization
The implementation begins with the initialization of the BERT tokenizer and model. The tokenizer is responsible for converting the input text into a format suitable for BERT, including tokenization and encoding. The model is then used to generate the embeddings and attention scores necessary for both dense and sparse representations.

### Representation Generation
- **Dense Representations**: The BERT model processes the input query and documents, producing embeddings that encapsulate the semantic context of the text. The [CLS] token representation is extracted from the output as the final dense embedding for each input.

- **Sparse Representations**: TF-IDF is utilized to generate sparse embeddings that represent the importance of each term in the documents relative to the query. This representation highlights key terms that are critical for document relevance.

### Similarity Computation
To compute the similarity between the query and documents, the dense embeddings and sparse representations are compared using cosine similarity. The scores from both representations are combined using a weighted approach, allowing the system to rank documents effectively based on their relevance.

### Document Ranking and Answer Extraction
The final stage involves ranking the documents based on their combined similarity scores. The top-ranked document can then be used for further analysis or to extract specific answers using additional NLP techniques.

## Future Work
- **Leveraging Retrieved Documents**: Utilize the documents retrieved to feed into language models (LM) for answering questions, generating summaries, and other advanced NLP tasks.


## License
This project is licensed under the MIT License - see the LICENSE file for details.
