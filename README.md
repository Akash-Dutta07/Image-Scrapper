# Image Scraper

A Python-based web scraper that automatically downloads product images from eBay search results using Selenium WebDriver.

## Overview

This project provides an automated solution for scraping product images from eBay. It uses Selenium to navigate through eBay's search results and downloads images based on your search query.

## Features

- 🔍 Automated eBay product search
- 📸 Bulk image downloading
- 🤖 Headless browser support (configurable)
- 🛡️ Built-in anti-detection measures
- 📁 Organized image storage in custom folders
- ⚡ Configurable timeouts and wait conditions

## Prerequisites

- Python 3.12 or higher
- Google Chrome browser installed
- ChromeDriver (compatible with your Chrome version)

## Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd image-scraper
```

2. **Create a virtual environment** (recommended)
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

## Dependencies

The project uses the following main libraries:
- `selenium` - Web browser automation
- `requests` - HTTP requests for downloading images
- `beautifulsoup4` - HTML parsing (optional)
- `numpy` - Array operations
- `pandas` - Data manipulation
- Additional scientific computing libraries (matplotlib, seaborn, scikit-learn) for data analysis

## Usage

### Basic Usage

Run the scraper with default settings:

```python
from code import EbayImageScraper

# Initialize scraper
scraper = EbayImageScraper(url="https://www.ebay.com/")

# Run scraper with custom search query
scraper.run(text="gaming laptop", folder_name="gaming_laptops")
```

### Using Jupyter Notebook

Open the included `code.ipynb` notebook and run the cells to execute the scraper interactively.

### Customization

You can customize the scraper behavior:

```python
# Change timeout duration (default: 7 seconds)
scraper = EbayImageScraper(url="https://www.ebay.com/", timeout=10)

# Customize search and output folder
scraper.run(text="wireless headphones", folder_name="headphones_images")
```

## Project Structure

```
image-scraper/
├── code.ipynb           # Jupyter notebook with implementation
├── main.py             # Main entry point (customizable)
├── requirements.txt    # Project dependencies
├── pyproject.toml     # Project configuration
├── uv.lock            # Dependency lock file
├── .gitignore         # Git ignore rules
├── .python-version    # Python version specification
└── README.md          # This file
```

## How It Works

1. **Initialization**: Creates a Chrome WebDriver instance with anti-detection settings
2. **Navigation**: Opens eBay homepage and waits for page load
3. **Search**: Enters search query and submits
4. **Scraping**: Locates product images using CSS selectors
5. **Download**: Downloads each image and saves with sequential naming
6. **Cleanup**: Closes browser and reports completion

## Configuration

The scraper includes several built-in configurations:

- **Chrome Options**:
  - Disabled HTTP/2
  - Incognito mode
  - Anti-automation detection bypass
  - Custom user agent

- **Timeouts**: Configurable wait times for page elements
- **Image Selection**: Uses CSS selector `img.s-card__image` to target product images

## Output

Images are saved in the specified folder with the naming convention:
```
folder_name/
├── image_1.jpg
├── image_2.jpg
├── image_3.jpg
└── ...
```

## Error Handling

The scraper includes error handling for:
- Page load failures
- Missing search elements
- Image download failures
- Network timeouts

Errors are printed to console with descriptive messages.


---

**Note**: This tool is provided as-is for educational purposes. Always ensure you have permission to scrape and use images from websites.
