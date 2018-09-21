
# Azure Data Preparation Codename "Pendleton" Public Preview

## Download and Installation Links
Download:

- [DataPrep SDK (public preview candidate)](https://dataprepdownloads.azureedge.net/pypi/monthly-AE98437A2C8F6F45842C/latest/)
```    
 pip install install azureml-dataprep
```
## New Azure Data Prep API
Here are examples on how to use the new DataPrep API:
- [DataPrep Transforms Examples](API)
- [End-to-End Scenario](Scenarios/NYTaxiCab)

## Known Issues
 - To fix "Error Message: Cannot run the event loop while another loop is running", downgrade your Tornado version to 4.5.3
```    
pip install -U tornado==4.5.3
```
