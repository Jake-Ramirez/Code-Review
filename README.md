# Code Review

Link to the [article](https://journals.asm.org/doi/10.1128/msystems.00182-21?utm_source=google&utm_medium=cpc&utm_campaign={campaignname}&utm_id=23710637249&utm_term=&utm_content={adgroupname}-&utm_device=c&utm_network=x&utm_matchtype=&utm_adgroupid=&gad_source=1&gad_campaignid=23705254047&gbraid=0AAAAADL69_3QT-vfkthuorwytScJD3aEJ&gclid=CjwKCAjw46HPBhAMEiwASZpLRFfJ9rUup7fAOeUhQkhHK8bxILd9DgIdWy__YNj_0Qyz2f1K_c_bKxoCDEMQAvD_BwE) and to the [repository](https://journals.asm.org/doi/10.1128/msystems.00182-21?utm_source=google&utm_medium=cpc&utm_campaign={campaignname}&utm_id=23710637249&utm_term=&utm_content={adgroupname}-&utm_device=c&utm_network=x&utm_matchtype=&utm_adgroupid=&gad_source=1&gad_campaignid=23705254047&gbraid=0AAAAADL69_3QT-vfkthuorwytScJD3aEJ&gclid=CjwKCAjw46HPBhAMEiwASZpLRFfJ9rUup7fAOeUhQkhHK8bxILd9DgIdWy__YNj_0Qyz2f1K_c_bKxoCDEMQAvD_BwE).

---
## Summary

This manuscript by Mukherjee presents a meta-analysis framework for dual RNA sequencing (RNA-Seq) data in the context of malaria infection. The core idea is compelling: rather than treating host or parasite reads as "contamination," the authors repurpose existing public RNA-Seq datasets from *Homo sapiens*, *Macaca mulatta*, and *Mus musculus* to simultaneously analyze host and *Plasmodium* transcriptomes and infer cross-species gene co-expression networks. This pipeline spans from raw sequence retrieval through ortholog identification, correlation analysis, network construction, and GO enrichment. As requested by the editor, my review below focuses on the code associated with this manuscript.

---

## High-Level Feedback

1. **The README is truly useful in exchange for a lack of methods supplement.** It is evident that the production of this documentation has been a curated endeavor. Each of the 12 steps are explained in plain language, and the entry-point shortchut ("If you want to run the analysis downstream of retrieving these networks, please feel free to download the networks and run any script atfer Step 6.") is a thoughtful design choice that makes the downstream analysis accessible for different necessities. I am aware that some reviewers might point to the lack of a methods supplement, nevertheless the extensive README perfectly compensates it since users truly interested in reproducing this work are probably the github conoisseurs.

2. **There is no reproducible environment specification.** While the readme lists approximately 25 R packages required to run the pipeline, no version is specified and no mechanism to recreate the author's environment is provided. Given the overall high conding understanding here displayed I find surprising that tools like 'renv' were not used to generate a lockfile of all package versions.

3. **The pipeline is modular in spirit, but partially incomplete.** Each step maps to a named script, which is excellent practice. However, the README explicitly acknowledges that the thresholding script is missing ("The script for applying thresholds are not included in this repo at the moment") and that some downstream sections are "not yet fully reproducible." For a published paper, a reader who wants to fully reproduce the results would hit a wall at Step 3. The authors should either include the missing scripts or clearly document what manual steps are needed to substitute for them. Also it has been 4 years since the last time the README has been modified.

4. **Steps 1–2 require substantial manual file preparation with no guidance on format validation.** Setting up the pipeline from scratch involes manually creating several input files. While the the README describes the content of the files no format reference is provided in for the second step. Also in the first script a [function](https://github.com/seandavi/SRAdb/blob/master/R/getSRAdbFile.R) from another repo is mentioned, in my opinion this makes the reproducibility of your pipeline contingent upon another using not modifying or erasing files.

5. **Computational time and resource requirements are not mentioned.** Step 4 run 10,000 permutation test, this could be computationally demanding. The user should have an idea if their environment (local or remote) counts with the necessary computing power to reproduce this analysis (in hours, days?).

---

## Specific / Lower-Level Feedback 

- **The Zenodo archive should be more prominently mentioned.** The frozen version of the code used for the paper (`https://doi.org/10.5281/zenodo.4535898`) is cited in the paper but is not referenced anywhere in the README itself. This makes it easy to everlook!!
