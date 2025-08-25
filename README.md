# namjusthoughts.github.io

# Motivation

In my last semester at Vanderbilt (Spring of 2025) , I met Dr.Ravi Shah who was a Dr.Gamazon's new collaborator. I generated some data for them to write a grant on cardiorespiratory fitness. I am now at Penn Vet (Fall 2025) and finished orientation. The first-years toured the New Bolton Center and I learned that sports medicine is a field in veterinary medicine. I wondered if I can do a TWAS on race horses and see what proteins indicate healthy crf in the blood and if I can apply that to human medicine. I think it would be interesting since they would be under stronger evolutionary pressure due to aritifical selection. Also..consider longitudinal aspects too because animals' lifespan are typically shorter

To do more in-depth research, I wanted to review what I know and have a fundamental understanding of any overlooked concepts during first semester of vet school, when I probably would not be doing any research. 

# Vet school aspirations

If I consider the UK Biobank, the sample size outweighs any kind of research I might be doing in the near future. Thus, to better leverage what I have in front of me and do something sepcial by pusuing veterinary medicine, I must consider the unique nature of veterinary medicine. 

# Goal
1. Consolidate what I know so far about genomics, transcriptomics, and proteomics
2. Review statistical concepts
3. Think about research questions
4. Learn the github md file syntax
5. Gain more knowledge on evolutionary biology

Questions I had: non-matrix factorization, bayesian methods, batch effect, regressing out covariates

# Statistics

**Bernoulli random variable**

**Discrete random variable**

**Continuous random variable** 

probability mass function
cumulative distribution function

**independent and identically distributed**
1. The Xis are independent
2. Every Xi has the same probability distribution

**variance**

$E(X^2) - (E(X))^2 = E(X^2) - µ^2

or 

$E[(X-µ)^2]
- V(aX+b) = a^2 * V(x)


**Moment generating function**
(kth moment of random variable X is E(X^k), while the kth moment about the mean of X is E[(X-µ)^k], where µ = E(X))

$ M_x(t) = E(e^{t X}) = sum_{x} e^{t x} p(x)

$ M_Y(t) = e^{b t} M_x(at)

$ M_x(0) is the sum of all probabilities

**Binomial Distribution**

$$
b(x;n,p) = P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}
B(x;n,p) = P(X \leq k) = \sum_{y=0}^{x} b(y;n,p)
E(X) = np
V(X) = np(1-p)
$$

Using the moment generating function for binomial distribution

$$
M_x(t) = E(e^{t X}) = \sum_{x} e^{t x} p(x) = \sum_{x=0}^n e^{t x} \binom{n}{x}p^x(1-p)^{n-x} = \sum_{x=0}^n \binom{n}{x}(pe^t)^x(1-p)^{n-x} = (pe^t + 1 - p)^n
$$




Sampling distribution of a Statistic
e.g. distribution of the mean px(x), distribution of 

# Genome-wide association studies (GWAS)

## Quantitative Phenotypes
Quantitative traits such as LDL level in the blood, height, weight, etc

Additive model
y = µ + xß + 𝜀 
- µ = mean of genotype 0 (when all are homozygous reference/alternate)
- ß = effect of each copy of allele 1 on mean phenotype
- 𝜀 = error term 
- y = quantitative phenotype

Fit a linear regression on the quantitative trait with respect to SNP x.

lm.fit = lm(y~x)
summary(lm.fit)

Under coefficients, (Intercept) and x have column "Estimate"
- Standard error: 
- t value
- Pr(>|t|)


## Binomial Phenotypes


# Transcriptomics

## RNA-seq
source: youtube
https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-0881-8
https://hhj6212.github.io/sequencing/informatics/2021/04/10/CPM-TPM.html
for analysis: https://pmc.ncbi.nlm.nih.gov/articles/PMC4670015/
https://pmc.ncbi.nlm.nih.gov/articles/PMC6096346/
quantification: [https://www.rna-seqblog.com/rpkm-fpkm-and-tpm-clearly-explained/](https://www.youtube.com/watch?v=TTUrtCY2k-w)

### How it is done
1. extract RNA
2. break RNA into pieces because some are very long and sequencing machine can only sequence about 200~300bp fragments
3. convert RNA fragments into double stranded DNA
4. add sequencing adapter
   - recognize fragments
   - sequence different samples at same time bc different samples use diff adapters 
5. PCR amplify
6. QC
   - filter out garbage reads
     - adapter can bind to each other 
   - align high quality reads to a genome
   - count number of reads per gene
7. Normalize
    - Raw count: affected by transcript length, total number of reads, and sequencing biases
    - RPKM (reads per kilobase of exon model per million reads):
      $$
  
      $$
         - for single end RNA-seq
         - within-sample normalization that remove feature-length and library-size effects
         - kilobase: length of fragments
             - longer genes will have more reads mapped
         - million: sequencing depth
             - runs with more depth will have more reads mapped to each gene 
             
    - FPKM (fragments per kilobase of exon model per million mapped reads): within-sample normalized transcript expression measure
  
    $$
      [Number of fragments]/[(transcript length/1000)/(total reads)/10^6)]
    $$
         - paired end RNA-seq: both ends can map so give two reads. FPKM accounts
                          for that
         - kilobase: length of fragments
         - million: sequencing depth 
           
    - TPM (transcripts per million):
  
    $$
      TPM = 10^6 * ((reads mapped to transcript)/(transcript length))/Sum(reads mapped to transcript/transcript length) = 10^6 * RPKM/Sum(RPKM)
    $$ 
    
          - between-sample comparison
          1. normalize for gene length (kb) by dividing from raw count, giving reads per kilobase
          2. normalize for sequencing depth by dividing the sum of each replication by million. This gives a scaling factor, which can be used to divide reads per kilobase with.
   
Things to consider to quantify RNA expression across different genes, replicates, and experiments, two factors must be controlled for:
-	**The different number of reads** (if there are inconsistences in the preparation of your **sequencing library**, you might get more cDNA in one experiment than another, leading to more reads across all genes, but that doesn’t indicate an increase in expression across all genes)
-	**Different lengths of genes**


### Different units

