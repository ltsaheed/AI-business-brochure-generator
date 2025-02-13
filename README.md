# AI Website Scraper and Brochure Generator

## Overview
This project is a Python-based tool that scrapes a company's website, extracts relevant information, and generates a brochure in Markdown format. It uses OpenAI's GPT-4o-mini model to analyze web pages and create structured content suitable for a company's brochure.

## Features
- Scrapes website content using `requests` and `BeautifulSoup`
- Extracts text while ignoring scripts, styles, images, and form inputs
- Identifies relevant links for company-related pages (e.g., About, Careers)
- Streams AI-generated brochure content to the terminal using `rich`
- Ensures markdown formatting for structured output

## Requirements
Before running the script, ensure you have the following dependencies installed:

```bash
pip install requests beautifulsoup4 openai python-dotenv rich
```

## Setup
1. Clone or download the repository.
2. Create a `.env` file in the project directory and add your OpenAI API key:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```
3. Ensure the API key starts with `sk-proj-` and is correctly loaded.

## Usage

### Run the Brochure Generator
```python
stream_brochure("LostPetFlyers.com", "https://lostpetflyers.com")
```
This will:
- Scrape the given URL
- Extract meaningful text
- Identify useful links for the brochure
- Stream the generated markdown content to the terminal

### Generate a Brochure Without Streaming
```python
create_brochure("LostPetFlyers.com", "https://lostpetflyers.com")
```
This will generate and print the full brochure at once.

### Extract Website Contents
```python
website = Website("https://example.com")
print(website.get_contents())
```
This will retrieve and print the cleaned-up textual content of the given webpage.

### Extract Relevant Links
```python
links = get_links("https://example.com")
print(links)
```
This will return a JSON object containing categorized links relevant to the company.

## Code Structure
```
project/
│── website_scraper.py      # Main script handling web scraping
│── openai_utils.py        # Handles AI interactions
│── .env                   # Stores OpenAI API key
│── README.md              # Project documentation
```

## Technologies Used
- **Python**: Core scripting language
- **Requests**: Fetching webpage content
- **BeautifulSoup**: Parsing HTML for text and links
- **Rich**: Formatting terminal output with markdown
- **OpenAI API**: Generating AI-powered content

## Troubleshooting
1. **API Key Issues**:
   - Ensure the key is loaded correctly from `.env`.
   - Verify the key format (`sk-proj-xxxxx`).
2. **Scraper Not Extracting Data**:
   - Check if the website has a `robots.txt` file blocking scraping.
   - Ensure the correct headers are passed in `requests`.
3. **Markdown Not Displaying Properly**:
   - Confirm `rich` is installed and properly rendering markdown.

## Future Improvements
- Add caching to avoid redundant requests.
- Implement error handling for broken/missing URLs.
- Improve filtering of irrelevant links using AI.

## License
This project is released under the MIT License.

