<details>
<summary>Not minus and less than or equal to FIELD</summary>
 
```ruby
.>=0 and .<=${FIELD}
```

</details>

<details>
<summary>Limit options selected</summary>
 
```ruby
count-selected(${FIELD})=1
```

</details>

<details>
<summary>No whitespace at start or end of string</summary>
 
```ruby
not(regex(., '^\s+|\s+$'))
```

</details>
