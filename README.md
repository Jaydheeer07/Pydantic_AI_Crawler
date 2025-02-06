# Pydantic AI Crawler

A Python-based web crawler implementation using Crawl4AI to extract content from websites. This project includes two scripts: one for single URL crawling and another for parallel crawling of multiple URLs from a sitemap.

## Prerequisites

- Python 3.7+
- Virtual Environment (recommended)
- Chrome/Chromium browser

## Installation

1. Create and activate a virtual environment:
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/MacOS
python -m venv venv
source venv/bin/activate
```

2. Install the required dependencies:
```bash
pip install crawl4ai
```

3. Install browser dependencies:
```bash
python -m playwright install --with-deps chromium
```

## Scripts

### 1. Single URL Crawler (`single_url.py`)

This script demonstrates basic usage of Crawl4AI to crawl a single webpage.

#### Features:
- Basic web crawling
- Error handling
- UTF-8 encoding support
- Logging configuration

#### Usage:
```bash
python single_url.py
```

The script will:
- Crawl the specified URL (default: https://docs.crawl4ai.com/)
- Save the crawled content to a file
- Log the process in both console and a log file

### 2. Multi URL Crawler (`multi_url.py`)

A more advanced implementation that supports parallel crawling of multiple URLs from a sitemap.

#### Features:
- Parallel crawling with configurable concurrency
- Memory and CPU usage monitoring
- Comprehensive error handling and logging
- Progress tracking
- Batch processing
- Detailed statistics and reporting

#### Usage:
```bash
python multi_url.py
```

The script will:
1. Fetch URLs from the specified sitemap
2. Process URLs in parallel batches
3. Create an `output` directory containing:
   - Individual markdown files for each crawled page
   - A `crawler.log` file with detailed logging
   - A `summary.txt` file with crawling statistics

#### Configuration:
You can modify these parameters in the script:
- `max_concurrent`: Number of parallel crawling tasks (default: 5)
- Browser settings in `browser_config`
- Crawler settings in `crawl_config`

#### Output Structure:
```
output/
├── crawler.log           # Detailed logging information
├── summary.txt          # Crawling statistics and summary
└── page_[n].md         # Crawled content files
```

## Error Handling

Both scripts include comprehensive error handling for common issues:
- Network errors
- Parsing errors
- Timeout issues
- Memory constraints

## Logging

The scripts provide detailed logging through:
- Console output
- Log files
- Progress updates
- Memory and CPU usage statistics (multi_url.py)

## Best Practices

1. Monitor resource usage when crawling many URLs
2. Adjust the `max_concurrent` parameter based on your system's capabilities
3. Check the log files for detailed information about any failures
4. Respect the target website's robots.txt and crawling policies

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

[MIT License](LICENSE)
