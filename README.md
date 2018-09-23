
# Azure Data Preparation Codename "Pendleton" Public Preview

## Download and Installation Links
Download:

### DataPrep SDK
install from PyPI:
```    
 pip install azureml-dataprep
```
## New Azure Data Prep API
Here are examples on how to use the new DataPrep API:
- [Getting Started](Scenarios/GettingStarted/getting-started.ipynb)
- [DataPrep Transforms Examples](API)
- [End-to-End Scenario](Scenarios/NYTaxiCab)

## Known Issues
 - To fix "Error Message: Cannot run the event loop while another loop is running", downgrade Tornado version to 4.5.3. Restart any running kernels for the change to take effect.
```    
pip install -U tornado==4.5.3
```
