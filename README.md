# Personalized Job Recommendations using NLP and Data Analysis

This project aims to provide personalized job recommendations based on a candidate's resume and a dataset of job postings. The system uses Natural Language Processing (NLP) and Data Analysis techniques to compare the candidate's skills and job requirements. The project also includes data visualization to explore the job market and analyze the top skills for each job category.

## Table of Contents

1. [Data Collection and ETL Pipeline](#data-collection-and-etl-pipeline)
2. [Natural Language Processing](#natural-language-processing)
3. [Data Visualization](#data-visualization)
4. [Job Recommendation System](#job-recommendation-system)
5. [Usage](#usage)

## Data Collection and ETL Pipeline

The project collects job posting data by scraping various job websites. The ETL pipeline is built using AWS Lambda, DynamoDB, S3, and SageMaker. AWS Lambda is used for serverless computing, allowing for the periodic execution of the scraping process. The scraped data is stored in DynamoDB, while AWS S3 is used to store the raw and processed data files. SageMaker is used for hosting the pre-trained NLP model.

## Natural Language Processing

The project uses the Paraphrase-MPNet-Base-v2 model, a SentenceTransformer model based on the MPNet architecture. This model is particularly suitable for generating sentence embeddings, capturing semantic similarity between the candidate's skills and job requirements.

## Data Visualization

Plotly is used for creating interactive data visualizations, such as bar charts, to analyze and explore the job market. The visualizations include:

- Top skills for each job category.
- Number of jobs by location.
- New job postings by day of the week.
- New job postings by week and category.

## Job Recommendation System

The recommendation system is based on two similarity measures:

- Cosine Similarity: Measures the cosine of the angle between two vectors, resulting in a similarity score between -1 and 1.
- Modified Jaccard Similarity: Calculates the ratio of the intersection to the length of the job requirements set.

The system recommends the top 20 jobs based on each similarity score, providing a personalized list of job opportunities for the candidate.

## Usage

To use the project, follow these steps:

1. Set up the AWS services (Lambda, DynamoDB, S3, and SageMaker) and configure the scraping process.
2. Collect and preprocess the job postings data using the ETL pipeline.
3. Train and fine-tune the Paraphrase-MPNet-Base-v2 model.
4. Use the provided functions to analyze and visualize the job market.
5. Call the `recommend_jobs()` function to generate personalized job recommendations for a candidate.

Note: Make sure to have the required libraries installed, such as pandas, sklearn, and plotly, before running the code.
