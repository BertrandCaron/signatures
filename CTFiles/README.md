# CTFile Formats

* [https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf](https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf)

## New signatures

* dev/1 Structure-data file (SDF)\
BOF: three lines with up to 80 ASCII characters, then 34 characters, then the MOL file version number (V2000 or V3000): `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V'('2'|'3')'000'` 80 max offset\
EOF: one new line followed by four dollar signs: `(0A|0D|0D0A)'$$$$'` and possibly a certain number of new lines (16 max offset)