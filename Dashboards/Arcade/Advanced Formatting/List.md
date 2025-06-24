<details>
<summary>Days since submission</summary>
  
```ruby
var subdate = $datapoint.FIELD;  
var present = Today();  
var dayssince = Floor(DateDiff(present, subdate, 'days'),0)+1;  
  
var subdateonly = Text($datapoint.FIELD, 'DD/MM/YYYY');  
  
return {  
    attributes: {  
      dayssince: dayssince,  
      subdateonly: subdateonly,  
      }  
}
```

</details>
