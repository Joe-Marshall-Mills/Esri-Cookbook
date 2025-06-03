<details>
<summary>Get exif data from image field</summary>
  
```
pulldata("@exif", ${FIELD}, "GpsImgDirection")
```
```
pulldata("@exif", ${FIELD}, "GpsLatitude")
```
```
pulldata("@exif", ${FIELD}, "GpsLongitude")
```

</details>

<details>
<summary>getValue from feature layer (${Where_Calc} refers to first example)</summary>

```
concat("ATTRIBUTE='",${FIELD},"'")
```
```
pulldata("@layer", "getValue", "attributes.FIELD", "https://services6.arcgis.com/ID/arcgis/rest/services/LAYERNAME/FeatureServer/SUBLAYER#", ${Where_Calc})  
```
```
pulldata("@exif", ${FIELD}, "GpsLatitude")
```
```
pulldata("@exif", ${FIELD}, "GpsLongitude")
```

</details>
