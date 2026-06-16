<details>
<summary>Create "label style" tags for strings using a HTML table</summary>

```ruby
'<figure class="table" style="margin-bottom: 15px;">'+
'<table style="border-collapse:collapse;display:inline-table;" cellpadding="0" cellspacing="0">'+
'<tbody><tr>'+
'<td style="background-color:#F4C795;color:#1F3D34;border-radius:8px 2px 2px 8px;line-height:1;padding:8px 12px 8px 4px;">'+
'<span style="font-size:14px;">🞇   STRING</span></td>'+
'<tr><td style="height:4px;"></td></tr>'+
'</tr></tbody></table>'
```

</details>

<details>
<summary>Create a progress bar by using dynamic data for the 'width:' parameter</summary>

```ruby
'<div style="width: 100%; background-color:#F4F0E9; border-radius:4px;">'+
'<div style="width:' + FIELD/PERCENT + '%; background-color:#00A77B; color:white; text-align:center; border-radius:4px;">'+
FIELD/PERCENT + '%</div></div>'
```

</details>

<details>
<summary>Create a donut chart by using dynamic data for the 'background: conic-gradient' parameter and label </summary>

```ruby
'<div style="width: 65px;height: 65px;border-radius: 50%;background: conic-gradient(#00A77B 0% ' + FIELD/PERCENT + '%, #F4F0E9 ' + FIELD/PERCENT + '% 100%); display: inline-flex; align-items: center; justify-content: center;">'+
'<div style="width: 55px; height: 55px; border-radius: 50%; background: #ffffff; text-align: center; line-height: 60px; font-weight: bold; font-size:14px; color: #00A77B;">' + FIELD/PERCENT + '%</div>'
```

</details>
