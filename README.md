# namjusthoughts.github.io

# Motivation
Wanted to review what I know during first semester of vet school, when I probably would not be doing any research. Trying to keep my research side at all times. 

# Goal
1. Consolidate what I know so far about genomics, transcriptomics, and proteomics
2. Review statistical concepts
3. Think about research questions
4. Learn the github md file syntax

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
