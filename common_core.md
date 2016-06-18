# Common Core
## CCNG json backend

```json
{
"analysis_identifier": "10000-01A",
"analysis_uuid": "3381a2ae-83d1-4af3-9a21-d412b2fd0fb5",
"timestamp": "2016-01-02 01:01",
"metadata": {
  "sample": "FooBar001",
  "material": "Sanidine",
  "project": "Bat"},
"detectors": {
 "H1": {
   "ic_factor": 1.0,
   "ic_factor_err": 0.0,
   "kind": "Faraday",
   "gain": 1.0,
   "resistance": 10e12},
 "CDD": {
   "ic_factor": 1.025,
   "ic_factor_err": 0.0,
   "kind": "ion_counter"}},
"data": {
  "encoding": "base64",
  "format": ">ff",
  "isotopes": {
   "Ar40": {
     "detector": {"name": "H1"},
     "points": "123412d129caselasdc091rd1123....",
     "fit": "linear",
     "filter_outliers": {"enabled": True, "iterations": 1, "std_devs": 2},
     "tzero_intercept": 1.0,
     "tzero_interceptEr": 0.001},
   "Ar36":{
     "detector": {"name": "CDD"},
     "points": "123412d129caselasdc091rd1123...."},
     "fit": "linear",
     "filter_outliers": {"enabled": True, "iterations": 1, "std_devs": 2},
     "tzero_intercept": 1.0,
     "tzero_interceptEr": 0.001}},
  "baselines": {
      "H1": {
          "points": "123412d129caselasdc091rd1123....",
          "fit": "linear",
          "filter_outliers": {"enabled": True, "iterations": 1, "std_devs": 2},
          "tzero_intercept": 1.0,
          "tzero_interceptEr": 0.001},
      "CDD": {
          "points": "123412d129caselasdc091rd1123....",
          "fit": "linear",
          "filter_outliers": {"enabled": True, "iterations": 1, "std_devs": 2},
          "tzero_intercept": 1.0,
          "tzero_interceptEr": 0.001}
      }
   }
}
```

## CCNG yaml backend

```yaml
analysis_identifier: 10000-01A
analysis_uuid: 3381a2ae-83d1-4af3-9a21-d412b2fd0fb5
data:
  encoding: base64
  format: '>ff'
  isotopes:
    Ar36:
      detector: {name: CDD}
      points: 123412d129caselasdc091rd1123....
    Ar40:
      detector: {name: H1}
      points: 123412d129caselasdc091rd1123....
detectors:
  CDD: {ic_factor: 1.025, ic_factor_err: 0.0}
  H1: {gain: 1.0, ic_factor: 1.0, ic_factor_err: 0.0, kind: Faraday, resistance: 10000000000000.0}
```
