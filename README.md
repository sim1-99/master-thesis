# 3D U-Net Domain Generalization in Fetal Brain MRI Segmentation

MSc thesis in Applied Physics, University of Bologna, A.Y. 2024/2025.

## Abstract

This work investigates domain generalization of a 3D U-Net (nnU-Net v2.4.1) for fetal brain MRI tissue segmentation. The central question was whether GIN-IPA, a promising but not widely studied image augmentation method, would improve the network robustness across acquisition shifts. Three datasets with different super-resolution reconstruction (SRR) were employed: Kispi-mial (small size, both healthy and pathological cases), Kispi-irtk (similar to Kispi-mial but higher quality), and dHCP (larger size, high quality, healthy only). Label sets were harmonized to a common 7-tissue scheme.

Three strategies were compared within the nnU-Net training loop: (i) default nnU-Net augmentation, comprising standard geometric and photometric transforms; (ii) GIN-IPA, an appearance perturbation that aims to mimic acquisition shifts; and (iii) the combination of both. Models were trained separately on each dataset and assessed on unseen samples from both the source dataset and external datasets, using typical metrics such as the Dice score and others.

Two conclusions were drawn. First, generalization was primarily determined by data quality and scale: training on dHCP yielded the most stable cross-domain performance, almost independent of augmentation. Second, GIN-IPA was beneficial when source data were limited and differed from the target: training on Kispi-irtk and inferring on dHCP resulted in significant improvements compared to default nnU-Net augmentation. By contrast, stacking the two augmentations was not additive and, at times, detrimental.

Limitations include the small size of public clinical datasets, the need for label-set harmonization, and hardware constraints that prevented a full exploration of the GIN-IPA potential. The results suggest that multi-center, high-quality fetal MRI with standardized SRR should be prioritized. Within constrained single-source regimes, GIN-IPA may represent a pragmatic option for domain generalization, despite the need for further validation.
