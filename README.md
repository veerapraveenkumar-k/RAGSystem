# RAGSystem

# RAG System - Hands-On Project

A Retrieval-Augmented Generation (RAG) system implementation that extracts text from PDF documents for further processing and question-answering capabilities.

## Overview

This project demonstrates a RAG system that can process PDF documents by extracting text content, which can then be used for document-based question answering and information retrieval.

## Features

- **PDF Text Extraction**: Extract text content from PDF files using PyMuPDF
- **Error Handling**: Robust handling of empty or scanned PDFs
- **Clean Text Processing**: Filters out empty pages and provides clean text output

## Prerequisites

- Python 3.7+
- Jupyter Notebook or JupyterLab

## Installation

1. Clone the repository:
```bash
git clone https://github.com/veerapraveenkumar-k/RagSystem.git
cd RagSystem
```

2. Install required dependencies:
```bash
pip install PyMuPDF
```

## Usage

### PDF Text Extraction

The main function `extract_text_from_pdf()` extracts text from PDF files:

```python
import fitz

# Extract text from a PDF file
pdf_path = "path/to/your/document.pdf"
extracted_text = extract_text_from_pdf(pdf_path)

if extracted_text:
    print("Text extracted successfully!")
    print(extracted_text[:500])  # Print first 500 characters
else:
    print("No text could be extracted from the PDF")
```

### Function Parameters

- `pdf_path` (str): Path to the PDF file you want to process

### Return Values

- Returns extracted text as a string if successful
- Returns `None` if no text could be extracted (with a warning message)

## File Structure

```
RagSystem/
├── ragHandOn.ipynb          # Main Jupyter notebook with RAG implementation
├── README.md               # This file
└── requirements.txt        # Python dependencies (if applicable)
```

## Dependencies

- **PyMuPDF (fitz)**: For PDF text extraction and manipulation

## Error Handling

The system handles various edge cases:
- Empty PDF files
- Scanned PDFs without extractable text
- Corrupted or unreadable PDF files
- Pages with no text content

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Author

**Veera Praveen Kumar K**
- GitHub: [@veerapraveenkumar-k](https://github.com/veerapraveenkumar-k)

## Future Enhancements

- [ ] Add text chunking for large documents
- [ ] Implement vector embeddings for semantic search
- [ ] Add support for multiple document formats
- [ ] Integrate with language models for question-answering
- [ ] Add web interface for document upload and querying

## Troubleshooting

### Common Issues

1. **"No module named 'fitz'"**
   - Solution: Install PyMuPDF using `pip install PyMuPDF`

2. **"No extractable text found"**
   - This usually means the PDF is scanned or image-based
   - Consider using OCR tools like Tesseract for scanned documents

3. **Memory issues with large PDFs**
   - Process PDFs page by page for memory efficiency
   - Consider implementing text chunking strategies
