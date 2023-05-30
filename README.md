# Powershell Tips and Tricks

## Useful command

### Telnet alternative

```
Test-NetConnection -ComputerName [dns or ip address] -Port [port number]
```

### nslookup alternative

- Standard command

```
Resolve-DnsName -Name [dns name]
```

```
# Output
Name                                           Type   TTL   Section    IPAddress
----                                           ----   ---   -------    ---------
[dns name]                                      A      206   Answer    [IP address]
```

- Understand the properties and methods list

```
# Display properties and methods
Resolve-DnsName -Name [dns name] | Get-Member
```

```
# Output
Name         MemberType    Definition
----         ----------    ----------
Address      AliasProperty Address = IP4Address
IPAddress    AliasProperty IPAddress = IP4Address
QueryType    AliasProperty QueryType = Type
Equals       Method        bool Equals(System.Object obj)
GetHashCode  Method        int GetHashCode()
GetType      Method        type GetType()
ToString     Method        string ToString()
CharacterSet Property      Microsoft.DnsClient.Commands.DNSCharset CharacterSet {get;set;}
DataLength   Property      uint16 DataLength {get;set;}
IP4Address   Property      string IP4Address {get;set;}
Name         Property      string Name {get;set;}
Section      Property      Microsoft.DnsClient.Commands.DNSSection Section {get;set;}
TTL          Property      uint32 TTL {get;set;}
Type         Property      Microsoft.DnsClient.Commands.RecordType Type {get;set;}
```

- Only IP address command

```
# This command can be stored in a variable
(Resolve-DnsName -Name [dns name]).IPAddress
```

## Array

### Create a list

```
# Create a new empty array
$new_empty_array = @()

# Create an array
$new_array = @(1, "a", "hello")
# or
$new_array = 1, "a", "hello"
```

### Operation on a list

```
# Add an element in a list
$new_array += 367

# Number of elememnts in a list
$new_array.Count
# or
$new_array.Length

# Store an element from a list into a vaariable
$my_var = $new_array[3]

# Delete a list
$new_array = $null
```

## Loops

### Looping on a list

```
foreach($i in "a","b","c") {
    Write-Host "${i}"
}
```

## Functions tips

```

```
