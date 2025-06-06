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
    LABEL = feature.get_value('FIELD') or 'Unknown' #Print string in field LABEL 
    count = feature.get_value('count') or 0 #Print count based on FIELD
```

</details>

<details>
<summary>Pandas module</summary>
  
```ruby
from pandas import pandas #Import module
```

</details>

<details>
<summary>Pandas DataFrame</summary>
  
```ruby
data = {
  "LABEL": [], #Create empty list for LABEL
  "Count": [] #Create empty list for Count
} 

for feature in query_results: #Loop thorugh each feature using query_results
    data["LABEL"].append(feature.get_value('FIELD') or 'Unknown') #Add resulting FIELD to list
    data["Count"].append(feature.get_value('count') or 0) #Add resulting counts to list

df = pandas.DataFrame(data) #Create DataFrame

print(df)
```

</details>

<details>
<summary>Import (2nd) FeatureLayer</summary>
  
```ruby
from arcgis.features import FeatureLayer #Import module
service_url = "URL" #Provide URL of feature layer
feature_layer = FeatureLayer(service_url) #Use above URL to load the feature layer
```

</details>

<details>
<summary>Calculate</summary>
  
```ruby
for row in range(len(df)): #Loop through each row in resulting DataFrame
    LABEL = df["LABEL"][row] #Add relevant Site to row
    count = df["Count"][row] #Add relevant count to row
    
    feature_layer.calculate( #Calculate field in feature_layer_ss
    where="FIELD = '" + str(LABEL) + "'", #Where LABEL matches FIELD in feature_layer
    calc_expression={"field": "FIELD", "value": count}) #Add count from DataFrame based on where
```

</details>

