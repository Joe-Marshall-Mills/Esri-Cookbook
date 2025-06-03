<details>
<summary>Using an if statment to either pulldata or use override field</summary>
  
```
if(string-length(${FIELD})>0, ${FIELD}, pulldata("@layer", "getValue", "attributes.ATTRIBUTE", "https://services6.arcgis.com/ID/arcgis/rest/services/LAYERNAME/FeatureServer/SUBLAYER#", ${Where_Calc}))
```
[see pulldata.md](pulldata.md) for more info
