# Common Core

The Common Core specification is defined by ```modules```, ```submodules```, ```attributes``` and ```values```.

Modules are the top level grouping of the specification. The Core specification is augmented using [Add-ons](/add_ons.md)

Submodules are nested modules within the top level modules. Submodules may be infinitely nested and we will refer to all modules not in the top level modules as submodules.

note. a module need not have a submodule.

Submodules and modules are collections of submodules and attribute: value pairs.

The backend and syntax using to implement this specification can vary, but json is the preferred implementation at this point.

Below is the specification and two examples in JSON and YAML
# Specification
optional values are indicated by square brackets [...]

default values are shown in parentheses (...)

### Modules
#### metadata
analysis_identifier
analysis_uuid
timestamp
institution
user
email
sample
material
project
igsn
#### detectors
##### detector
- ic_factor (1.0)
- ic_factorEr (0.0)
- [kind]
- [gain]
- [resistance]

#### data
- encoding
- format

##### Submodules
- isotopes
  - name
      - detector
      - points
      - fit
      - filter_outliers
        - enabled
        - iterations
        - std_devs    
      - tzero_intercept
      - tzero_interceptEr
- baselines
    - name
        - points
        - fit
        - filter_outliers
          - enabled
          - iterations
          - std_devs    
        - tzero_intercept
        - tzero_interceptEr

## CCNG json backend

```json
{
"metadata": {
  "analysis_identifier": "10000-01A",
  "analysis_uuid": "3381a2ae-83d1-4af3-9a21-d412b2fd0fb5",
  "timestamp": "2016-01-02 01:01",
  "institution": "NMGRL",
  "user": "Jake Ross",
  "email": "foo.bar@nmt.edu",
  "sample": "FooBar001",
  "material": "Sanidine",
  "project": "Bat",
  "igsn": "MRO3132412"},
"detectors": {
 "H1": {
   "ic_factor": 1.0,
   "ic_factorEr": 0.0,
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
     "detector": "H1",
     "points": "123412d129caselasdc091rd1123....",
     "fit": "linear",
     "filter_outliers": {"enabled": true, "iterations": 1, "std_devs": 2},
     "tzero_intercept": 1.0,
     "tzero_interceptEr": 0.001},
   "Ar36":{
     "detector": "CDD",
     "points": "123412d129caselasdc091rd1123....",
     "fit": "linear",
     "filter_outliers": {"enabled": true, "iterations": 1, "std_devs": 2},
     "tzero_intercept": 1.0,
     "tzero_interceptEr": 0.001}},
  "baselines": {
      "H1": {
          "points": "123412d129caselasdc091rd1123....",
          "fit": "linear",
          "filter_outliers": {"enabled": true, "iterations": 1, "std_devs": 2},
          "tzero_intercept": 1.0,
          "tzero_interceptEr": 0.001},
      "CDD": {
          "points": "123412d129caselasdc091rd1123....",
          "fit": "linear",
          "filter_outliers": {"enabled": true, "iterations": 1, "std_devs": 2},
          "tzero_intercept": 1.0,
          "tzero_interceptEr": 0.001}
      }
   }
}

```

## CCNG yaml backend

```yaml
data:
  baselines:
    CDD:
      filter_outliers: {enabled: true, iterations: 1, std_devs: 2}
      fit: linear
      points: 123412d129caselasdc091rd1123....
      tzero_intercept: 1.0
      tzero_interceptEr: 0.001
    H1:
      filter_outliers: {enabled: true, iterations: 1, std_devs: 2}
      fit: linear
      points: 123412d129caselasdc091rd1123....
      tzero_intercept: 1.0
      tzero_interceptEr: 0.001
  encoding: base64
  format: '>ff'
  isotopes:
    Ar36:
      detector: {name: CDD}
      filter_outliers: {enabled: true, iterations: 1, std_devs: 2}
      fit: linear
      points: 123412d129caselasdc091rd1123....
      tzero_intercept: 1.0
      tzero_interceptEr: 0.001
    Ar40:
      detector: {name: H1}
      filter_outliers: {enabled: true, iterations: 1, std_devs: 2}
      fit: linear
      points: 123412d129caselasdc091rd1123....
      tzero_intercept: 1.0
      tzero_interceptEr: 0.001
detectors:
  CDD: {ic_factor: 1.025, ic_factor_err: 0.0, kind: ion_counter}
  H1: {gain: 1.0, ic_factor: 1.0, ic_factor_err: 0.0, kind: Faraday, resistance: 10e12}
metadata: {analysis_identifier: 10000-01A, analysis_uuid: 3381a2ae-83d1-4af3-9a21-d412b2fd0fb5,
  email: foo.bar@nmt.edu, institution: NMGRL, material: Sanidine, project: Bat, sample: FooBar001,
  timestamp: '2016-01-02 01:01', user: Jake Ross}
```
