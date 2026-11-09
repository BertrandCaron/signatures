# CTFile Formats

* [https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf](https://discover.3ds.com/sites/default/files/2020-08/biovia_ctfileformats_2020.pdf)

## New signatures

* dev/1 Structure-data file (SDF)\
  The signature uses the '$$$$' delimiter that must be present between records and at the end of the file (possibly followed by several new lines), and adds to that the version of the first MOL file (V2000 or V3000). Analysis of sample files shows that all header elements can be absent, even the timestamp and the geometry ("2D" or "3D"), so they weren't used as patterns. The MOL file version was found to be absent in one sample file, but it seems better to keep it in the signature to reinforce it. In one other case, the comment line was absent, but this could cause errors in rendering the file, so I kept it as a mandatory element. \
BOF: three lines with up to 80 ASCII characters, then a fourth line with the MOL file version number (V2000 or V3000) on column 34: `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V'('2'|'3')'000'` 80 max offset\
EOF: one new line followed by four dollar signs: `(0A|0D|0D0A)'$$$$'` and possibly a certain number of new lines (16 max offset)

* dev/2 V2000 MOL file\
BOF: three lines with up to 80 ASCII characters, then a fourth line with the format version number V2000 on column 34: `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V2000'` 80 max offset\
EOF: one new line followed by "M", one to three bytes, and "END": `(0A|0D|0D0A)'M{1-3}END'` and possibly a certain number of new lines (16 max offset)

* dev/3 V3000 MOL file\
BOF: three lines with up to 80 ASCII characters, then a fourth line with the format version number V3000 on column 34: `(0A|0D|0D0A){0-80}(0A|0D|0D0A){0-80}(0A|0D|0D0A){34}'V3000'` 80 max offset\
EOF: one new line followed by "M", one to three bytes, and "END": `(0A|0D|0D0A)'M{1-3}END'` and possibly a certain number of new lines (16 max offset)
