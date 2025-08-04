<details>
<summary>Most counted</summary>
  
```ruby
// Documentation: https://arcg.is/18ejKn3

function getFilteredFeatureSet(ds) {
  var result = ds.layer;
  var queryParams = ds.queryParams;

  if (!IsEmpty(queryParams.where)) {
    result = Filter(result, queryParams.where);
  }

  if (!IsEmpty(queryParams.geometry)) {
    result = Intersects(result, queryParams.geometry);
  }

  return result;
}


// July-Nov
// The filteredFeatureSet1 has already been filtered using spatial filters and attribute filters.
var filteredFeatureSet1 = getFilteredFeatureSet($dataSources["dataSource_1-0-dataView_2"]);
// selectedFeatures1 is the selection view of data source.
// var selectedFeatures1 = $dataSources["dataSource_1-0-dataView_2"].selectedFeatures;

//Sum of each FIELD
var NAME = Sum(filteredFeatureSet1, 'FIELD')
var NAME = Sum(filteredFeatureSet1, 'FIELD')
var NAME = Sum(filteredFeatureSet1, 'FIELD')
var NAME = Sum(filteredFeatureSet1, 'FIELD')
var NAME = Sum(filteredFeatureSet1, 'FIELD')
var NAME = Sum(filteredFeatureSet1, 'FIELD')
var NAME = Sum(filteredFeatureSet1, 'FIELD')

//Create FeatureSet
var d = {
  fields: [
    { alias: 'ALIAS', name: 'FIELD', type: 'esriFieldTypeString' },
    { alias: 'ALIAS', name: 'FIELD', type: 'esriFieldTypeInteger' },
    { alias: 'ALIAS', name: 'FIELD', type: 'esriFieldTypeString' }
  ],
  geometryType: '',  //Leave blank if no geometry
  spatialReference: { wkid: 4326 },  //Still needed even without geometry
  features: [
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
    {attributes: { Item: 'LABEL', Count: NAME, Size: 'Medium' }},
  ]
};

//Wrap it in FeatureSet()
var fs = FeatureSet(d);

//Use FeatureSet functions like OrderBy()!
var sorted = OrderBy(fs, 'Count DESC');
var top = First(sorted);
      
return {
  value: top.Item + ' (' + Text(top.Count/0.067, '#,###') + ')',
  text: {
    // size: 14,
    // color: 'rgb(0, 0, 255)',
    // bold: true,
    // italic: false,
    // underline: false,
    // strike: false
  },
};
```

</details>
