How to generate the reverse complement of a sequence! 
  1. First, ensure your genome is downloaded into your workbench. In our this is scratch. 
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
  
