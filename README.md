# Information Redaction System

## Description

An advanced AI-powered document redaction system that automatically detects and redacts Personally Identifiable Information (PII) and Protected Health Information (PHI) from PDF documents. The system uses LangChain with LLM integration to generate contextually appropriate dummy data replacements, ensuring documents remain useful while protecting sensitive information.

This is a duplicate/variant of the `backend` project with similar functionality.

## Features

- **Intelligent PII/PHI Detection**:
  - Names, addresses, phone numbers, emails
  - Social Security Numbers (SSN)
  - Medical Record Numbers (MRN)
  - Health Plan Beneficiary Numbers
  - Medical conditions and medications
  - Doctor and hospital names
  - Credit card numbers, account numbers
  - IP addresses, URLs
  - Dates of birth and ages

- **Dual Redaction Modes**:
  - **Dummy Replacement**: LLM-generated realistic fake data
  - **Anonymization**: Generic placeholders (e.g., [NAME_1])

- **Visual Element Processing**:
  - Image classification and redaction
  - Text box overlays for images
  - Replacement image insertion
  - Maintains document layout

- **Document Processing**:
  - Docling-powered PDF parsing
  - OCR support for scanned documents
  - Page-by-page processing for accuracy
  - Coordinate-precise redaction

- **Policy Management**:
  - Configurable redaction policies
  - Global and entity-specific rules
  - YAML-based policy definitions
  - Audit logging

- **Output Options**:
  - Redacted PDF generation
  - Overlay PDF showing redaction locations
  - Color-coded redaction types
  - Processing logs and metrics

## Technologies Used

- **FastAPI** - Web framework for API endpoints
- **LangChain** - LLM orchestration and prompt management
- **OpenRouter** - LLM API integration
- **Docling** - Advanced document processing
- **PyMuPDF (fitz)** - PDF manipulation
- **Pydantic** - Data validation
- **OpenCV** - Image processing
- **BeautifulSoup** - Web scraping for replacement images
- **Python 3.9+**

## Getting Started

### Prerequisites

- Python 3.9+
- OpenRouter API key

### Installation

```bash
# Install dependencies
pip install -r requirements.txt
```

### Configuration

Create a `.env` file:

```bash
OPENROUTER_API_KEY=your_openrouter_api_key
```

### Running the Application

```bash
# Start the FastAPI server
uvicorn app_main:app --host 0.0.0.0 --port 8000 --reload
```

## Usage

### Basic Redaction

```python
from app_main import SecureInfoRedactionPipeline

# Initialize pipeline
pipeline = SecureInfoRedactionPipeline("input.pdf")

# Process document
redacted_pdf = pipeline.process()
```

## Redaction Modes

### Dummy Replacement Mode
- Uses LLM to generate realistic fake data
- Maintains document readability
- Contextually appropriate replacements

### Anonymization Mode
- Generic placeholders with occurrence tracking
- Consistent replacement across document

## License

This project is licensed under the terms specified in the LICENSE file.

## Note

This project shares similar functionality with the `backend` project. Consider consolidating if they serve the same purpose.
