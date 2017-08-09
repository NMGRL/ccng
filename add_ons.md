# Add-Ons


## Ar-Ar

### TZeroResult
```json
"tzero_results": {
     "Ar40": {"value": 10, "error": 1,
             "fit": "linear", 
             
             "filter_outliers": {
                      "enabled": true,
                      "iterations": 1,
                      "std_devs": 2},
             "baseline": {"value": 1, "error": 0.1,
                          "fit": "linear", 
                          "filter_outliers": {
                             "enabled": true,
                             "iterations": 1,
                             "std_devs": 2}}
}
```
### Irradiation
 ```json
"irradiation": {
 "chronology": [{"power": 1.0,
            "start": "2016-01-01 01:01",
            "end": "2016-01-01 09:01"}],
  "correction_factors": {"K3739": 1.0,
                         "K3739Er": 0.001,
                         "Ca3937": 1.0,
                         "Ca3937Er": 0.001,},
  "flux": 0.0001,
  "fluxEr": 0.00005,
  "lambda_K": 5.463e-10,
  "lambda_KEr": 0,
  "lambda_Ar39": 1,
  "lambda_Ar37": 1},
  ```

### Results
```json
"results": {
    "age": 1.0,
    "ageEr": 0.001,
    "kca": 20.01,
    "kcl": 10001.04,
    "rad40": 98.01,
}
```

## Geolocation
```json
"geolocation": {"latitude": 102.234,
"longitude": 10.212,
"altitude": 431,
"altitude_units": "m",
}
```