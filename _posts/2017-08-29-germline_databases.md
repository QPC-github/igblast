---
layout: page
category: cook
title: "How to set up"
order: 0
---
##### Download IgBlast program 

You can get it from ftp://ftp.ncbi.nih.gov/blast/executables/igblast/release/LATEST

#### Make blast database for germline V, D, and J gene sequences.  
   
The NCBI mouse germline gene databases (i.e., mouse_gl_V, etc.) are supplied with igblastn program 
(see [https://www.ncbi.nlm.nih.gov/igblast/](https://www.ncbi.nlm.nih.gov/igblast/) about database details).
  
To search IMGT germline sequences, you need to download them from IMGT web site 
([http://www.imgt.org/IMGT_vquest/share/textes/](http://www.imgt.org/IMGT_vquest/share/textes/) ).  You need to download all V, D and J sequences for whatever 
organisms you are interested in.  Combine all V and all J sequences, respectively, into a separate file (i.e., 
one file for all V sequences and one file all for J sequences).  After you have downloaded the sequences, 
invoke our utility tool edit_imgt_file.pl (download from the release/ directory) to process the sequences (to change 
 the long IMGT definition lines to germline gene names only).  For example:

```
./edit_imgt_file.pl imgt_file > my_seq_file
```

Then you can use NCBI's makeblastdb tool to make the blast database from the output file.  For example:

```
makeblastdb -parse_seqids -dbtype nucl -in my_seq_file
```

Now you can use my_seq_file as blast database file for igblast.
