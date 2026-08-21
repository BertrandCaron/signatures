# CTFile Formats

* [https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf](https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf)

## New signatures

* dev/1 Structure-data file (SDF)\
BOF: three lines with up to 80 ASCII characters, then a fourth line with the MOL file version number (V2000 or V3000) on column 34: `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V'('2'|'3')'000'` 80 max offset\
EOF: one new line followed by four dollar signs: `(0A|0D|0D0A)'$$$$'` and possibly a certain number of new lines (16 max offset)

* dev/2 V2000 MOL file\
BOF: three lines with up to 80 ASCII characters, then a fourth line with the format version number V2000 on column 34: `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V2000'` 80 max offset\
EOF: one new line followed by "M", two spaces, and "END": `(0A|0D|0D0A)'M  END'` and possibly a certain number of new lines (16 max offset)

* dev/3 V3000 MOL file\
BOF: three lines with up to 80 ASCII characters, then a fourth line with the format version number V3000 on column 34: `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V3000'` 80 max offset\
EOF: one new line followed by "M", two spaces, and "END": `(0A|0D|0D0A)'M  END'` and possibly a certain number of new lines (16 max offset)