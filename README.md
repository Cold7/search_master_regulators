# search_master_regulators

search_master_regulators is a simple Python script that follows the rules of David & Rebay's work to determine the master regulators of a set of differentially expressed genes. First, it searches for TFs (Transcription Factors) that regulate these genes by selecting those TFs that are strongly connected. These will be candidates for master regulators, and three properties will be evaluated for each candidate: (1) it regulates another candidate, (2) it is regulated by another candidate, and (3) its molecular product interacts with another candidate. If these three rules are satisfied, then we define them as master regulators.

INSTALL

It can be installed via pip using the following command:
  pip install search_master_regulators
This may require superuser permissions for Linux distributions. Additionally, these users would need to execute it using pip3:
  pip3 install search_master_regulators
If you need to install it only for the current user (without superuser permissions), you would run:
  pip3 install --user search_master_regulators
Finally, this program can be executed from your command line

USAGE

search_master_regulators [-h] -g GENES -n NETWORK [-u UPSTREAM] -p PPI [-o OUTPUT]
options:
  -h, --help show help message
  -g GENES, --genes GENES
                        Path to a file (one-column format) with Differentially Expressed Genes.
  -n NETWORK, --network NETWORK
                        Path to the Gene Regulatory Network file. Available formats are GML or two-column (TF - Gene) as TSV or CSV. No header is mandatory.
  -u UPSTREAM, --upstream UPSTREAM
                        Number of upstream TFs of DE genes to be considered. Default: 1.
  -p PPI, --ppi PPI     Protein-Protein Interaction network file. Available formats are GML or two-column (TF - Gene) as TSV or CSV. No header is mandatory.
  -o OUTPUT, --output OUTPUT
                        Path for output files. If the path does not exist, it will be created. Default: /your-home/MRs_output.
