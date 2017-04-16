Install feather:
- https://github.com/wesm/feather/tree/master/python

Convert a row-major tsv file to many tsv-split-cols files:
- Straightforward to make this work with csv, but it's ~5x slower, so I didn't
```sh
cat ebd_US-CA_relFeb-2017.txt | pv -terbl -s34m | ./tsv-split-cols ebd_US-CA_relFeb-2017.txt.tsv-split-cols/
```

Convert the tsv-split-cols files into one column-major feather file:
```sh
./feather-from-tsv-split-cols ebd_US-CA_relFeb-2017.txt.tsv-split-cols/ ebd_US-CA_relFeb-2017.feather
```

Use feather:
- https://github.com/wesm/feather
- https://blog.rstudio.org/2016/03/29/feather/
- http://blog.cloudera.com/blog/2016/02/introducing-apache-arrow-a-fast-interoperable-in-memory-columnar-data-structure-standard/
