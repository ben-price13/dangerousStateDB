# Most Dangerous State Database Project

## Python Libraries & Modules
- mysqlclient
- mysql-connector-python
- sqlalchemy
- csv

## Data Cleaning
The data in its Raw form is not ideal for the project.
A Python notebook utilizing the Pandas and Numpy Python libraries was used to clean the four .csv datasets.
Some RawData files were removed after cleaning to avoid conflicts with github's maximum file size of 100 MB.
However, a .pdf was saved to the CleanData directory which shows the results of the DataCleaning.ipynb notebook.
This .pdf details via Python comments the basic analysis and logic behind the removal or renaming of attributes.
The clean data was saved as .csv files in the CleanData directory.

During the creation of the database, there were some issues with the size of the data being added to the database.
To address this, a second round of data cleaning was done (file DataCleaningPt2.ipynb) in which three files were created.
Two files were simplified versions of the independent murder and total murder .csv files which were made to be only 5000 rows each.
Additionally, an oris.csv file was created to house each of the unique ORIs, which resulted in <9000 rows instead of the original >30,000 that were being looped through to create the ORIs table in the database.  These new files were stored in the CleanData directory, and the old files were left there for reference.

## Database Planning
MySQL Workbench was used to create an EER diagram of the database with the following tables:
- TotalMurders
- IndividualMurders
- ORIs
- CrashFatalities
- Populations
- States
- Regions

The model file as well as a screenshot of the EER diagram have been added to the directory for reference.

## Table Creation
Table creation and insertion were performed in the CreateDatabase.ipynb file.  Sqlalchemy was used to connect to the database and the Python csv library was used to read-in the data to be added.
Please take caution when running portions of the Python notebook file.  The data is relatively large and can take quite a long time to be added to each table.  Only run the blocks of code for creating the tables and inserting data when absolutely necessary!

