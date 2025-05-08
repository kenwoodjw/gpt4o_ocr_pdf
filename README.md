# GPT-4o OCR PDF to Markdown Tool

**Author:** kenwood  
**Version:** 0.0.2  
**Type:** Dify Plugin Tool

## Description

This tool uses OpenAI's GPT-4o model to perform OCR (Optical Character Recognition) on PDF files and convert the extracted content to Markdown format. It preserves the document structure including headings, paragraphs, lists, and tables.

Inspired by [mistral_ocr_pdf](https://github.com/reorx/mistral_ocr_pdf) project.

## Features

- Extract text from PDF files using GPT-4o's advanced vision capabilities
- Convert extracted content to clean, formatted Markdown
- Preserve document structure (headings, paragraphs, lists, tables)
- Support for both Azure OpenAI and OpenAI APIs
- Process PDFs in batches for efficient handling of large documents
- Maintain original formatting as much as possible

## Requirements

- Python 3.8+
- Dify Plugin Framework
- OpenAI API key or Azure OpenAI API credentials
- PyMuPDF (for PDF processing)

## Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Configuration

The tool supports both OpenAI and Azure OpenAI APIs. You need to provide the appropriate credentials based on which service you want to use.

### OpenAI Configuration

- **API Type**: Select "OpenAI"
- **API Key**: Your OpenAI API key
- **Model Name**: (Optional) The model to use (defaults to "gpt-4o")

### Azure OpenAI Configuration

- **API Type**: Select "Azure OpenAI"
- **API Key**: Your Azure OpenAI API key
- **API Endpoint**: Your Azure OpenAI endpoint URL
- **Deployment Name**: Your GPT-4o model deployment name
- **API Version**: Azure OpenAI API version (e.g., "2023-05-15")

## Usage

Once configured, you can use the tool to extract text from PDF files and convert it to Markdown:

1. Upload a PDF file
2. The tool processes the PDF in batches
3. GPT-4o extracts text and formats it as Markdown
4. The final Markdown content is returned

## How It Works

1. The PDF is loaded and each page is converted to an image
2. Images are encoded in base64 format
3. Images are sent to GPT-4o with instructions to extract text and format as Markdown
4. The tool processes the PDF in batches (up to 5 pages at a time) to handle large documents
5. The extracted Markdown content from each batch is combined into a single document

## Limitations

- Performance depends on the quality of the PDF
- Very large PDFs may take longer to process
- Complex layouts or tables may not be perfectly preserved
- Images in the PDF will be described but not included in the Markdown output

## License

[MIT License](LICENSE)
