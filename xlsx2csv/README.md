# excel-to-csv

Convert several Excel files in Google Cloud Storage to CSV format using Python and the `pandas` library. This tool enables easy conversion of Excel files to CSV, making it convenient for loading data into Google BigQuery or other data processing tasks.

## Insatllation

Make sure you have the required libraries installed:

- *pandas* - Python library for data analysis and manipulation
- *google-cloud-storage* - Python library for Google Cloud managed service for storing unstructured data

Install the dependencies using `pip`:
```bash
pip3 install pandas
pip3 install google-cloud-storage
pip3 install xlrd
pip3 install openpyxl
```

## How to use

1. You should create a source and destination folder in your Google Cloud Storage bucket.
2. Place your Excel files into the source folder. for example:
```bash
# list files with .xls format
gsutil ls gs://folder/*.xls
# move .xls files into source folder
gsutil mv gs://folder/*.xls gs://folder/source/
gsutil ls gs://folder/*.xlsx
gsutil mv gs://folder/*.xlsx gs://folder/source/
```   
3. Modify the parameters in the main.py file as follows:
```bash
# you should place the full path (without 'gs://') for both source and output folder name.
bucket_name = ""
source_folder_name = ""
output_folder_name = ""
```
4. Run the main.py script.

## Expected result

After running the script, the converted CSV files will be saved in the specified output folder within your Google Cloud Storage bucket. The script will display the names of the saved CSV files:

```bash
CSV files saved in the gs://sample/output folder on Google Cloud Storage:
abc.csv
def.csv
```
You can now use the CSV files for further data processing, analysis, or loading into Google BigQuery.
