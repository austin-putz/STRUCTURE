# STRUCTURE

Documentation for the STRUCTURE software to discover underlying population structure

# Disclaimer

Like anything open source, absolutely no warranty with anything in this respository or my other GitHub repositories. Not associated with my role as Geneticist with Hypor. Simply documentation for myself and others who need to learn how to use STRUCTURE software for a genetic analysis. 

# File Input Format

The genotype file input follows
1) Column 1 = Identification of the animal or human
2) Column 2 = Group identification
3) Column 3,4,...,n = alleles coded (1 and 2 for alleles A or B, 0 is missing)

From the dense genotype codes counting (Illumina) 'B' alleles, 0,1,2 (5 missing) format to this format requires coding 0 -> 1 1, 1 -> 1 2, and 2 -> 2 2. 

![Screenshot of Genotype File](/Screenshots/structure_input_genotype_file_format.png?raw=true "Genotype file input")

In animal breeding, we commonly use dense genotypes. 

![Screenshot of dense genotype format](/Screenshots/dense_genotype_format.png?raw=true "Dense genotype format")

You can use the `dense_to_structure.sh` shell script for the conversion. It's attached. Simply make it executable with `chmod 775 dense_to_structure.sh`. 






