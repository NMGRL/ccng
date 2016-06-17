# Specification

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
"irradiation": {
 "steps": [{"power": 1.0, 
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
"detectors": {
 "H1": {
   "ic_factor": 1.0,
   "ic_factor_err": 0.0,
   "kind": "Faraday",
   "gain": 1.0,
   "resistance": 10e12},
 "CDD": {
   "ic_factor": 1.025,
   "ic_factor_err": 0.0 }},
"data": {
  "encoding": "base64",
  "format": ">ff",
  "isotopes": {
   "Ar40": {
     "detector": {"name": "H1"},
     "points": "123412d129caselasdc091rd1123...."},
   "Ar36":{
     "detector": {"name": "CDD"},
     "points": "123412d129caselasdc091rd1123...."}
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
irradiation:
  correction_factors: {Ca3937: 1.0, Ca3937Er: 0.001, K3739: 1.0, K3739Er: 0.001}
  flux: 0.0001
  fluxEr: 5.0e-05
  lambda_Ar37: 1
  lambda_Ar39: 1
  lambda_K: 5.463e-10
  lambda_KEr: 0
  steps:
  - {end: '2016-01-01 09:01', power: 1.0, start: '2016-01-01 01:01'}
metadata: {material: Sanidine, project: Bat, sample: FooBar001}
timestamp: 2016-01-02 01:01
```

