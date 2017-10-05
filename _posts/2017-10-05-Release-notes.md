---
layout: page
category: rel
title: "Release notes"
order: 2
---

#### Sept 22, 2017

* Release 1.8.0.

* Re-engineered multi-threading mechanism which significantly shortens the processing time. Default t
o use 4 threads.

* Added ability to accept the SRA accession directly as query input.

* Lower the default nucleotide mismatch penalty values for finding D and J genes (from -4 to -2 and f
rom -3 to -2, respectively). This is to better accommodate moderately mutated sequences. 

#### April 19, 2017

* Release 1.7.0.

* Make nucleotide overlaps at VDJ junctions an option (-allow_vdj_overlap) and default is set to no o
verlap allowed.  Previous versions were hard-coded to allow nucleotide overlaps at VDJ junctions.
*Use alignment length instead of percent identity as tiebreaker for hits with identical blast scores
.
* Allow custom J gene mismatch penalty.
* Add CDR3 start and stop to sub-region table

#### Oct 26, 2016

* Release 1.6.1
* Added clonotype report
* Enabled multi-threading option -num_threads

#### April 25, 2016

* Release 1.5.0
* Added CDR3 annotation 
* Added option for extending at 5' side
* Default to IMGT region (was Kabat previously)

July 17, 2014

* Release 1.4.0
* Added capability to analyze monkey sequences.

#### February 19, 2014

* Release 1.3.0
* Better handling of non-Ig sequences
* Include makeblastdb binary with pre-compiled releases
