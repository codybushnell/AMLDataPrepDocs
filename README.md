
# Azure Machine Learning Data Prep Public Preview

The Azure Machine Learning Data Prep SDK is used to load, transform, and write data for machine learning workflows. You can interact with the SDK in any Python environment, including Jupyter Notebooks or your favorite Python IDE. The Azure Machine Learning Data Prep SDK includes the following set of functionalities to help prepare your data for modeling:

- Intelligent transforms: Use the SDK to derive or split a column by example, impute missing values, fuzzy group, auto join, and perform other automated tasks.
- Smart reading functionality: The SDK can automatically detect any of the supported file types. You don’t need to use special file readers for CSV, text, Excel, etc., or to specify delimiter, header, or encoding parameters.
- Varying schema processing: The SDK engine can read different columns per row instance, also sometimes referred to as ragged-right format.
- Scale through streaming: Instead of loading all the data into memory, the SDK engine serves data using streaming, allowing it to scale and perform better on large datasets.
- Cross-platform functionality with a single code artifact: Write to a single SDK and run it on Windows, macOS, Linux, or Spark in a scale-up or scale-out manner. When running in scale-up, the engine attempts to utilize all hardware threads available, when running scale-out the engine allows the distributed scheduler to optimize execution.


## Installation
### DataPrep SDK
install from PyPI:
```    
 pip install --upgrade azureml-dataprep
```
## New Azure Data Prep API
Here are examples on how to use the new DataPrep API:
- [Getting Started](Scenarios/GettingStarted/getting-started.ipynb)
- [DataPrep Transforms Examples](API)
- [End-to-End Scenario](Scenarios/NYTaxiCab)
- [API Reference Docs](http://aka.ms/data-prep-sdk)

## Known Issues

- <b>If running version 0.1.0</b>: To fix "Error Message: Cannot run the event loop while another loop is running", downgrade Tornado version to 4.5.3. Restart any running kernels for the change to take effect.
```    
pip install -U tornado==4.5.3
```
