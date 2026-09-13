Gen_AI

Coursework notebooks for the Generative AI module — Post Graduate Program in AI & Data Science, Jio Institute.

Contents
File	Description
Generative AI - Assignment 1.ipynb	Assignment 1: LangChain pipelines for (1) BBC news topic classification, summarization and entity extraction, and (2) job posting category classification and requirements extraction.
Class Exercise.ipynb	In-class exercise notebook.
Setup
1. Install dependencies
bash
pip install langchain langchain-groq pandas python-dotenv pydantic
2. API key

The notebook reads a Groq API key from a .env file at the repo root:

GROQ_API_KEY=your-key-here

Get a free key at console.groq.com. If no .env is found, the notebook falls back to an interactive prompt for the key.

3. Data files

Assignment 1 expects the following CSVs in the same directory as the notebook (provided as part of the assignment, not included in this repo):

bbc-news-data.csv — BBC News Archive (tab-separated)
job_title_des.csv — Job Title and Job Description dataset
Running

Open the notebook in Jupyter and run all cells top to bottom. Each part saves its final merged results to CSV:

part1_news_analysis_output.csv
part2_job_analysis_output.csv
Notes
Two Groq models are used (gpt-oss-120b for structured extraction, gpt-oss-20b for lighter text tasks) to spread work across separate free-tier rate limits.
By default the notebook processes the first 30 news articles and first 25 job postings, per the assignment brief. To run the full datasets (bonus), raise N_ARTICLES / N_JOBS in Part 1 Step 6 and Part 2 Step 1 accordingly — note this will hit Groq's free-tier rate limits, so the assignment brief suggests switching to Ollama with a local SLM for full-dataset runs.
