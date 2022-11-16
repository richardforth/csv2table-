# csv2table++
csv2table, but written in C++

Has a number of advantages and disadvantages over the original csv2table that was written in C:

## Advantages:
 - No external dependencies required
 - 100% C++ code
 
 ## Disadvantages
  - Currently doesnt work with stdin, only accepts a single filename argument

## Example output
```bash
cat fakeipswap.csv
Old,Old netmask,New,New netmask
192.168.1.1,255.255.255.0,10.0.1.1,255.255.0.0
192.168.1.2,255.255.255.0,10.0.1.2,255.255.0.0
192.168.1.3,255.255.255.0,10.0.1.3,255.255.0.0
192.168.1.4,255.255.255.0,10.0.1.4,255.255.0.0
192.168.1.5,255.255.255.0,10.0.1.5,255.255.0.0




$ csv2table++ fakeipswap.csv
Argument Count: 2
Argument0: csv2table++
Argument1: fakeipswap.csv
Elements in result array: 24
Max Columns: 4
Max Rows: 6
Max Cell Size: 15
+----------------+----------------+----------------+----------------+
|            Old |    Old netmask |            New |    New netmask |
+----------------+----------------+----------------+----------------+
|    192.168.1.1 |  255.255.255.0 |       10.0.1.1 |    255.255.0.0 |
|    192.168.1.2 |  255.255.255.0 |       10.0.1.2 |    255.255.0.0 |
|    192.168.1.3 |  255.255.255.0 |       10.0.1.3 |    255.255.0.0 |
|    192.168.1.4 |  255.255.255.0 |       10.0.1.4 |    255.255.0.0 |
|    192.168.1.5 |  255.255.255.0 |       10.0.1.5 |    255.255.0.0 |
+----------------+----------------+----------------+----------------+
```

# TODO List:
 - Work on accepting STDIN
