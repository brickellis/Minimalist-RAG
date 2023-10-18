# Minimalist-RAG
-------
Functionality
-------

The first notebook creates a ChromaDB vectorstore for a text file.
The second notebook queries the vectorstore and embeds the returned documents into an LLM prompt.

-------
How it Works
-------
Both notebooks use LangChain for all of their functionality.
The steps are as follows:
1. Convert the text into a list of LangChain Documents
2. Add those Documents to a ChromaDB vectorstore (and their embeddings) and save the store in the local directory.

1. Open the saved vectorstore.
2. Query the documents by searching for the documents with embeddings most similar to the query's, effectively comparing the documents by their semantic meanings.
3. Supply the queried documents into a propmt constructor which uses the documents as context for the supplied question.
4. Return the LLM's response to the question, based on the supplied context.

-------
How to Use
-------

Pip install the requirements.txt.
Change the file_name variable in both notebooks to your file's name, with .txt omitted. 
In the second notebook, replace the question in the third cell with your own.

Example query and output:
question = 'What was the name of Benjamin Franklin\'s newspaper?'
The name of Benjamin Franklin's newspaper was the Pennsylvania Gazette.

-------
Potential Future Updates/Welcome Pull Requests
-------
I'd be curious to see more effective methods of querying a database based on a question, maybe by supplying an LLM with the question along with some context for the search and having it return some recommended queries.

There is a lot which can be done using filters for querying the vector databases, and the information can be hard to find. A third notebook with some example filters using a non-persisted database would be helpful.

