# Ingestion Pipeline Testing

This branch contains the implementation and testing of the ETL ingestion pipeline for the App Store Review Sentiment Analysis project.

## Scope

The work in this branch focuses on:

- Creating the MySQL database schema
- Building the four database tables
  - App
  - Country
  - Raw_Reviews
  - Cleaned_Reviews
- Importing cleaned datasets into MySQL
- Testing repeated ingestion using the same RSS database
- Testing ingestion using the new RSS database
- Documenting issues identified during repeated ingestion testing

## Documentation

The following documents are included in the `docs` folder:

- Repeated Ingestion run Test.pdf
- App_Store_Data_Ingestion.ipynb
  
The code script regarding the loading is in the 'App_Store_Data_Ingestion.ipynb', right after the line: 'part for Data Schema Design and Data Ingestion'

Some previously defined fields get changed: 1. date->review_date, in the table raw_reviews(only change name)

                                            2. language->review_language, in the table raw_reviews(only change name)
                                            
                                            3. The empty_after_cleaning field is dropped, in the table raw_reviews
                                            
                                            4. record_remove_reason field now includes 4 categories of values:'"Missing Review Content", 
                                            'Duplicated_Records',' Non-English Review Content', "Empty Content After Cleaning"
## Current Status

The ingestion pipeline has been successfully implemented and tested for the same RSS database scenario(Skipped the duplicates, while repeatedly loading the same data).

For testing on the new RSS dataset, a design issue was identified, and this issue has been documented in 'Repeated Ingestion run Test.pdf'.

