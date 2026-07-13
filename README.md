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
  

## Current Status

The ingestion pipeline has been successfully implemented and tested for the same RSS database scenario(Skipped the duplicates, while repeatedly loading the same data).

For testing on the new RSS dataset, a design issue was identified, and this issue has been documented in 'Repeated Ingestion run Test.pdf'.

