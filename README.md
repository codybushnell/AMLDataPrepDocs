
# Azure Machine Learning Data Prep Public Preview

The Azure Machine Learning Data Prep SDK is used to load, transform, and write data for machine learning workflows. You can interact with the SDK in any Python environment, including Jupyter Notebooks or your favorite Python IDE. The Azure Machine Learning Data Prep SDK includes the following set of functionalities to help prepare your data for modeling:

- Intelligent transforms: Use the SDK to derive or split a column by example, impute missing values, fuzzy group, auto join, and perform other automated tasks.
- Smart reading functionality: The SDK can automatically detect any of the supported file types. You don’t need to use special file readers for CSV, text, Excel, etc., or to specify delimiter, header, or encoding parameters.
- Varying schema processing: The SDK engine can read different columns per row instance, also sometimes referred to as ragged-right format.
- Scale through streaming: Instead of loading all the data into memory, the SDK engine serves data using streaming, allowing it to scale and perform better on large datasets.
- Cross-platform functionality with a single code artifact: Write to a single SDK and run it on Windows, macOS, Linux, or Spark in a scale-up or scale-out manner. When running in scale-up, the engine attempts to utilize all hardware threads available, when running scale-out the engine allows the distributed scheduler to optimize execution.


## Installation
### Data Prep SDK
install from PyPI:
```    
 pip install --upgrade azureml-dataprep
```
## New Azure Data Prep API
Here are examples on how to use the new Data Prep API:
- [Getting Started](Scenarios/GettingStarted/getting-started.ipynb)
- [Data Prep Transforms Examples](API)
- [End-to-End Scenario](Scenarios/NYTaxiCab)
- [API Reference Docs](http://aka.ms/data-prep-sdk)

## Known Issues

- <b>If running version 0.1.0</b>: To fix "Error Message: Cannot run the event loop while another loop is running", downgrade Tornado version to 4.5.3. Restart any running kernels for the change to take effect.
```    
pip install -U tornado==4.5.3
```
## Release Notes
### 2018-11-1

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
