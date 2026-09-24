# OLAGUIR_assignment_1_genome_exploration
# Name: Olaguir, Junavhel Jane B.
# Activity Title: Basic Genome Structure and Sequence Exploration Using Galaxy
BIO 300 –A Cell and Molecular Biology Laboratory
# Species:_Anas flavirostris_genome assembly (JBCATY010000001.1)
# Objectives
To describe the structure of the Anas flavirostris genome assembly using basic statistics, sequence-length filtering, and a small-scale open reading frame (ORF) exploration, and to learn how to inspect and interpret an assembled genome.
# Tools Used in Galaxy
NCBI Genome/FTP
gfastats
Compute sequence length
Sort
Filter sequences by length
Filter sequences by ID from a tabular file
getorf
# Part 1 — Genome Download
Source: NCBI FTP
Species: Anas flavirostris
File: Anas flavirostris genomic FASTA file
Renamed in Galaxy to: **Anas_flavirostris_genome_original.fna.gz**
# Part 2 — Assembly Statistics
Tool: _gfastats_
Tool mode: Summary statistics generation
Report mode: Genome assembly statistics (--nstar-report)
Input file: 1: Anas_flavirostris_genome_original.fna.gz
Output renamed to: Anas_flavirostris_Assembly_Statistics_gfastats

The gfastats output was used to examine the basic characteristics of the Anas flavirostris genome assembly, including the total assembly size, number of assembled sequences, sequence-length distribution, GC content, and assembly-contiguity statistics.
# Part 3 — Sequence-Length Structure
Tool: Compute sequence length
Input file: 1: Anas_flavirostris_genome_original.fna.gz
Setting: “Strip fasta description from header?” = Yes
Output: Compute sequence length on dataset 1

The resulting sequence-length table was sorted using Galaxy's Sort tool, with column 2 sorted in descending order, to identify the five longest sequences in the genome assembly.
# Part 4 — Length-Filtering Experiment
Step 1: Filter sequences by length
Tool: Filter sequences by length
Input file: 1: Anas_flavirostris_genome_original.fna.gz
Parameter: Minimum length = 10,000 bp (10 kb)
Output renamed to: Anas_flavirostris_filtered_10kb

Sequences shorter than 10 kb were removed, leaving only sequences that were at least 10,000 bp long.

Step 2: Re-run assembly statistics
Tool: gfastats
Input file: Anas_flavirostris_filtered_10kb
Settings: Same settings used in Part 2
Output renamed to: Anas_flavirostris_Filtered_10kb_Assembly_Statistics_gfastats

The original and filtered assembly statistics were compared to determine the effect of removing short sequences on the overall structure and continuity of the genome assembly.

# Part 5 — Small ORF Exploration
Step 1: Filter the assigned sequence
Tool: Filter sequences by ID from a tabular file
Input file: 1: Anas_flavirostris_genome_original.fna.gz
Filter: ID list from the provided list
My assigned ID: [Insert assigned Anas flavirostris sequence ID]
Sequence length: [Insert length] bp
Output: Positive matches only
Output renamed to: Anas_flavirostris_genome_original.fna uncompressed with matched ID
Step 2: ORF identification
Tool: getorf
Input: Anas_flavirostris_genome_original.fna uncompressed with matched ID
Minimum nucleotide size of ORF to report: 300 bp
What to output: Translation of regions between STOP codons
All START codons to code for Methionine: Yes
Circular sequence: No
Output: Anas_flavirostris_getorf.fasta

The getorf analysis was performed to identify potential open reading frames within the selected genomic sequence. These predicted ORFs represent possible coding regions based on sequence characteristics, but they cannot be considered confirmed functional genes without additional evidence.

# Short Interpretation

The Anas flavirostris genome assembly was examined using a series of basic bioinformatics tools in Galaxy. The gfastats analysis provided an overview of the assembly structure, while sequence-length analysis showed the distribution of assembled sequences and allowed the longest sequences to be identified.

The 10-kb length-filtering experiment provided a simplified view of the assembly by removing sequences shorter than 10,000 bp. Comparing the original and filtered assembly statistics can demonstrate how short sequences contribute to the total assembly and how filtering affects assembly characteristics.

The small ORF exploration using getorf demonstrated how a selected genomic sequence can be examined for potential protein-coding regions. Although ORFs can indicate possible coding sequences, their presence alone does not confirm that they represent actual genes. Further evidence, such as genome annotation, sequence homology, transcript evidence, or protein-domain analysis, would be necessary for functional confirmation.
# Overall Conclusion

The activity demonstrated a basic workflow for exploring an assembled Anas flavirostris genome. Assembly statistics, sequence-length analysis, length filtering, and ORF prediction provided different perspectives on genome organization and sequence content. These analyses illustrate how Galaxy can be used to examine genome assemblies and generate preliminary information about their structural characteristics and potential coding regions.
