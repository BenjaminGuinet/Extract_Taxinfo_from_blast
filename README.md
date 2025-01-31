# Extract_Taxinfo_from_blast
This python script uses taxadb sqlite database to extract TaxID and Taxinfo associated to Accession ids. '

First you need to download the taxadb from https://github.com/HadrienG/taxadb 


-----------------------------------------------------------------------------------

                        Add taxonomy informations into blast tab.

-----------------------------------------------------------------------------------

usage: Add_taxid_info.py [-h] [-b BLAST] [-o OUT] [-d TAXADB_SQLITE_FILE]
                         [-blst BLAST_TYPE] [-del OUTPUT_DELIMITATOR]

Allows you to add taxonomic information to a blast, diamond or mmseqs2 output
file.

optional arguments:
  -h, --help            show this help message and exit
  -b BLAST, --blast BLAST
                        The blast file in tabular format
  -o OUT, --out OUT     The ouptut path (with the new filename) where to
                        create the oufile
  -d TAXADB_SQLITE_FILE, --taxadb_sqlite_file TAXADB_SQLITE_FILE
                        The directory where is located the sqlite database
  -blst BLAST_TYPE, --blast_type BLAST_TYPE
                        The type of blast : support blast (blast), diamond
                        (diamond) and mmseqs2 (mmseqs2) analysis
  -del OUTPUT_DELIMITATOR, --Output_delimitator OUTPUT_DELIMITATOR
                        The desired output delimitator, by default : ';' but
                        you cand add tabular format with the option : 'tab'

Ex usage python3 add_taxid_info.py -blst Mmseqs2  -b /beegfs/data/bguinet/these/Horizon_project_part/tBLASTn_VLPs/Matches_VLPs_prot_vs_NR_mmseqs2_all.m8 -d /beegfs/data/bguinet/taxadb/taxadb_new.sqlite -o /beegfs/data/bguinet/these/Horizon_project_part/tBLASTn_VLPs/Matches_VLPs_prot_vs_NR_mmseqs2_all_taxid.m8 
python3 python_test.py -blst Mmseqs2  -b tab_test -d /beegfs/data/bguinet/taxadb/taxadb_new.sqlite -o tab_test_taxid.m8 




