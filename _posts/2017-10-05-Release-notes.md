---
layout: page
category: rel
title: "Release notes"
order: 2
---

#### Mar 7, 2023
Release 1.21.0

*Added gaps to *_alignment_aa fields (such as sequence_alignment_aa) to reflect gaps in nucleotide sequence alignment.

*Added the new AIRR format field: sequence_aa.  This is direct translation (no gaps) of nucleotide sequence using the reading frame determined by nucleotide sequence alignment to its closet germline V gene.

*Added the new AIRR format field: d_frame.  This is the D gene frame that is in-frame with the J gene coding frame.  IgBLAST offers built-in IGHD gene frame support for mouse as defined by Ichihara Y et al (European Journal of Immunology Volume 19, Issue 10 p. 1849-1854).  Users can use their own custom D gene definition with IgBLAST according to their needs.

#### Oct 18, 2022
Release 1.20.0

*Added capability to use custom V gene FWR/CDR annotation

#### Jun 02, 2022
Release 1.19.0

*Added logic to handle the case where there is an unrearranged J gene downstream of the VDJ rearrangement. 

#### Dec 13, 2021
Release 1.18.0

*Added capability to report C genes for Ig sequences.

#### Feb 26, 2021
Release 1.17.1

*Fixed annotation errors for TCR J genes.

#### Oct 16, 2020
Release 1.17.0

*Added the V frame shift field to indicate if there is an internal frame shift in V gene translation frame (for example, nucleotide deletions/insertions found in pseudogenes or caused by somatic mutations).

*The definition for whether a sequence is productive or not has now been updated.  Previously, a sequence is considered to be productive if the V(D)J rearrangement frame is in-frame and no stop codon is found.  Now the definition for a productive sequence includes no internal frame shift in V gene, in addition to previous requirement of V(D)J rearrangement frame being in-frame and no stop codon.

#### Apr 17, 2020
Release 1.16.0

*Added ability to use custom organism.  

*Added ability to extend J gene alignment at 3' end.

*Added the AIRR complete_vdj field.

*Deleted parameters that are used for standard BLAST but not for IgBLAST.

#### Jan 21, 2020
Release 1.15.0

*Added support for the FWR4 annotation.

*The previous "-penalty" parameter was renamed as V_penalty to be consistent with other IgBLAST penalty options

*Restored constant internal BLAST search parameters for domain annotation (i.e., FWR/CDR) such that this process is not influenced by user parameters

*Corrected FWR/CDR annotations for certain mouse VK and rat VH germline genes.

#### Apr 29, 2019
* Release 1.14.0

* Making AIRR format more consistent with AIRR specs including changing undefined type (NON, N/A) to empty string, not appending "reversed" to seqid when query is in reversed orientation, using standard locus names such as IGH, TRB instead of traditional VH, VB etc.

* Loosening criteria to show CDR3 end by allowing the first FWR4 base to be missing.

* Bug fix: Restoring seqid for no result case in AIRR rearrangement format.  Printing IgBlast version number instead of Blast version number with -version option.

#### Mar 7, 2019
* Release 1.13.0
* Determine the V gene reading frame from the end of FWR3 region instead of end of V gene.  This is to allow proper determination of the
 frames for rearrangements that have insertions or deletions near the V gene end.

* Increase allowed distance between V gene end and J gene start to 225 bp to allow detection of ultra long D/N region.

* Package the edit_imgt_file.pl script, the internal_data and optional_files folders into the IgBlast release such that it is easy for u
ser to install.

#### Nov 26, 2018
* Release 1.12.0

* Increase allowed distance between V gene end and J gene start positions (from 90 bp to 150 bp) as well as between V gene end and D gene start positions (from 55 to 120 bp) to accommodate extremely long VDJ junctions found in some antibodies. 

#### Oct 25, 2018

* Release 1.11.0

* Change the 0-based coordinate system to 1-based coordinate system in AIRR format (with -outfmt 19 parameter) for sequence start positions per the new AIRR Rearrangement Schema ( http://docs.airr-community.org/en/latest/datarep/rearrangements.html ).


#### Aug 24, 2018

* Release 1.10.0

* Fix some processes not exiting under cpu full load condition

#### April 30, 2018

* Release 1.9.0

* Adding the AIRR rearrangement tabular format	

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

#### July 17, 2014

* Release 1.4.0
* Added capability to analyze monkey sequences.

#### February 19, 2014

* Release 1.3.0
* Better handling of non-Ig sequences
* Include makeblastdb binary with pre-compiled releases
