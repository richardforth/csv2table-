# csv2table++
csv2table, but written in C++

Has a number of advantages over [the original csv2table that was written in C](https://github.com/richardforth/csv2table):

## Advantages:
 - No external dependencies required
 - 100% C++ code
 
## Disadvantage (now solved)

Could only get the C++ version to take arguments but not STDIN, this has now ben solved. 
 
# Installation

```bash
$ c++ csv2table++.cpp -o csv2table++
```
Should work cross-platform (Windows, Linux, MacOS) 

## Example output
```bash
cat fakeipswap.csv
Old,Old netmask,New,New netmask
192.168.1.1,255.255.255.0,10.0.1.1,255.255.0.0
192.168.1.2,255.255.255.0,10.0.1.2,255.255.0.0
192.168.1.3,255.255.255.0,10.0.1.3,255.255.0.0
192.168.1.4,255.255.255.0,10.0.1.4,255.255.0.0
192.168.1.5,255.255.255.0,10.0.1.5,255.255.0.0


$ csv2table++ <<< $(echo -e "1,2,3,4,5\n6,7,8,9,0")
Main Function.
Has Exactly One Argument? false
process_stdin() called
Empty line ignored.
make_table() called.
Result array size: 10
Max Cols: 5
Max Rows: 3
Max Cell Size: 3
+----+----+----+----+----+
|  1 |  2 |  3 |  4 |  5 |
+----+----+----+----+----+
|  6 |  7 |  8 |  9 |  0 |
+----+----+----+----+----+



$ csv2table++ fakeipswap.csv
Main Function.
Has Exactly One Argument? true
process_arg() called on fakeipswap.csv
Empty line ignored.
make_table() called.
Result array size: 24
Max Cols: 4
Max Rows: 7
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


$  cat fakeipswap.csv | csv2table++
Main Function.
Has Exactly One Argument? false
process_stdin() called
Empty line ignored.
make_table() called.
Result array size: 24
Max Cols: 4
Max Rows: 7
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
 - Work on adhering to DRY principles.
