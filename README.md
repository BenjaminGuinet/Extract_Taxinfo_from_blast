Extract_Taxinfo_from_blast

This Python script uses the taxadb SQLite database to extract TaxID and taxonomic information associated with Accession IDs from BLAST, Diamond, or MMseqs2 output files.
Prerequisites

Before using this script, you need to download the taxadb database. You can find it here:
[🔗 taxadb GitHub Repository](https://github.com/HadrienG/taxadb)

Description

This script allows you to add taxonomic information to a BLAST, Diamond, or MMseqs2 output file. It reads the input file, extracts Accession IDs, and appends the corresponding TaxID and taxonomic information to the output file.
Usage
Command-Line Arguments
bash
Copy
```
usage: Add_taxid_info.py [-h] [-b BLAST] [-o OUT] [-d TAXADB_SQLITE_FILE]
                         [-blst BLAST_TYPE] [-del OUTPUT_DELIMITATOR]

Allows you to add taxonomic information to a blast, diamond, or mmseqs2 output file.

optional arguments:
  -h, --help            Show this help message and exit.
  -b BLAST, --blast BLAST
                        The blast file in tabular format.
  -o OUT, --out OUT     The output path (with the new filename) where to create the output file.
  -d TAXADB_SQLITE_FILE, --taxadb_sqlite_file TAXADB_SQLITE_FILE
                        The directory where the SQLite database is located.
  -blst BLAST_TYPE, --blast_type BLAST_TYPE
                        The type of blast: supports 'blast', 'diamond', and 'mmseqs2' analysis.
  -del OUTPUT_DELIMITATOR, --Output_delimitator OUTPUT_DELIMITATOR
                        The desired output delimiter. Default is ';'. Use 'tab' for tabular format.
```
Example Usage

    For MMseqs2 output:
    bash
    Copy

    python3 add_taxid_info.py -blst Mmseqs2 \
    -b /path/to/Matches_VLPs_prot_vs_NR_mmseqs2_all.m8 \
    -d /path/to/taxadb_new.sqlite \
    -o /path/to/Matches_VLPs_prot_vs_NR_mmseqs2_all_taxid.m8

    For testing with a sample file:
    bash
    Copy

    python3 python_test.py -blst Mmseqs2 \
    -b tab_test \
    -d /path/to/taxadb_new.sqlite \
    -o tab_test_taxid.m8

Output

The script generates a new file with the same format as the input file, but with additional columns for TaxID and taxonomic information.
Notes

    Ensure that the taxadb SQLite database is correctly downloaded and accessible.

    The script supports BLAST, Diamond, and MMseqs2 output formats.

    By default, the output delimiter is ;. Use the -del tab option for tab-delimited output.

License

This project is open-source and available under the MIT License.

Feel free to contribute or report issues! 🚀
