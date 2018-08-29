
# Azure Data Preparation Codename "Pendleton" Private Preview

## Download and Installation Links
Download:

- [Data Prep SDK](https://dataprepdownloads.azureedge.net/pypi/privPreview/latest/)

```    
pip install --upgrade --extra-index-url https://dataprepdownloads.azureedge.net/pypi/privPreview/latest/ azureml-dataprep
```

- [AzureML SDK](https://github.com/Azure/ViennaDocs/tree/master/PrivatePreview)
 
- [CLI link](https://github.com/Azure/ViennaDocs/blob/master/PrivatePreview/cli/CLI-101-Install-and-Local-Run.md)

## New Azure Data Prep API
Here are examples on how to use the new Data Prep API

- For examples to use different transforms [Examples](API)

- For an [End-to-End](Scenarios/NYTaxiCab)

## Known Issues
 - To fix "Error Message: Cannot run the event loop while another loop is running" downgrade your Tornado version to 4.5.3

