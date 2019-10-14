# A rough overview of:
# Abundance of conserved CRISPR-Cas9 target sites within highly polymorphic genomes of Anopheles and Aedes mosquitoes from natural populations
Hanno Schmidt, Travis C. Collier, Mark J. Hanemaaijer, Parker D. Houston, Yoosook Lee, Gregory C. Lanzaro

------------------

## Background ##

- CRISPR-Cas9 targets a 23bp sequence of DNA.
- Important mosquitoes have a lot of genetic diversity.
- Some folks question wether there are many Cas9 targets without polymorphism in natural poulations.

Let's just check all the targets in all the protein coding genes and see how many are *good*.  
By *good*, we mean it is
- has the right PAM and has appropriate GC ratio
- specific (no off-target matches with &leq; 3 mismatches) 
- and has natural variation below a given threshold.

(First two items are handled by the chopchop program from valenlab)

## Genomes ##

| | Anopheles gambiae s.l. (AgamP4.11) | Aedes aegypti (AaegL5.1) | 
| --- | --- | --- |
| **Genome size (Mbp)** | 230.5 | 1,195 |
| **Coding part of the genome (Mbp)** | 25.7 (11.2%) | 59.1 (5%) |
| **Protein-coding genes** | 12,562 | 13,601 |
| --- | --- | --- |
| **Raw targets** | 3,918,579 | 3,638,628 |
| **Potential targets** | 1,196,509 (30.5%) | 828,454 (22.8%) |
| **Protein-coding genes with potential targets** | 12,213 (97.2%) | 12,536 (92.2%) |


## Datasets ##

| **dataset** | VGL-gam | Ag100g-gam | VGL-col | Ag1000g-col | VGL-Aaeg |
| --- | --- | --- | --- | --- | --- |
| **species** | An. gambiae s.s. | An. gambiae s.s. | An. coluzzii | An. coluzzii | Ae. aegypti |
| **num. samples** | 111 | 654 | 100 | 283 | 132 |
| **seq. depth\*** | 8x | 30x | 10x | 30x | 10x |
| **countries** | Cameroon, Comoros, Mali, Tanzania, Zambia | Burkina Faso, Cameroon, Eq. Guinea, Mayotte (Fr.), Gabon, Ghana, Guinea, Uganda | Benin, Cameroon, Eq. Guinea, Mali, São Tomé and Príncipe | Angola, Burkina Faso, Côte d'Ivoire, Ghana, Guinea | Mexico, South Africa, California USA, Florida USA |
| **years** | 2006, 2011, 2015 | 2000, 2002, 2009, 2011, 2012 | 2002, 2004, 2005, 2006, 2010, 2011, 2012, 2014, 2015, 2017 | 2009, 2012 | 2013, 2014, 2015, 2016, 2017, 2018 |
| **nucleotide diversity\*\*** | 0.98% | 1.02% | 1.00 | 0.95% | 0.94% |

\* median sequencing depth of all coding transcript position and all samples  
\** for coding transcripts only

> The nucleotide diversity of coding transcripts for each dataset is near 1%.  
> Genome-wide nucleotide diversity is estimated at 2% for each of the gambiae and coluzzii datasets.  The estimate based on VGL-Aaeg is 1.3%, but this is likely a significant underestimate since aegypti contains many highly polymorphic regions which fail to sequence or map to the reference well.  
> As a point of comparison, a relatively high estimate of human nucleotide diversity is 0.6% (https://www.nature.com/articles/nature15393).  


## Results ##
*Note: DRA = Drive Resistance Allele.  
In this context the % DRA is the percent of variant allels we deem acceptable*

### % Genes with good CRISPR targets by dataset ###

<img src="percent_good_genes_overview.svg" width=75% alt="Good genes by dataset">  
Results are highly dependent on number of samples.  Lots of samples allows detection of more rare variants.  
Ignoring variants with freq \< 1% makes sample size dependency go away.

### Relationship between allowable DRA % number of targets ###

<img src="Ag1000g-gambiae_good-vs-freq.png" width=75% alt="Good vs frequency">
Good targets (orange) drop off quickly as allowable DRA % decreases.  
Genes with at least 1 good target (blue) doesn't drop until very low allowable DRA %, but then drops quick.

## Conclusions ##
- Many possible Cas9 targets, but most have variants which might be DRA.
- Since most genes have many targets, there is a high chance at least one is good.
- ...Unless you can not accept even a very low frequency of variants.

- Pop Replacement gene drive strategies don't put strong selection on resistance.  So some low freq DRAs are OK.
- Pop Suppression gene drive very strongly selects for resistance... so DRAs are probably trouble.

- When targeting a gene for CRISPR-Cas9, look at natural variation in all the possible targets in the gene **before** making a strain.
