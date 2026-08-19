# CTFile Formats

* [https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf](https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf)

## New signatures

* dev/1 Structure-data file (SDF)\
BOF: `(0A|0D|0D0A){10}[30:39][30:39][30:39][30:39][30:39][30:39][30:39][30:39][30:39][30:39](32|33)(44|64)` 80 max offset\
EOF: `(0A|0D|0D0A)24242424` 2 max offset