# grepandseek

grepandseek is a powerful terminal-based search engine for your local files. It provides fast text search capabilities across many file types by creating and maintaining an index of your files.

## Features

- **Full-text search** across many file formats
- **Fast indexing** with multi-threading support
- **Rich terminal UI** with progress bars and highlighted search results
- **Metadata extraction** from various file formats
- **Configurable indexing** with path management and ignore patterns
- **Support for many file types** including:
  - Documents: .txt, .pdf, .docx, .doc, .rtf, .odt
  - Images: .jpg, .jpeg, .png, .gif, .tiff, .tif
  - Data: .csv, .json, .xlsx, .xls
  - Media: .mp3, .ogg, .wav
  - Web: .html, .htm
  - Email: .eml, .msg
  - And more!

## Installation

### Prerequisites

1. Install [ExifTool](https://exiftool.org/install.html)
2. Install [textract dependencies](https://textract.readthedocs.io/en/stable/installation.html) (optional, but recommended for full text extraction)

### Install grepandseek

```bash
git clone https://github.com/alec-jensen/grepandseek.git
cd grepandseek
pip install -r requirements.txt
```

## Getting Started

### Initial Setup

Initialize the search index:

```bash
python -m grepandseek.main indexer init
```

This command will prompt you for a directory to index. You can add more paths later.

### Basic Usage

Search for files containing specific text:

```bash
python -m grepandseek.main search "your search term"
```

### Commands Reference

#### Search Commands

```bash
# Basic search
python -m grepandseek.main search "search term"

# Limit results (default is 10)
python -m grepandseek.main search "search term" --limit 20

# Disable snippets in results
python -m grepandseek.main search "search term" --snippets False
```

#### Indexer Commands

```bash
# Initialize the index
python -m grepandseek.main indexer init

# Update the index (refresh content)
python -m grepandseek.main indexer update-index

# Add a path to be indexed
python -m grepandseek.main indexer add /path/to/directory

# Remove a path from the index
python -m grepandseek.main indexer remove /path/to/directory

# List all indexed paths
python -m grepandseek.main indexer list

# Update index silently (no progress bar)
python -m grepandseek.main indexer update-index --silent
```
