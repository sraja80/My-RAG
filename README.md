How It Works

Retrieval: The build_tfidf function creates a TF-IDF matrix from the documents. For a query, it computes a similar vector and finds the most similar documents via cosine similarity.
Output/Generation: The generate_response function takes the retrieved documents and produces a simple output. In practice, replace this with an LLM call (e.g., using OpenAI's API) like: "Use this context to answer: {context} Query: {query}".
Example Output (from running the code):
textQuery: What is the capital of France?
Retrieved context: The capital of France is Paris. France is in Europe.
Generated answer: Based on the context, the answer is derived from 'The capital of France is Paris. France is in Europe.'.
(Note: Retrieval may include semi-relevant docs due to shared terms like "France"; top_k=2 for demo Purpose)
