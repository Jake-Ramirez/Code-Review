# Code Review

Link to the [article](https://journals.asm.org/doi/10.1128/msystems.00182-21?utm_source=google&utm_medium=cpc&utm_campaign={campaignname}&utm_id=23710637249&utm_term=&utm_content={adgroupname}-&utm_device=c&utm_network=x&utm_matchtype=&utm_adgroupid=&gad_source=1&gad_campaignid=23705254047&gbraid=0AAAAADL69_3QT-vfkthuorwytScJD3aEJ&gclid=CjwKCAjw46HPBhAMEiwASZpLRFfJ9rUup7fAOeUhQkhHK8bxILd9DgIdWy__YNj_0Qyz2f1K_c_bKxoCDEMQAvD_BwE) and to the [repository](https://journals.asm.org/doi/10.1128/msystems.00182-21?utm_source=google&utm_medium=cpc&utm_campaign={campaignname}&utm_id=23710637249&utm_term=&utm_content={adgroupname}-&utm_device=c&utm_network=x&utm_matchtype=&utm_adgroupid=&gad_source=1&gad_campaignid=23705254047&gbraid=0AAAAADL69_3QT-vfkthuorwytScJD3aEJ&gclid=CjwKCAjw46HPBhAMEiwASZpLRFfJ9rUup7fAOeUhQkhHK8bxILd9DgIdWy__YNj_0Qyz2f1K_c_bKxoCDEMQAvD_BwE).

---
## Summary

This manuscript by Mukherjee presents a meta-analysis framework for dual RNA sequencing (RNA-Seq) data in the context of malaria infection. The core idea is compelling: rather than treating host or parasite reads as "contamination," the authors repurpose existing public RNA-Seq datasets from *Homo sapiens*, *Macaca mulatta*, and *Mus musculus* to simultaneously analyze host and *Plasmodium* transcriptomes and infer cross-species gene co-expression networks. This pipeline spans from raw sequence retrieval through ortholog identification, correlation analysis, network construction, and GO enrichment. As requested by the editor, my review below focuses on the code associated with this manuscript.

---

## High-Level Feedback

1.
