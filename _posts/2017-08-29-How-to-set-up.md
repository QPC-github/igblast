---
layout: page
category: cook
title: "How to set up"
order: 0
---
#### 1. Download IgBlast program and other required files

IgBlast program can be downloaded from ([https://ftp.ncbi.nih.gov/blast/executables/igblast/release/LATEST](ftp://ftp.ncbi.nih.gov/blast/executables/igblast/release/LATEST) ).

For versions prior to 1.13.0, you also need to download the entire directory of internal_data and optional_file from [https://ftp.ncbi.nih.gov/blast/executables/igblast/release/](ftp://ftp.ncbi.nih.gov/blast/executables/igblast/release/).  We strongly encourage you to get the latest version.

#### 2. Make blast database for germline V, D, and J gene sequences.  

IgBlast allows you to search any germline databases of your choice (using -germline_db_V, -germline_db_J and -germline_db_D options).

The NCBI mouse germline gene databases (i.e., mouse_gl_V, etc.) are supplied on our ftp site (see [https://www.ncbi.nlm.nih.gov/igblast/](https://www.ncbi.nlm.nih.gov/igblast/) about database details).
  
To search IMGT germline sequences, you need to download them from IMGT web site 
([http://www.imgt.org/vquest/refseqh.html#VQUEST](http://www.imgt.org/vquest/refseqh.html#VQUEST) ).  You need to download all V, D and J sequences for whatever organisms you are interested in.  Combine all V, all D and all J sequences, respectively, into separate files (i.e., one file for all V sequences, one for all D sequences and one file all for J sequences).  After you have downloaded the sequences, invoke our utility tool edit_imgt_file.pl (For versions prior to 1.13.0, you need to download it separately from the release/ directory) to process the sequences (i.e., to change the long IMGT definition lines to germline gene names only).  For example:

```
./edit_imgt_file.pl imgt_file > my_seq_file
```

Then you can use NCBI's makeblastdb tool (also packaged with IgBlast release) to make the blast database from the output file.  For example:

```
makeblastdb -parse_seqids -dbtype nucl -in my_seq_file
```

Now you can use my_seq_file as blast database file for IgBlast.

#### Other notes on setting up IgBlast 
The internal_data directory contains data internal to igblast program only and users should NEVER add, delete, move, copy or edit any files in this directory.  Igblastn program expects the internal_data directory under current directory (i.e., where you run igblast 
program) or a path pointed to by IGDATA environmental variable (avoid using space in your path name for 
Windows system). Note that this directory does NOT contain any germline gene databases you should search (see above 
for how you can obtain a germline gene database).

The optional_file directory contains files that indicate germline J gene coding frame start position (position is 0-based), the J gene type, and the CDR3 end position for each sequence in the germline J sequence database (Fields are tab-delimited).  The suppliled annotation information is only for NCBI or IMGT  germline gene sequence database (including gene names as well as the sequences).   If you search your own database and if it contains different sequences or sequence identifiers, then you need to edit the corresponding file accordingly (Enter -1 if the frame information is unknownor) or you won't get proper frame status or CDR3 information (other results will still be shown correctly).  You need to use -auxiliary_data option to specify your file. You can directly supply a path to this file or put it under a path pointed to by IGDATA environmental variable.
