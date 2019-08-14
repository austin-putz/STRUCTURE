# STRUCTURE

Documentation for the STRUCTURE software to discover underlying population structure

# Disclaimer

Like anything open source, absolutely no warranty with anything in this respository or my other GitHub repositories. Not associated with my role as Geneticist with Hypor. Simply documentation for myself and others who need to learn how to use STRUCTURE software for a genetic analysis. 

# Documentation

I don't think there is any. Free and open-source software is usually extremely poorly documented. This software is no different. Here is a link to the website ([STRUCTURE](https://web.stanford.edu/group/pritchardlab/structure.html)), but I don't see any documentation anywhere. I think most people learn by word of mouth. 

# File Input Format

The genotype file input follows
1) Column 1 = Identification of the animal or human
2) Column 2 = Group identification
3) Column 3,4,...,n = alleles coded (1 and 2 for alleles A or B, 0 is missing)

I make sure everything starts at the same character number. 

From the dense genotype codes counting (Illumina) 'B' alleles, 0,1,2 (5 missing) format to this format requires coding 0 -> 1 1, 1 -> 1 2, and 2 -> 2 2. 

![Screenshot of Genotype File](/Screenshots/structure_input_genotype_file_format.png?raw=true "Genotype file input")

In animal breeding, we commonly use dense genotypes. 

![Screenshot of dense genotype format](/Screenshots/dense_genotype_format.png?raw=true "Dense genotype format")

You can use the `dense_to_structure.sh` shell script for the conversion. It's attached. Simply make it executable with `chmod 775 dense_to_structure.sh`. 

You can run structure with the following command:

```shell
./structure -N 237 -L 49119 -K 6 -i structure.in -o output1.txt
```

Where `237` is the number of individuals, `49119` is the number of SNP (2 times this number of columns associated with these), `6` is the magical 'K' value specified to the program. This K value is the number of populations you assume (please see Lawson, van Dorp, and Falush, 2018, doi:10.1038/s41467-018-05257-7 for more on this value). `structure.in` is the input file name (genotype file) and `output1.txt` is the name of the output file (ancestrial composition or breed composition output is here). 



