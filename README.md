CIDR Merge
==========

Merge and de-dupe overlapping or adjacent IP ranges. Invalid CIDRs in
the input cause cidrmerge to print an error and halt.

Please report any use-cases where cidrmerge fails. Thank you!

```
$ ./cidrmerge -?
Usage: cat cidr_list [cidr_list...] | ./cidrmerge > output
$ 
$ cat test
123.11.13.0/24
123.10.0.0/16
123.10.125.0/24
123.11.12.0/24
123.10.121.16
123.10.125.0/24
123.11.12.221/32
$ 
$ cat test | ./cidrmerge 
123.10.0.0/16
123.11.12.0/23
$ 
$ echo 10.1.1.1/24 | ./cidrmerge 
ERROR: [10.1.1.1/24] Invalid starting address for /24. Try 10.1.1.0 or 10.1.2.0
$ 
```

