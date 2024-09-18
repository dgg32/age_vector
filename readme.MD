
  
  

# Introduction

  

This repository contains code and data for my article "[PostgreSQL Goes Multi-Model: Graph, Vector, and SQL](https://medium.com/@dgg32/clinical-trial-search-with-google-spanner-graph-sql-vector-and-llm-all-in-one-query-5ada29f840cd)".

  
  
  

  

# Prerequisite

  

UMLS free tier

  
Docker

Python

  
  

# Run

1. If you want to reannotate the drugs in the trial data, create a config.yaml in the directory and fill in the following information:

>  umls_token: [YOUR_UMLS_TOKEN]

> google_sheet_id: [YOUR_MANUAL_CURATION_SHEET_ID]

> google_sheet_node_name: [YOUR_MANUAL_CURATION_SHEET_NAME]

  

The Google sheet is used to correct some mismapping of UMLS. It contains three columns: "substance", "correct_cui", and "preferred_umls_name". The substance contains the drugs that you want to manually correct. Correct_cui contains a semicolon delimited list of CUI that you want the drugs map to. And the preferred_umls_name is a semicolon delimited list of names that correspond to the CUI. An example is

  
| substance |  correct_cui|preferred_umls_name|
|--|--|--|
| lapatinib plus capecitabine  | C1506770;C0671970 |lapatinib;capecitabine|


If you want to redo the vector embedding for disease_4.json, fill in the OpenAI API key in a file call "config.yaml" and run embedding.ipynb

2. Start PostgreSQL Docker instance as described in the article  

3. Run import.ipynb to import the data

4. Run queries either in a Python or using tools such as DBeaver

## Authors

  

  

*  **Sixing Huang** - *Concept and Coding*

  

  

## License

  

  

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
