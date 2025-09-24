This uses a basic TF-IDF vectorizer for retrieval (implemented from scratch using NumPy, as we don't have scikit-learn). The "generation" part is mocked by concatenating the retrieved context into a simple response string—for a real-world system, you'd integrate an LLM (e.g., via API) to generate more natural answers based on the retrieved context.
This system includes:

A small knowledge base of documents.
Retrieval: Computes TF-IDF vectors for documents and queries, then uses cosine similarity to find top-k relevant documents.
Output: A mock generation that incorporates the retrieved context.


How It Works

Retrieval: The build_tfidf function creates a TF-IDF matrix from the documents. For a query, it computes a similar vector and finds the most similar documents via cosine similarity.
Output/Generation: The generate_response function takes the retrieved documents and produces a simple output. In practice, replace this with an LLM call (e.g., using OpenAI's API) like: "Use this context to answer: {context} Query: {query}".
Example Output (from running the code):
textQuery: What is the capital of France?
Retrieved context: The capital of France is Paris. France is in Europe.
Generated answer: Based on the context, the answer is derived from 'The capital of France is Paris. France is in Europe.'.
(Note: Retrieval may include semi-relevant docs due to shared terms like "France"; top_k=2 for demo Purpose)
