<details>
<summary>Get exif data from image field</summary>
  
```ruby
pulldata("@exif", ${FIELD}, "GpsImgDirection")
```
```ruby
pulldata("@exif", ${FIELD}, "GpsLatitude")
```
```ruby
pulldata("@exif", ${FIELD}, "GpsLongitude")
```

</details>

<details>
<summary>getValue from feature layer (${Where_Calc} refers to first line)</summary>

```ruby
concat("ATTRIBUTE='",${FIELD},"'")
```
```ruby
pulldata("@layer", "getValue", "attributes.FIELD", "https://services6.arcgis.com/ID/arcgis/rest/services/LAYERNAME/FeatureServer/SUBLAYER#", ${Where_Calc})  
```

</details>
