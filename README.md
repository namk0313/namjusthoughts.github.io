# namjusthoughts.github.io

# Motivation

In my last semester at Vanderbilt (Spring of 2025) , I met Dr.Ravi Shah who was a Dr.Gamazon's new collaborator. I generated some data for them to write a grant on cardiorespiratory fitness. I am now at Penn Vet (Fall 2025) and finished orientation. The first-years toured the New Bolton Center and I learned that sports medicine is a field in veterinary medicine. I wondered if I can do a TWAS on race horses and see what proteins indicate healthy crf in the blood and if I can apply that to human medicine. I think it would be interesting since they would be under stronger evolutionary pressure due to aritifical selection 

To do more in-depth research, I wanted to review what I know and have a fundamental understanding of any overlooked concepts during first semester of vet school, when I probably would not be doing any research. 


# Vet school aspirations

If I consider the UK Biobank, the sample size outweighs any kind of research I might be doing in the near future. Thus, to better leverage what I have in front of me and do something sepcial by pusuing veterinary medicine, I must consider the unique nature of veterinary medicine. 

# Goal
1. Consolidate what I know so far about genomics, transcriptomics, and proteomics
2. Review statistical concepts
3. Think about research questions
4. Learn the github md file syntax
5. Gain more knowledge on evolutionary biology

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
E(X^2) - (E(X))^2 = E(X^2) - µ^2
or 
E[(X-µ)^2]
- V(aX+b) = a^2 * V(x)


**Moment generating function**



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
    - 
   
Things to consider to quantify RNA expression across different genes, replicates, and experiments, two factors must be controlled for:
-	**The different number of reads** (if there are inconsistences in the preparation of your **sequencing library**, you might get more cDNA in one experiment than another, leading to more reads across all genes, but that doesn’t indicate an increase in expression across all genes)
-	**Different lengths of genes**


### Different units

