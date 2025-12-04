# D-Assist

**AI-Powered Diabetes Medicine Knowledge Base for Healthcare Professionals**

[![Java](https://img.shields.io/badge/Java-17+-blue.svg)](https://www.oracle.com/java/)
[![JavaFX](https://img.shields.io/badge/JavaFX-21-orange.svg)](https://openjfx.io/)
[![LangChain4j](https://img.shields.io/badge/LangChain4j-Enabled-green.svg)](https://github.com/langchain4j/langchain4j)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Target Users](#target-users)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Usage Guide](#usage-guide)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

**D-Assist** is a JavaFX-based desktop application designed to serve as a comprehensive diabetes medicine knowledge base for pharmacy staff and healthcare professionals. The system leverages **Retrieval-Augmented Generation (RAG)** technology powered by **LangChain4j** to deliver accurate, citation-backed responses to diabetes medication queries.

The application combines traditional structured database search with cutting-edge AI chat capabilities, enabling users to quickly locate medication details, verify dosages, check contraindications, and access clinical guidelines in high-pressure healthcare environments.

---

## 👥 Target Users

### Primary Users
- **Pharmacy Staff** (Retail & Hospital Settings)
- **Pharmacy Assistants**

### Secondary Users
- **Pharmacy Students**
- **Medical Students**

### User Needs Addressed
- Instant access to comprehensive diabetes medication information
- Reliable reference for dosages, side effects, and drug interactions
- AI-assisted clinical decision support with source citations
- Quick retrieval of past queries and frequently accessed content
- Clinical calculation tools for insulin dosing

---

## ✨ Key Features

### 🔍 Knowledge Access & Search
- ⚡ **Structured Medicine Search** – Browse diabetes medications by name, category, or therapeutic class
- 🔎 **Semantic Search** – Natural language queries powered by vector similarity
- 📂 **Category Quick Prompts** – Pre-defined queries for common medication classes
- ❓ **FAQ Library** – Curated frequently asked questions with verified answers

### 🤖 AI-Powered Chat Assistant
- 🧠 **RAG-Based Chatbot** – Contextual responses grounded in curated medical documents
- 📄 **Source Citations** – Every AI response includes references to original documents
- ⚠️ **Confidence Handling** – Graceful responses for ambiguous or out-of-scope queries
- 💬 **Conversation History** – Full chat history retrieval and management
- 👍👎 **Response Feedback** – Upvote/downvote system for response quality tracking

### 📚 Knowledge Base Management (Admin)
- 📤 **Document Ingestion** – Upload and process PDF, DOCX, and TXT files
- 🧩 **Content Chunking & Embedding** – Automatic vectorization for semantic retrieval
- 📋 **FAQ Management** – Add, edit, and delete frequently asked questions
- 🗂️ **Knowledge Entry CRUD** – Full control over structured medication database
- 📊 **Feedback Review** – Monitor and address negative user feedback

### 🧮 Clinical Tools
- 💉 **Mealtime Insulin Dose Calculator**
  - Inputs: Current blood glucose, carbohydrates, target BG, ISF, ICR
  - Outputs: Carbohydrate dose, correction dose, total suggested dose

### 👤 User Management & Personalization
- 🔐 **Role-Based Authentication** – Separate access for staff and administrators
- ✏️ **User Profile Management** – Edit personal information and preferences
- 🔖 **Bookmarks** – Save important queries and responses for quick access
- 🔔 **Notification System** – Admin alerts and system updates

### 🔐 Security & Compliance
- 📝 **Audit Logs** – Complete tracking of user actions and system changes
- 🛡️ **Role-Based Access Control (RBAC)** – Granular permission management
- 🔑 **Secure Login/Logout** – Session management and authentication

---

## 🏗️ System Architecture

D-Assist follows a **Model-View-Controller (MVC)** architecture with modular components:

```
┌─────────────────────────────────────────────────────────────┐
│                        Presentation Layer                    │
│  (JavaFX Controllers + FXML Views)                          │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────┴────────────────────────────────────────┐
│                        Service Layer                         │
│  (Business Logic + Authentication + Calculations)           │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────┴────────────────────────────────────────┐
│                     RAG Pipeline Layer                       │
│  (LangChain4j + Query Processing + Response Generation)     │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────┴────────────────────────────────────────┐
│               Data & Ingestion Layer                         │
│  (Vector Store + Document Processing + Database Access)     │
└─────────────────────────────────────────────────────────────┘
```

### Core Components:
- **Controller Layer**: Handles UI events and user interactions
- **Service Layer**: Implements business logic and coordinates operations
- **RAG Pipeline**: Processes queries, retrieves context, generates responses
- **Ingestion Pipeline**: Processes documents and generates embeddings
- **Vector Store**: Stores and retrieves document embeddings
- **Data Layer**: Manages database operations and persistence
- **Utility Modules**: Logging, error handling, validation

---

## 🛠️ Technology Stack

| Component | Technology |
|-----------|-----------|
| **Language** | Java 17+ |
| **UI Framework** | JavaFX 21 |
| **Build Tool** | Maven |
| **AI Framework** | LangChain4j |
| **Database** | TBD (MySQL/PostgreSQL/SQLite) |
| **Vector Store** | TBD (Chroma/Pinecone/In-Memory) |
| **Testing** | JUnit 5 |
| **Logging** | SLF4J + Logback |
| **Document Processing** | Apache POI, PDFBox |

---

## 📁 Project Structure

```
D-Assist/
├── src/
│   ├── main/
│   │   ├── java/com/dassist/
│   │   │   ├── controller/       # UI controllers for all screens
│   │   │   ├── model/            # Entity models
│   │   │   ├── service/          # Business logic layer
│   │   │   ├── rag/              # RAG pipeline (LangChain4j)
│   │   │   ├── ingestion/        # Document processing pipeline
│   │   │   ├── vectorstore/      # Vector storage and retrieval
│   │   │   ├── data/             # Database repositories
│   │   │   ├── ui/               # UI utilities
│   │   │   └── util/             # Utility classes
│   │   └── resources/
│   │       ├── fxml/             # JavaFX layouts
│   │       ├── css/              # Stylesheets
│   │       └── images/           # Assets
│   └── test/                     # Unit and integration tests
├── config/                       # Configuration files
├── assets/                       # Datasets and documents
├── docs/                         # User guide and architecture docs
├── demo/                         # Screenshots and demo videos
└── pom.xml                       # Maven configuration
```

---

## 🚀 Setup Instructions

### Prerequisites
- Java Development Kit (JDK) 17 or higher
- Apache Maven 3.8+
- (Optional) IDE with JavaFX support (IntelliJ IDEA, Eclipse, NetBeans)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/Qwen88wen/D-Assist.git
   cd D-Assist
   ```

2. **Configure the application**
   ```bash
   # Edit configuration files in the config/ directory
   # Update database.properties, langchain.properties as needed
   ```

3. **Build the project**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn javafx:run
   ```

### First-Time Setup
- Default admin credentials will be provided in documentation
- Load sample dataset from `assets/dataset/diabetes_medicines.csv`
- Upload initial medical documents via Admin Upload screen

---

## 📖 Usage Guide

### For Pharmacy Staff

1. **Login** – Use your credentials to access the system
2. **Search Medicines** – Use the Search screen to find medications by name or category
3. **Ask AI Questions** – Navigate to Chat screen and type natural language queries
4. **View Citations** – Click citation links to view source documents
5. **Bookmark Queries** – Save frequently used queries for quick access
6. **Calculate Insulin Doses** – Use the Insulin Calculator for dose recommendations

### For Administrators

1. **Upload Documents** – Add medical PDFs, DOCX, or TXT files via Admin Upload
2. **Manage FAQs** – Create and edit frequently asked questions
3. **Review Feedback** – Monitor user feedback on AI responses
4. **Manage Users** – Add or remove user accounts
5. **View Audit Logs** – Track system usage and changes

📘 **Full user guide available in**: `docs/USER_GUIDE.md`

---

## 🧪 Testing

### Running Tests
```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=ServiceTests

# Generate test coverage report
mvn jacoco:report
```

### Test Structure
- **Controller Tests**: UI interaction and event handling
- **Service Tests**: Business logic validation
- **RAG Tests**: Query processing and response generation
- **Ingestion Tests**: Document processing pipeline
- **Util Tests**: Utility function validation

---

## 🤝 Contributing

We welcome contributions from the community! Please read our [Contributing Guidelines](CONTRIBUTING.md) before submitting pull requests.

### Development Workflow
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Standards
- Follow Java naming conventions
- Write JavaDoc comments for public methods
- Maintain test coverage above 80%
- Format code with standard Java formatter

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 📧 Contact

**Project Repository**: [https://github.com/Qwen88wen/D-Assist](https://github.com/Qwen88wen/D-Assist)

---

## 🙏 Acknowledgments

- LangChain4j community for AI framework support
- JavaFX community for UI development resources
- Medical professionals who provided domain expertise
- Open-source contributors

---

<div align="center">

**Built with ❤️ for Healthcare Professionals**

[Report Bug](https://github.com/Qwen88wen/D-Assist/issues) · [Request Feature](https://github.com/Qwen88wen/D-Assist/issues)

</div>
