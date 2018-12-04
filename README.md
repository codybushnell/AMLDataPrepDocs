# Azure Machine Learning Data Prep Public Preview

The Azure Machine Learning Data Prep SDK is used to load, transform, and write data for machine learning workflows. You can interact with the SDK in any Python environment, including Jupyter Notebooks or your favorite Python IDE. The Azure Machine Learning Data Prep SDK includes the following set of functionalities to help prepare your data for modeling:

- Intelligent transforms: Use the SDK to derive or split a column by example, impute missing values, fuzzy group, auto join, and perform other automated tasks.
- Auto reading functionality: The SDK can automatically detect any of the supported file types. You don’t need to use special file readers for CSV, text, Excel, etc., or to specify delimiter, header, or encoding parameters.
- Varying schema processing: The SDK engine can read different columns per row instance, also sometimes referred to as ragged-right format.
- Scale through streaming: Instead of loading all the data into memory, the SDK engine serves data using streaming, allowing it to scale and perform better on large datasets.
- Cross-platform functionality with a single code artifact: Write to a single SDK and run it on Windows, macOS, Linux, or Spark in a scale-up or scale-out manner. When running in scale-up, the engine attempts to utilize all hardware threads available, when running scale-out the engine allows the distributed scheduler to optimize execution.


## Installation
### Data Prep SDK
Install from PyPI:
```    
 pip install --upgrade azureml-dataprep
```
## New Azure ML Data Prep API

Here are examples on how to use the new Data Prep API:
- [Getting Started Tutorial](tutorials/getting-started/getting-started.ipynb)
- [How-To Guides](how-to-guides)
- [Case Study](case-studies/new-york-taxi)
- [API Reference Docs](http://aka.ms/data-prep-sdk)

## Known Issues

- **If running version 0.1.0**: To fix "Error Message: Cannot run the event loop while another loop is running", downgrade Tornado version to 4.5.3. Restart any running kernels for the change to take effect.
```    
pip install -U tornado==4.5.3
```
## Release Notes
### 2018-12-03
Breaking changes
 - `SummaryFunction.N` was renamed to `SummaryFunction.Count`.
  
Bug Fixes
 - Use latest AML Run Token when reading from and writing to datastores on remote runs. Previously, if the AML Run Token is updated in Python, the Data Prep runtime will not be updated with the updated AML Run Token.
 - Additional clearer error messages
 - to_spark_dataframe() will no longer crash when Spark uses Kryo serialization
 - Value Count Inspector can now show more than 1000 unique values
 - Random Split no longer fails if the original Dataflow doesn’t have a name  

### 2018-11-19

New Features:
- Created a new DataPrep CLI to execute DataPrep packages and view the data profile for a dataset or dataflow
- Redesigned SetColumnType API to improve usability
- Renamed smart_read_file to auto_read_file
- Now includes skew and kurtosis in the Data Profile
- Can sample with stratified sampling
- Can read from zip files that contain CSV files
- Can split datasets row-wise with Random Split (e.g. into test-train sets)
- Can get all the column data types from a dataflow or a data profile by calling .dtypes
- Can get the row count from a dataflow or a data profile by calling .row_count

Bug Fixes:
- Fixed long to double conversion 
- Fixed assert after any add column 
- Fixed an issue with FuzzyGrouping, where it would not detect groups in some cases
- Fixed sort function to respect multi-column sort order
- Fixed and/or expressions to be similar to how Pandas handles them
- Fixed reading from dbfs path.
- Made error messages more understandable 
- Now no longer fails when reading on remote compute target using AML token
- Now no longer fails on Linux DSVM
- Now no longer crashes when non-string values are in string predicates
- Now handles assertion errors when Dataflow should fail correctly
- Now supports dbutils mounted storage locations on Azure Databricks

### 2018-11-05

New Features:
- Type Count added to Data Profile
- Value Count and Histogram is now available
- More percentiles in Data Profile
- The Median is available in Summarize
- Python 3.7 is now supported
- When you save a dataflow that contains datastores to a Data Prep package, the datastore information will be persisted as part of the Data Prep package
- Writing to datastore is now supported
 
Bug Fixes:
- 64bit unsigned integer overflows are now handled properly on Linux 
- Fixed incorrect text label for plain text files in smart_read
- String column type now shows up in metrics view
- Type count now is fixed to show ValueKinds mapped to single FieldType instead of individual ones
- Write_to_csv no longer fails when path is provided as a string
- When using Replace, leaving “find” blank will no longer fail

## Datasets License Information 
IMPORTANT: Please read the notice and find out more about this NYC Taxi and Limousine Commission dataset here: http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml 

IMPORTANT: Please read the notice and find out more about this Chicago Police Department dataset here: https://catalog.data.gov/dataset/crimes-2001-to-present-398a4 

