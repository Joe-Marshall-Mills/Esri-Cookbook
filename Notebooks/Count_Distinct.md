<details>
<summary>Import FeatureLayer</summary>
  
```ruby
from arcgis.features import FeatureLayer #Import module
service_url = "URL" #Provide URL of feature layer
feature_layer = FeatureLayer(service_url) #Use above URL to load the feature layer
```

</details>

<details>
<summary>Statistics</summary>
  
```ruby
out_statistics = [{"statisticType": "count", "onStatisticField": "FIELD", "outStatisticFieldName": "count"}] #Type of statistic, which field, name of output
```

</details>

<details>
<summary>Query</summary>
  
```ruby
query_results = feature_layer.query(out_statistics=out_statistics, group_by_fields_for_statistics="FIELD") #Query the feature layer using out_statistics
```

</details>

<details>
<summary>Loop</summary>
  
```ruby
for feature in query_results: #Loop through each feature using query_results
    site = feature.get_value('Site') or 'Unknown' #Print string in FIELD
    count = feature.get_value('count') or 0 #Print count based on FIELD
```

</details>
