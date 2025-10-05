# Staramr-
staramr (*AMR) scans bacterial genome contigs against the ResFinder, PointFinder, and PlasmidFinder databases (used by the ResFinder webservice and other webservices offered by the Center for Genomic Epidemiology) and compiles a summary report of detected antimicrobial resistance genes. The star|* in staramr indicates that it can handle all of the ResFinder, PointFinder, and PlasmidFinder databases.

Note: The predicted phenotypes/drug resistances are for microbiological resistance and not clinical resistance. This is provided with support from the NARMS/CIPARS Molecular Working Group and is continually being improved. A small comparison between phenotype/drug resistance predictions produced by staramr and those available from NCBI can be found in the tutorial. We welcome any feedback or suggestions.

For example:

staramr search -o out --pointfinder-organism salmonella *.fasta
out/summary.tsv:

Isolate ID	Quality Module	Genotype	Predicted Phenotype	CGE Predicted Phenotype	Plasmid	Scheme	Sequence Type	Genome Length	N50 value	Number of Contigs Greater Than Or Equal To 300 bp	Quality Module Feedback
SRR1952908	Passed	aadA1, aadA2, blaTEM-57, cmlA1, gyrA (S83Y), sul3, tet(A)	streptomycin, ampicillin, chloramphenicol, ciprofloxacin I/R, nalidixic acid, sulfisoxazole, tetracycline	Spectinomycin, Streptomycin, Amoxicillin, Ampicillin, Cephalothin, Piperacillin, Ticarcillin, Chloramphenicol, Nalidixic acid, Ciprofloxacin, Sulfamethoxazole, Doxycycline, Tetracycline	ColpVC, IncFIB(S), IncFII(S), IncI1-I(Alpha)	senterica_achtman_2	11	4785500	250423	41	
SRR1952926	Passed	blaTEM-57, gyrA (S83Y), tet(A)	ampicillin, ciprofloxacin I/R, nalidixic acid, tetracycline	Amoxicillin, Ampicillin, Cephalothin, Piperacillin, Ticarcillin, Nalidixic acid, Ciprofloxacin, Doxycycline, Tetracycline	ColpVC, IncFIB(S), IncFII(S), IncI1-I(Alpha)	senterica_achtman_2	11	4785451	228311	40	
out/detailed_summary.tsv:

Isolate ID	Data	Data Type	Predicted Phenotype	CGE Predicted Phenotype	%Identity	%Overlap	HSP Length/Total Length	Contig	Start	End	Accession
SRR1952908	ST11 (senterica_achtman_2)	MLST									
SRR1952908	ColpVC	Plasmid			98.96	100.0	193/193	contig00038	1618	1426	JX133088
SRR1952908	aadA1	Resistance	streptomycin	Spectinomycin, Streptomycin	100.0	100.0	792/792	contig00030	5355	4564	JQ414041
out/resfinder.tsv:

Isolate ID	Gene	Predicted Phenotype	CGE Predicted Phenotype	%Identity	%Overlap	HSP Length/Total Length	Contig	Start	End	Accession	Sequence	CGE Notes
SRR1952908	sul3	sulfisoxazole	Sulfamethoxazole	100.00	100.00	792/792	contig00030	2091	2882	AJ459418	ATGA[...]	
SRR1952908	tet(A)	tetracycline	Doxycycline, Tetracycline	99.92	97.80	1247/1275	contig00032	1476	2722	AF534183	ATGT[...]	
out/pointfinder.tsv:

Isolate ID	Gene	Predicted Phenotype	CGE Predicted Phenotype	Type	Position	Mutation	%Identity	%Overlap	HSP Length/Total Length	Contig	Start	End	Pointfinder Position	CGE Notes	CGE Required Mutation	CGE Mechanism	CGE PMID
SRR1952908	gyrA (S83Y)	ciprofloxacin I/R, nalidixic acid	Nalidixic acid,Ciprofloxacin	codon	83	TCC -> TAC (S -> Y)	99.96	100.00	2637/2637	contig00008	22801	20165	S83Y			Target modification	7492118,10471553
SRR1952926	gyrA (S83Y)	ciprofloxacin I/R, nalidixic acid	Nalidixic acid,Ciprofloxacin	codon	83	TCC -> TAC (S -> Y)	99.96	100.00	2637/2637	contig00011	157768	160404	S83Y			Target modification	7492118,10471553
out/plasmidfinder.tsv:

Isolate ID	Plasmid	%Identity	%Overlap	HSP Length/Total Length	Contig	Start	End	Accession
SRR1952908	ColpVC	98.96	100	193/193	contig00038	1618	1426	JX133088
SRR1952908	IncFIB(S)	98.91	100	643/643	contig00024	10302	9660	FN432031
out/mlst.tsv:

Isolate ID	Scheme	Sequence Type	Locus 1	Locus 2	Locus 3	Locus 4	Locus 5	Locus 6	Locus 7
SRR1952908	senterica_achtman_2	11	aroC(5)	dnaN(2)	hemD(3)	hisD(7)	purE(6)	sucA(6)	thrA(11)
SRR1952926	senterica_achtman_2	11	aroC(5)	dnaN(2)	hemD(3)	hisD(7)	purE(6)	sucA(
