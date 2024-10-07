PDF Chatbot using Google Gemini and FAISS
This project is a Streamlit application that allows users to upload PDF files and ask questions based on the content of the PDFs. It uses Google Gemini (Generative AI) and FAISS (Facebook AI Similarity Search) to extract information from PDF files and provide accurate responses to user questions.

Features
PDF Upload: Users can upload multiple PDF files.
Text Extraction: Extracts text from the uploaded PDF files.
Text Chunking: Splits the extracted text into manageable chunks for processing.
Vector Store Creation: Uses Google Generative AI Embeddings and FAISS to create a vector store of the text chunks.
Conversational Chain: Uses Google Gemini (Generative AI) to answer user queries based on the content of the PDF.
Interactive Interface: Provides a user-friendly interface using Streamlit.
Technologies Used
Streamlit: For building the web app interface.
PyPDF2: To extract text from PDF files.
Langchain: For text chunking, managing embeddings, and building the question-answering chain.
Google Generative AI: To generate embeddings and handle conversations using Gemini models.
FAISS: For similarity search over the text embeddings.
dotenv: To load environment variables for the Google API key.
Setup Instructions
Prerequisites
Make sure you have the following installed:

Python 3.8 or higher
Google API key (for Google Generative AI)
FAISS library
Installation
Clone the repository:

bash
Copy code
git clone <repository-url>
cd <repository-name>
Create a virtual environment:

bash
Copy code
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Set up Google API Key:

Create a .env file in the root directory of the project.

Add your Google API Key to the .env file:

plaintext
Copy code
GOOGLE_API_KEY=your-google-api-key
Run the application:

bash
Copy code
streamlit run app.py
Usage
Open the Streamlit application in your browser (usually at http://localhost:8501).
Upload one or more PDF files via the sidebar.
Once the files are uploaded, click the Submit & Process button to extract and process the text.
Enter your question in the text input field and get responses based on the content of the PDF.
Folder Structure
plaintext
Copy code
|-- app.py               # Main Python script with Streamlit app code
|-- README.md            # This README file
|-- requirements.txt     # Python dependencies
|-- .env                 # Google API Key (not included in the repo, created manually)
|-- faiss_index          # Saved FAISS index after text processing (created automatically)
Dependencies
streamlit
PyPDF2
langchain
langchain-google-genai
google-generativeai
faiss
python-dotenv
How It Works
PDF Upload & Processing:

The user uploads PDF files.
The application extracts text from all pages using PyPDF2 and splits the text into chunks using RecursiveCharacterTextSplitter from Langchain.
Vector Store Creation:

The chunks of text are converted into embeddings using Google Generative AI embeddings.
A FAISS index is created for similarity search using the generated embeddings.
Question Answering:

When the user enters a question, the app retrieves the most relevant chunks of text from the FAISS index.
The question and relevant text are passed to the Google Gemini model for answering.
The model responds, and the answer is displayed in the application.
Future Improvements
Add support for more file formats like DOCX.
Implement caching mechanisms for large PDF files.
Add more options for configuring the FAISS index parameters.
