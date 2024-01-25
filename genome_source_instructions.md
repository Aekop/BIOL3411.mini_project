# How to download the *Borrelia burgdorferi* genome used in this project.

1. Navigate to the [GenBank data source](https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/008/685/GCA_000008685.2_ASM868v2/) page from [GenomeNet](https://www.genome.jp/kegg-bin/show_organism?org=bbu).
2. Copy the link address of the desired file by right-clicking on the specific file.
   1. GCA_000008685.2_ASM868v2_genomic.fna.gz file was used in this project.
3. On the command line, navigate to the directory in which the genome will be saved.
4. Run `wget <link_you_just_copied_to_genome>`.
   1. Upon downloading the genome, the text file is compressed and the contents are not in plain English.
   2. Note: the filename will end in the extension .gz
5. Unzip the .gz file with `gunzip -d <genome_filename.gz>`.
   1. `-d`: decompress the compressed file.
     1. Reference for decompressing .gz files:<br>
        Michael. *Files ending with .fna.gz, .gbff.gz, .gff.gz, .faa.gz & gpff.gz* [Online forum response]. Biostars. [https://www.biostars.org/p/192781/](https://www.biostars.org/p/192781/)
   2. The genome file should now contain ATCGs!
   3. Note: the .gz file extension will now be absent.
