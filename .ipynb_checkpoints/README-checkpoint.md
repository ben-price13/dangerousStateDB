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

At this point in the cleaning, a discrepancy was found between the ORIs from the total murder table and those found in the individual murder table after reducing the rows to a random 5000 entries.  To correct this discrepancy, and to ensure the total murder table represents the individual murder table accuractely, a new approach was taken.  Instead of using the total murder data as-is, we instead created triggers on insert into the individual murder table to increment the total murders for a given ORI and year.  In this way, the total murder table will exactly reflect the number of murders in the individual murder table.  Additionally, we inserted ORIs used in the ind_murd_simple.csv instead of from the total_murd_simple.csv file.

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

## Project Write-Up
The final project write-up is located in the file mostDangerousState.ipynb.  In the write up, each aspect of the project has been combined to show how the database was created as well as to examine the data and find out which state is the most dangerous (for the purposes of the project).  A walkthrough of the content of this file has been recorded and can be viewed at https://www.youtube.com/watch?v=oTIvx16FbmM . For any questions, please feel free to reach out to benjamin.price@colorado.edu and I'd be happy to answer any questions!