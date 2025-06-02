var subdate = $datapoint.***FIELD***;  
var present = Today();  
var dayssince = Floor(DateDiff(present, subdate, 'days'),0)+1;  
  
var subdateonly = Text($datapoint.***FIELD***, 'DD/MM/YYYY');  
  
return {  
&nbsp;&nbsp; attributes: {  
&nbsp;&nbsp;&nbsp;&nbsp; dayssince: dayssince,  
&nbsp;&nbsp;&nbsp;&nbsp; subdateonly: subdateonly,  
&nbsp;&nbsp;  }  
}
