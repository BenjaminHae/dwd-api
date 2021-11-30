# dwd
Aktuelle Wetterdaten von allen Deutschen Wetterstationen

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Package version: 1.0.1
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >= 3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
from deutschland import dwd
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
from deutschland import dwd
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
from deutschland import dwd
from pprint import pprint
from deutschland.dwd.api import default_api
from deutschland.dwd.model.crowd_meldung import CROWDMeldung
from deutschland.dwd.model.error import Error
from deutschland.dwd.model.gemeinde_warnings import GemeindeWarnings
from deutschland.dwd.model.station_overview import StationOverview
from deutschland.dwd.model.warning_coast import WarningCoast
from deutschland.dwd.model.warning_nowcast import WarningNowcast
# Defining the host is optional and defaults to https://app-prod-ws.warnwetter.de/v30
# See configuration.py for a list of all supported configuration parameters.
configuration = dwd.Configuration(
    host = "https://app-prod-ws.warnwetter.de/v30"
)



# Enter a context with an instance of the API client
with dwd.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)
    
    try:
        # Alpen Wettervorhersage als Text
        api_response = api_instance.alpen_forecast_text_dwms_json_get()
        pprint(api_response)
    except dwd.ApiException as e:
        print("Exception when calling DefaultApi->alpen_forecast_text_dwms_json_get: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://app-prod-ws.warnwetter.de/v30*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DefaultApi* | [**alpen_forecast_text_dwms_json_get**](docs/DefaultApi.md#alpen_forecast_text_dwms_json_get) | **GET** /alpen_forecast_text_dwms.json | Alpen Wettervorhersage als Text
*DefaultApi* | [**crowd_meldungen_overview_v2_json_get**](docs/DefaultApi.md#crowd_meldungen_overview_v2_json_get) | **GET** /crowd_meldungen_overview_v2.json | DWD Crowdwettermeldungen
*DefaultApi* | [**gemeinde_warnings_v2_en_json_get**](docs/DefaultApi.md#gemeinde_warnings_v2_en_json_get) | **GET** /gemeinde_warnings_v2_en.json | Gemeinde Unwetterwarnungen
*DefaultApi* | [**sea_warning_text_json_get**](docs/DefaultApi.md#sea_warning_text_json_get) | **GET** /sea_warning_text.json | Hochsee Unwetterwarnungen als Text
*DefaultApi* | [**station_overview_extended_get**](docs/DefaultApi.md#station_overview_extended_get) | **GET** /stationOverviewExtended | Wetterstation Daten
*DefaultApi* | [**warnings_coast_en_json_get**](docs/DefaultApi.md#warnings_coast_en_json_get) | **GET** /warnings_coast_en.json | Küsten Unwetterwarnungen (englisch)
*DefaultApi* | [**warnings_coast_json_get**](docs/DefaultApi.md#warnings_coast_json_get) | **GET** /warnings_coast.json | Küsten Unwetterwarnungen (deutsch)
*DefaultApi* | [**warnings_lawine_json_get**](docs/DefaultApi.md#warnings_lawine_json_get) | **GET** /warnings_lawine.json | Alpen Wettervorhersage als Text
*DefaultApi* | [**warnings_nowcast_en_json_get**](docs/DefaultApi.md#warnings_nowcast_en_json_get) | **GET** /warnings_nowcast_en.json | Nowcast Warnungen (englisch)
*DefaultApi* | [**warnings_nowcast_json_get**](docs/DefaultApi.md#warnings_nowcast_json_get) | **GET** /warnings_nowcast.json | Nowcast Warnungen (deutsch)


## Documentation For Models

 - [CROWDMeldung](docs/CROWDMeldung.md)
 - [CROWDMeldungHighestSeverities](docs/CROWDMeldungHighestSeverities.md)
 - [CROWDMeldungMeldungen](docs/CROWDMeldungMeldungen.md)
 - [Error](docs/Error.md)
 - [GemeindeWarnings](docs/GemeindeWarnings.md)
 - [GemeindeWarningsBinnenSee](docs/GemeindeWarningsBinnenSee.md)
 - [GemeindeWarningsBinnenSee209901000](docs/GemeindeWarningsBinnenSee209901000.md)
 - [GemeindeWarningsWarnings](docs/GemeindeWarningsWarnings.md)
 - [StationOverview](docs/StationOverview.md)
 - [StationOverview10865](docs/StationOverview10865.md)
 - [StationOverview10865Days](docs/StationOverview10865Days.md)
 - [StationOverview10865Forecast1](docs/StationOverview10865Forecast1.md)
 - [StationOverview10865Forecast2](docs/StationOverview10865Forecast2.md)
 - [WarningCoast](docs/WarningCoast.md)
 - [WarningCoastWarnings](docs/WarningCoastWarnings.md)
 - [WarningCoastWarnings501000007](docs/WarningCoastWarnings501000007.md)
 - [WarningNowcast](docs/WarningNowcast.md)
 - [WarningNowcastRegions](docs/WarningNowcastRegions.md)
 - [WarningNowcastWarnings](docs/WarningNowcastWarnings.md)


## Documentation For Authorization

 All endpoints do not require authorization.

## Author

kontakt@bund.dev


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in dwd.apis and dwd.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from deutschland.dwd.api.default_api import DefaultApi`
- `from deutschland.dwd.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
from deutschland import dwd
from deutschland.dwd.apis import *
from deutschland.dwd.models import *
```
