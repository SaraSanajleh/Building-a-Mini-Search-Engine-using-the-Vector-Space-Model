
# Mini Search Engine

## Project Overview

This project implements a **mini search engine** using the **Vector Space Model**. The search engine retrieves documents based on user queries by applying **TF-IDF weighting** and **Cosine Similarity**. The engine processes a collection of text documents, ranks them based on relevance to the user's query, and displays the most relevant results.

## Project Requirements

### 1. Preprocessing
For each text document, the following steps are performed:
- **Tokenization**: Splitting the text into individual words.
- **Lowercasing**: Converting all words to lowercase.
- **Stopword Removal**: Removing common words such as "the", "and", "is", etc.
- **Stemming**: Using **PorterStemmer** from the **NLTK** library to reduce words to their root form.

### 2. Indexing
An **inverted index** is created where each term is mapped to:
- The list of documents in which the term appears.
- The **Term Frequency (TF)** in each document.

### 3. Weighting
The **TF-IDF** (Term Frequency-Inverse Document Frequency) weight is computed for each term in each document:
- **TF** is calculated as the number of times a term appears in a document.
- **IDF** 

### 4. Query Processing
The engine accepts a free-text query from the user:
- The query is preprocessed in the same way as the documents (tokenization, lowercasing, stopword removal, and stemming).
- The query is represented as a **TF-IDF weighted vector**.

### 5. Ranking
- The **Cosine Similarity** is calculated between the query vector and the vector for each document.
- The documents are ranked by descending similarity score, with the most relevant documents appearing first.

### 6. Displaying Results
The top-k most relevant documents are displayed to the user, along with their **document IDs** and **similarity scores**.

## How to Run the Search Engine

1. Clone or download the project repository.
2. Install the necessary Python libraries:
    ```bash
    pip install nltk
    ```
3. Load the dataset. This project uses the **Cranfield 1400** dataset for testing. Ensure that the dataset is accessible for the engine.
4. Run the search engine by calling the `test_multiple_user_inputs()` function, which will prompt the user for input queries.

## Example Usage

To test the engine with multiple queries, run the following:

```python
test_multiple_user_inputs()
```

This will prompt the user to input N queries. For each query, the engine will display the top 10 documents based on **Cosine Similarity**.

## Test Cases

Here are examples of some test cases:

1. **Query**: "aerodynamics of wing"
   - The engine will return documents related to aerodynamic properties of wings with similarity scores.

2. **Query**: "high-speed flight"
   - Results will focus on documents discussing high-speed flight characteristics and performance.

3. **Query**: "slipstream effect"
   - Documents that discuss the effect of slipstreams on wing aerodynamics will be ranked higher.

Each query will result in a ranked list of documents, sorted by their similarity to the input query.


## Group Members

- **Sara Alsanajleh**: 163418
- **Ghada Abu Shaqra**: 164188


