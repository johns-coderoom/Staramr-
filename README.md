# Staramr-
staramr (*AMR) scans bacterial genome contigs against the ResFinder, PointFinder, and PlasmidFinder databases (used by the ResFinder webservice and other webservices offered by the Center for Genomic Epidemiology) and compiles a summary report of detected antimicrobial resistance genes. The star|* in staramr indicates that it can handle all of the ResFinder, PointFinder, and PlasmidFinder databases.

Note: The predicted phenotypes/drug resistances are for microbiological resistance and not clinical resistance. This is provided with support from the NARMS/CIPARS Molecular Working Group and is continually being improved. A small comparison between phenotype/drug resistance predictions produced by staramr and those available from NCBI can be found in the tutorial. We welcome any feedback or suggestions.

For example:

staramr search -o out --pointfinder-organism salmonella *.fasta
out/summary.tsv:

https://github.com/johns-coderoom/Staramr-/blob/main/output.docx
