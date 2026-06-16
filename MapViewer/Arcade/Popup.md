<details>
<summary>Attachment URL</summary>

```ruby
var P1 = "https://services6.arcgis.com/ITEMID/arcgis/rest/services/LAYERNAME/FeatureServer/0/"  
var ObjectID = $feature.FIELD 
var P2 = "/attachments/"  
var AttachID = $feature.FIELD
  
P1 + ObjectID + P2 + AttachID
```

</details>

<details>
<summary>Open Survey123 mobile and fill question "Site"</summary>

```ruby
arcgis-survey123://?itemID=d873e788e4514002ab759254ab78631b&field:Site={Site}
```

</details>

