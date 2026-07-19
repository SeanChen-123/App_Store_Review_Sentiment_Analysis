# New Documents

- **Ingestion_Final_Round** contains the latest version of the ingestion pipeline.
- **Repeated Ingestion Run Test Final** contains the latest repeated ingestion test results.


# Updates overview
In this script, we use a stable business key (dedup_key) instead of relying on row order or Python-generated primary keys.
The key is generated while combining 3 keys: 'app_id | country_name | review_id'.
This key uniquely identifies each raw review across ingestion runs and is used to detect duplicate records before inserting new data into the database.
We first insert the raw_review data into the database without creating the 'raw_review_pk'. 
After auto-incrementing the 'raw_review_pk'in SQL, the mapping between `dedup_key` and `raw_review_pk` is retrieved from the database and merged back into Python.
This mapping is then used to assign the correct foreign key (`raw_review_pk`) when inserting records into the `Cleaned_Reviews` table.
Ensuring referential integrity between the two tables.

# Validation results

Duplicates are successfully skipped.
The Insertion data in the new RSS ingestion run is reasonable.
All valid raw reviews are successfully loaded into `Cleaned_Reviews'.
ALL cleaned reviews stored in the cleaned table are not duplicated (No single raw_review table record responds to over one cleaned review record).
The duplicate counts may vary between ingestion runs. However, query validation shows the pipeline correctly skips existing records while inserting only new reviews.

