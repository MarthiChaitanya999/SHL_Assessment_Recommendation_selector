# SHL Assessment Recommender

![SHL Assessment Recommender](https://img.shields.io/badge/Version-1.0-blue)  
An intelligent web application and API to recommend SHL assessments based on job descriptions or hiring queries. Built with Streamlit, FastAPI, and SentenceTransformers, it features a modern UI with a gradient background and black input box.

© 2025 Chaitanya Marthi | SHL GenAI Assignment

---

## Overview

The SHL Assessment Recommender helps recruiters and HR professionals find the best SHL assessments for their hiring needs. It accepts natural language queries (e.g., "cognitive test for software engineers under 45 minutes") or job description URLs, returning up to 10 relevant assessments with details like name, URL, test type, duration, remote testing, adaptive/IRT status, and AI-generated relevance explanations.

### Features
- **Semantic Search**: Matches queries to assessments using embeddings from Mistral (via OpenRouter API).
- **Custom UI**: Gradient background (#667eea to #764ba2), black input box with white text.
- **Filters**: Category and maximum duration sliders.
- **Output**: Detailed recommendations in an expander layout, with a table view option.
- **Data Source**: Scrapes SHL’s product catalog (`https://www.shl.com/solutions/products/product-catalog/`).

---

## Tech Stack

- **Backend**: FastAPI
- **Frontend**: Streamlit
- **AI/ML**: SentenceTransformers, OpenRouter API (Mistral Small 3.1)
- **Data Processing**: pandas, numpy
- **Scraping**: BeautifulSoup, requests
- **Visualization**: Plotly

---

## Prerequisites

- Python 3.8+
- Git
- An OpenRouter API key (get one from [OpenRouter](https://openrouter.ai/))

---

## Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/MarthiChaitanya999/shl-assessment-recommender.git
   cd shl-assessment-recommender

2.Install Dependencies
pip install -r requirements.txt

3.Set Up Environment Variables Create a .env file in the root directory and add your OpenRouter API key:
OPENROUTER_API_KEY=your-api-key-here

4.Run the Application
API Only:
uvicorn api:app --host 0.0.0.0 --port 8000 --reload

5.Streamlit Frontend
streamlit run app.py

6.Access the App
API: http://localhost:8000/api/recommend
Web UI: http://localhost:8501


Usage
Web Interface
Open the Streamlit app in your browser.
Use the sidebar to filter by assessment category and maximum duration.
Enter a query (e.g., "We need a test for Java developers under 45 minutes") in the black input box.
Click "Get Recommendations" to see results in expandable sections with details and relevance explanations.
API Endpoint
Endpoint: /api/recommend
Method: GET
Parameters:
query: Your job description or hiring need (required).
top_k: Number of recommendations (default: 10, max: 10).

Example:
curl "http://localhost:8000/api/recommend?query=We%20need%20a%20cognitive%20test%20for%20software%20engineers%20under%2045%20minutes"

Response:
{
  "recommendations": [
    {
      "name": "Java 8 (New)",
      "url": "https://www.shl.com/solutions/products/product-catalog/view/java-8-new/",
      "test_type": "K",
      "remote_testing": "Yes",
      "adaptive_irt": "No",
      "duration": "N/A",
      "relevance": "This test assesses Java programming skills essential for software engineers."
    },
}

Project Structure
• api.py - FastAPI backend
• app.py - Streamlit frontend
• scraper.py - SHL catalog scraper
• openrouter_api.py - OpenRouter API integration
• shl_assessments.csv - Cached assessment data
• requirements.txt - Dependencies
• .env - Environment variables
• README.md - This file

Data
Source: Scraped from SHL’s product catalog.
Fields: name, URL, duration, test_type (e.g., A=Ability, B=Behavior, C=Competency, K=Knowledge, P=Personality, S=Skills), remote_testing, adaptive_irt.
Note: Duration is often "N/A" unless scraped from individual pages.
Contributing
Fork the repository.
Create a feature branch (git checkout -b feature/your-feature).
Commit changes (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a pull request.
Credits
Developed by: Chaitanya Marthi
GitHub: MarthiChaitanya999
Powered by: FastAPI, Streamlit, SentenceTransformers, OpenRouter API
Assignment: SHL GenAI Assignment, © 2025 Chaitanya Marthi
License
This project is licensed under the MIT License - see the  file for details.


---

### Instructions to Use:
1. **Create the File**:
   - Copy the text above.
   - Open a text editor (e.g., VS Code, Notepad).
   - Paste the content and save it as `README.md` in your project’s root directory (`shl-assessment-recommender/`).

2. **Push to GitHub**:
   ```bash
   git add README.md
   git commit -m "Add README file"
   git push origin main



I used free API, If anything merge/cashes CONTACT ME Mail id : marthichaitanya999@gmail.com
                                                 linkedin Id : https://www.linkedin.com/in/marthi-chaitanya-392047238/

