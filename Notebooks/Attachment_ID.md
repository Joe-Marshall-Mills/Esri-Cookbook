<details>
<summary>Import FeatureLayer</summary>
 
```ruby
from arcgis.features import FeatureLayer #Import module
service_url = "URL" #Provide URL of feature layer
feature_layer = FeatureLayer(service_url) #Use above URL to load the feature layer
```

</details>

<details>
<summary>Query NULL Field</summary>
 
```ruby
# Query only features where Attachment_ID is NULL or empty
empty_oid_query = feature_layer(
    where="FIELD IS NULL OR FIELD = ''",
    return_ids_only=True
)

empty_oids = empty_oid_query.get('objectIds', [])

# Only proceed if there are any empty FIELD fields
if empty_oids:
    print(empty_oids)
```

</details>

<details>
<summary>Import Pandas</summary>
 
```ruby
from pandas import pandas
```

</details>

</details>

<details>
<summary>Pandas DataFrame</summary>
 
```ruby
data = [] #Create an empty database

for oid in empty_oids:
    atts = feature_layer_glan.attachments.get_list(oid) #Loop through each objectid and get their attachment ids

    if atts:
        for att in atts:
            if att.get('keywords') == 'Site_Image': #If the attachment starts with 'Site_Image' then retrieve the attachment id
                data.append({
                    "ObjectID": oid, #Put objectid into column
                    "Attachment_ID": att['id'] #Put attchment id into column
                })

df = pandas.DataFrame(data)

print(df)
```

</details>

<details>
<summary>Loop through DataFrame</summary>
 
```ruby
for row in range(len(df)): #Loop through each row in resulting DataFrame
    objectid = df["ObjectID"][row] #Refer to ObjectID above
    attid = df["Attachment_ID"][row] #Refer to Attachment_ID above
    
    feature_layer_glan.calculate( #Calculate field in feature_layer_glan
    where="ObjectID = '" + str(objectid) + "'", #Where Site matches Site in feature_layer_glan
    calc_expression={"field": "Attachment_ID", "value": attid}) #Add count from DataFrame based on where
```

</details>

