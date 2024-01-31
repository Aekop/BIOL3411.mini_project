# 1. How to generate the reverse complement of a sequence! 
  1. First, ensure your genome is downloaded into your workbench. In ours is in scratch. 
  2. Login to scratch: /scratch/username/ 
  3. Load your modules -> `module load emboss/6.6.0` and `module load seqtk/1.3`
  4. Check that they loaded with `module list`
Now, you are ready to begin to generate the reverse complement.
  5. Use `infoseq` to see what your downloaded file contains. It should output the complete genome, plasmids, and         chromosomes.
  6. Choose a plasmid *not* the whole genome.
  7. Use `echo` or any other document creation command. `echo accession_number > new_file.txt` ours was `echo AE001583.1 > list.txt`
  8. Now use seqtk subseq to isolate your sequence from your complete genome and save it in a new file. `seqtk subseq downloaded_genome.fna new_file.txt > accession_number` ours was `seqtk subseq GCA_000008685.2_ASM868v2_genomic.fna list.txt > AE001583.1`
  9. Now make the reverse complement! `revseq accession_number accession_number.rev` ours was `revseq AE001583.1 AE001583.1.rev`
  10. Remember to check your work using `cat` to see the contents of your files.
  
# 2. How to calculate the GC content of the file! 
  1. Use the same modules if needed download using -> `module load emboss/6.6.0` and `module load seqtk/1.3`
  2. Use this command to calculate the nucleotide content of your sequence `seqtk comp downloaded_genome.fna | awk 'OFS="\t" {sumA+=$3; sumC+=$4; sumG+=$5; sumT+=$6} END {print "A:"sumA,"C:"sumC,"G:"sumG,"T:"sumT}'` This will print out A:, C:, G:, T:.
  3. Our results were: A:554356	C:209969	G:218703	T:538125
  4. Then do some simple math! ((G+C)/Total_nuc)*100 = % GC content.
  5. Our results are 28.18%. 

# 3. How to predict the amino acid sequence of a mRNA sequence!
  1. If not already loaded, run: `module load emboss/6.6.0`
  2. Use `transeq` from the emboss/6.6.0 module to translate the nuceleic acid sequence to amino acids: `transeq <nucleotide_seq_filename> <new_protein_filename>`.<br>
       1. For example: `transeq AE001583.1.rev AE001583.1.pep` translates the mRNA sequence stored in AE001583.1.rev and writes the amino acid seqeunece into AE001583.pep
       2. [`transeq` documention](https://emboss.sourceforge.net/apps/release/6.6/emboss/apps/transeq.html)
