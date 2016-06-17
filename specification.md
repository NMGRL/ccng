Specification
-------------

CCNG json backend
=================

```json
{
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

CCNG yaml backend
=================
```yaml
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

