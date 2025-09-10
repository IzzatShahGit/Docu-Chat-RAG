# DocuChat RAG Platform

A production-ready multi-user RAG (Retrieval-Augmented Generation) chatbot that enables intelligent conversations with your documents. Built with FastAPI backend and Streamlit frontend, supporting PDF, DOCX, and HTML processing through automated chunking and OpenAI embeddings stored in ChromaDB.

## 🚀 Features

### Intelligent Document Processing
- **Multi-format Support**: Process PDF, DOCX, and HTML documents seamlessly
- **Automated Chunking**: Smart text segmentation for optimal retrieval
- **OpenAI Embeddings**: High-quality vector representations for accurate search
- **ChromaDB Storage**: Efficient vector database for scalable document storage

### Advanced RAG Capabilities
- **Conversational RAG Chains**: Context-aware conversation flow using LangChain
- **Query Contextualization**: Intelligent query understanding and refinement
- **Conversation History**: Maintains context across chat sessions
- **Source Citations**: Responses include references to source documents

### Multi-User Architecture
- **User Management**: SQLite database for user registration, authentication, and session management
- **Concurrent Sessions**: Support for multiple users simultaneously
- **Document Management**: Upload, index, and manage documents per user
- **User Data Persistence**: Secure storage of user profiles and preferences
- **Real-time Interactions**: Fast response times for enterprise knowledge management
- **Scalable Vector Search**: Optimized retrieval system for large document collections

## 🏗️ Architecture

### Tech Stack
- **Backend**: FastAPI - Modern Python web framework
- **Frontend**: Streamlit - Interactive web application
- **LLM**: OpenAI GPT models for conversational AI
- **Vector Database**: ChromaDB for embedding storage and retrieval
- **User Database**: SQLite for user data storage and management
- **RAG Framework**: LangChain for orchestrating RAG workflows
- **Document Processing**: Automated PDF/DOCX/HTML parsing and chunking

### API Endpoints
- **User Management**: Registration, authentication, and profile management
- **Document Upload/Indexing**: Process and store documents
- **Chat Interactions**: Conversational Q&A with documents
- **Management Endpoints**: User session and document management
- **Health Checks**: System status and monitoring

## ⚙️ Setup & Configuration

### Prerequisites
- Python 3.8+
- OpenAI API key
- LangChain API key (optional, for tracing)

### Installation

```bash
# Clone repository
git clone <repository-url>
cd docuchat-rag

# Install dependencies
pip install -r requirements.txt
```

### Environment Variables

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=""
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=""
LANGCHAIN_PROJECT="Project-Name"
```

### Project Structure
```
Docu_Chat_RAG/
├── api/
│   ├── __init__.py
│   ├── app.log
│   ├── chroma_utils.py
│   ├── db_utils.py
│   ├── langchain_utils.py
│   ├── main.py
│   ├── pydantic_models.py
│   └── requirements.txt
├── app/
│   ├── api_utils.py
│   ├── chat_interface.py
│   ├── sidebar.py
│   └── streamlit_app.py
├── docs/
│   ├── Company_GreenFields BioTech.docx
│   ├── Company_QuantumNext Systems.docx
│   ├── Company_TechWave Innovations.docx
│   ├── GreenGrow Innovations_Company History.docx
│   └── GreenGrow's EcoHarvest System_A Revolution...
└── .env
```

## 🎯 Running the Application

### 1. Start the Backend Server

```bash
# Run FastAPI backend
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

The API will be available at `http://localhost:8000`
- API Documentation: `http://localhost:8000/docs`
- Interactive API: `http://localhost:8000/redoc`

### 2. Start the Frontend

```bash
# Run Streamlit frontend (in a separate terminal)
streamlit run app.py
```

The web application will be available at `http://localhost:8501`

## 📋 Usage

1. **User Registration**: Create an account or login to access the platform
2. **Upload Documents**: Use the Streamlit interface to upload PDF, DOCX, or HTML files
3. **Document Processing**: Files are automatically chunked and indexed in ChromaDB
4. **Start Chatting**: Ask questions about your documents through the chat interface
5. **View Sources**: Responses include citations and references to source material
6. **Manage Sessions**: Each user maintains separate conversation history and document collections
7. **User Profile**: Access and manage your documents, chat history, and account settings

## 🔧 Development

### Key Features Implementation
- **Modular API Design**: Clean separation of concerns with dedicated endpoints
- **Async Processing**: Non-blocking document processing and chat responses
- **Error Handling**: Comprehensive error handling and logging
- **Scalable Architecture**: Designed for enterprise deployment and scaling

## 🚀 Deployment

### Production Considerations
- Use environment variables for all API keys and configuration
- Implement proper logging and monitoring
- Set up database persistence for ChromaDB and SQLite
- Configure CORS and security headers
- Use production ASGI server (Gunicorn + Uvicorn)
- Implement proper user authentication and authorization
- Set up database backups for user data

### Example Production Commands
```bash
# Backend with Gunicorn
gunicorn main:app -w 4 -k uvicorn.workers.UvicornWorker --bind 0.0.0.0:8000

# Frontend with custom configuration
streamlit run app.py --server.port 8501 --server.address 0.0.0.0
```

## 📊 Performance Features

- **User Data Management**: Efficient SQLite database for user profiles and session data
- **Optimized Retrieval**: Fast vector search with ChromaDB
- **Concurrent Processing**: Handle multiple users simultaneously
- **Memory Management**: Efficient document chunking and embedding storage
- **Session Persistence**: Maintain user state across application restarts
- **Real-time Responses**: Optimized for enterprise knowledge management workflows

## 📄 License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/IzzatShahGit/Docu-Chat-RAG/blob/main/LICENSE)

This project is licensed under the MIT License - see the [LICENSE](https://github.com/IzzatShahGit/Docu-Chat-RAG/blob/main/LICENSE) file for details.
