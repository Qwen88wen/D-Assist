# D-Assist System Architecture

## Overview
D-Assist follows a Model-View-Controller (MVC) architecture with modular components.

---

## Architecture Layers

### 1. Presentation Layer (JavaFX)
- **Controllers**: Handle UI events and user interactions
- **FXML Views**: Define UI layouts
- **CSS Styling**: Application-wide styles

### 2. Service Layer
- **Business Logic**: Core application logic
- **Authentication**: User authentication and authorization
- **Services**: MedicineService, ChatService, DocumentService, etc.

### 3. RAG Pipeline Layer
- **Query Processing**: Normalize and validate queries
- **Vector Retrieval**: Semantic search using embeddings
- **Response Generation**: LLM-powered response generation
- **Citation Management**: Source citation formatting

### 4. Data Layer
- **Database Repositories**: CRUD operations
- **Vector Store**: Embedding storage and retrieval
- **Document Storage**: File system management

### 5. Utility Layer
- **Logging**: Application logging
- **Error Handling**: Global error management
- **Configuration**: Property loading

---

## Component Interactions

```
User Input → Controller → Service → RAG Pipeline → Vector Store
                    ↓                        ↓
                  Model ← Repository → Database
```

---

## Technology Stack

- **Frontend**: JavaFX 21
- **Backend**: Java 17
- **AI Framework**: LangChain4j
- **Build Tool**: Maven
- **Database**: TBD
- **Vector Store**: TBD

---

## RAG Pipeline Details

### Query Flow
1. User submits query
2. Query normalization and validation
3. Generate query embedding
4. Semantic search in vector store
5. Retrieve top-K relevant chunks
6. Format context
7. Generate AI response with LLM
8. Add citations
9. Return response to user

### Document Ingestion Flow
1. Admin uploads document
2. Extract text (PDF/DOCX/TXT)
3. Chunk text into segments
4. Generate embeddings
5. Store in vector database
6. Update document metadata

---

## Security Architecture

- **Authentication**: Role-based access control
- **Session Management**: Secure session handling
- **Audit Logging**: Complete action tracking
- **Data Validation**: Input validation at all layers

---

## Scalability Considerations

Placeholder for scalability design patterns and considerations.
