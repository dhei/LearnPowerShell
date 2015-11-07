### PowerShell Basics

##### Comments
```PowerShell
# This is a single-line comment

<# This is
a multi-line PowerShell
comment #>
```

##### Strings
```PowerShell
"This is a string, this $variable is evaluated as $(100+200)"

'This is a string, this $variable is not evaluated as $(100+200)'

@"
A double-quoted here-string can contain anything include carriage returns and quotes.
Expression are evaluated: $(100+200)
Note the end marker of the here-string must be at the beginning of a aline!
"@

@'
A single-quoted here-string does not evaluate expressions:
$(100+200)
'@
```

##### Operators
###### Comparison operators (case-insensitive)
```PowerShell
"abc" -eq "abc"
"abc" -ne "bca"
"bca" -gt "abc"
"abc" -ge "abc"
"abc" -lt "bca"
"abc" -le "abc"
"abc123" -replace "123", "def"
'a','b','c' -contains 'a'
1,2,3,4,5 -notcontains 6
'a' -in 'a','b','c'
6 -notin 1,2,3,4,5
```

###### Wildcard and regular expression comparison (case-insensitive)
```PowerShell
"abcde" -like "*cde"
"abcde" -notlike "*bcd"
"abcde" -match "abc"
"abcde" -notmatch "123"
"ab,cd,e" -split ","
"ab","cd","e" -join ","
```

###### Case sensitive comparison
```PowerShell
"abc" -cne "ABC"
"abc123" -creplace "abc", "ABC"
```

###### Logical and bitwise operators
```PowerShell
$true -and $true
$true -or $false
-not $false
(4 -band 3) -eq 0
(4 -bor 3) -eq 7
(-bnot 4) -eq -5
```

###### Type operators
```PowerShell
123 -is [int]
123 -isnot [string]
123 -as [string] # no error when conversion fails
[datetime]$date="11/7/2015" # cast operator
```

##### Arrays
```PowerShell
$emptyArray = @()

$arrayOfOneElement = ,"abc"
$arrayOfOneElement = @("abc")

$intArray = 1..10
$intArray[0..9]
$intArray[-1] # last element of the array
$intArray[-3..-1] # last three elements of the array
$intArray[($intArray.length-1)..0] # reverse the array

$twoDimensionArray = 1,(2,3),(4,5,6),(7,8,9,10)
```

##### Hash table
```PowerShell
$emptyHashtable = @{}

$hashtable = @{foo="value1"; bar=123}
$hashtable.newKey = "value2" # add a newKey with value2
$hashtable.foo -eq "value1"
$hashtable["bar"] -eq 123

$hashtable | ConvertTo-Json
<# Json output:
{
    "newKey":  "value2",
    "bar":  123,
    "foo":  "value1"
}
#>
```
