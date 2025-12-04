# Documents Folder

This folder stores uploaded medical documents for RAG ingestion.

## Supported File Types

- PDF (.pdf)
- Microsoft Word (.docx)
- Plain Text (.txt)

## File Organization

Documents are organized by upload date and document ID:
```
documents/
├── 2025/
│   ├── 01/
│   │   ├── doc_001.pdf
│   │   ├── doc_002.docx
│   └── 02/
│       └── doc_003.pdf
```

## Storage

- Documents are permanently stored here after upload
- Filenames are sanitized and prefixed with document ID
- Original metadata is preserved in database
