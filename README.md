CIDR Merge
==========

Merge and de-dupe overlapping or adjacent IP ranges. Invalid CIDRs cause
cidrmerge to print an error and halt.

```
$ ./cidrmerge -?
Usage: ./cidrmerge < cidr_list [cidr_list...] > output
$ 
$ cat test
123.10.0.0/16
123.10.125.0/24
123.11.12.0/24
123.10.121.16
123.10.125.0/24
123.11.12.221/32
$ 
$ ./cidrmerge < test
123.10.0.0/16
123.11.12.0/24
$ 
$ echo 10.1.1.1/24 | ./cidrmerge 
ERROR: [10.1.1.1/24] Invalid starting address for /24. Try 10.1.1.0 or 10.1.2.0
$ 
```
