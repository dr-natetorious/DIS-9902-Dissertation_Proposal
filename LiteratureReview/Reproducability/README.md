# Reproducability challenges in ML

## The Challenge of Reproducible ML (2021)

E. Rivera-Landos, F. Khomh and A. Nikanjam, "The Challenge of Reproducible ML: An Empirical Study on The Impact of Bugs," 2021 IEEE 21st International Conference on Software Quality, Reliability and Security (QRS), 2021, pp. 1079-1088, doi: 10.1109/QRS54544.2021.00116. [EmpiricalStudy.pdf](EmpiricalStudy.pdf).

The authors state that only 25% of deep learning papers contain code, and most repositories are unusable. One study found that 9% of surveyed papers **could** be reproduced, not wheather the results match.

They talk about the need for seeding data, which is good suggestion.

## Analyzing the analyzers (2018)

Qiu, L., Wang, Y., & Rubin, J. (2018). Analyzing the analyzers: FlowDroid/IccTA, AmanDroid, and DroidSafe. Proceedings of the 27th ACM SIGSOFT International Symposium on Software Testing and Analysis, 176–186. https://doi.org/10.1145/3213846.3213873

This paper also appeared in [TIM-8101 Principals of CS Week 5](https://github.com/dr-natetorious/TIM-8101-Principals_of_Computer_Science/tree/master/Week5_Conferences).

## Should We Strive to Make Science Bias-Free (2021)

Hudson, R. (2021). Should We Strive to Make Science Bias-Free? A Philosophical Assessment of the Reproducibility Crisis. Journal for General Philosophy of Science, 52(3), 389–405. https://doi.org/10.1007/s10838-020-09548-w. [ScienceBiasFree.pdf](ScienceBiasFree.pdf).

1. Reproducibility versus Replicability
1. Start with data; follow with method
1. Using the wrong statistical method
1. Influence of societal norms
1. Insufficient evidence to disprove null hypothesis
1. Publication Bias (new sells; repeats dont)

## Addressing the Reproducibility Crisis (2022)

Douglas, H., & Elliott, K. C. (2022). Addressing the Reproducibility Crisis: A Response to Hudson. Journal for General Philosophy of Science, 1–9. https://doi.org/10.1007/s10838-022-09606-5. [Douglas-Elliott2022_Article_AddressingTheReproducibilityCr](Douglas-Elliott2022_Article_AddressingTheReproducibilityCr.pdf)

In this rebuttle, Douglas claims that Hudson doesn't know head from ass.

> In this response to Robert Hudson’s article, “Should We Strive to Make Science BiasFree? A Philosophical Assessment of the Reproducibility Crisis,” we identify three ways in which he misrepresents our work: (1) he confates value-ladenness with bias; (2) he describes our view as one in which values are the same as evidential factors; and (3) he creates a false dichotomy between two ways that values could be considered in science for policy. We share Hudson’s concerns about promoting scientifc reproducibility and reducing bias in science, but we reject his view that the value-free ideal provides helpful guidance for addressing these issues. [NoRawData](NoRawData.pdf).

## No raw data, no science (2020)

Miyakawa, T. (2020). No raw data, no science: another possible source of the reproducibility crisis. Molecular Brain, 13(1), 24. https://doi.org/10.1186/s13041-020-0552-2.

> A reproducibility crisis is a situation where many scientific studies cannot be reproduced. Inappropriate practices of science, such as HARKing, p-hacking, and selective reporting of positive results, have been suggested as causes of irreproducibility. In this editorial, I propose that a lack of raw data or data fabrication is another possible cause of irreproducibility.As an Editor-in-Chief of Molecular Brain, I have handled 180 manuscripts since early 2017 and have made 41 editorial decisions categorized as "`Revise before review`," requesting that the authors provide raw data. **Surprisingly, among those 41 manuscripts, 21 were withdrawn without providing raw data, indicating that requiring raw data drove away more than half of the manuscripts**. I rejected 19 out of the remaining 20 manuscripts because of insufficient raw data. Thus, **more than 97% of the 41 manuscripts did not present the raw data supporting their results when requested by an editor, suggesting a possibility that the raw data did not exist from the beginning**, at least in some portions of these cases.Considering that any scientific study should be based on raw data, and that data storage space should no longer be a challenge, journals, in principle, should try to have their authors publicize raw data in a public database or journal site upon the publication of the paper to increase reproducibility of the published results and to increase public trust in science.

They identify madeup research when

> These comments are made when I feel that the data shown are ‘too beautiful to be true’, when error bars are too short despite a small number of samples analyzed, and/or when the effect size of experimental manipulation is huge (sometimes accompanied with complete rescue by some drug administration).

## Quantum computing’s reproducibility crisis (2021)

Frolov, S. (2021). Quantum computing’s reproducibility crisis: Majorana fermions. Nature: International Weekly Journal of Science, 592(7854), 350–352. https://doi.org/10.1038/d41586-021-00954-8. [Quantum_computing's_reproducib](Quantum_computing's_reproducib.pdf).

The authors discuss Majroanas, a nanowire that is heavily cited technology for quantum circuits.

> Producing Majoranas in the laboratory is very hard. Experiments combine cutting-edge fields such as nanotechnology, superconductivity, device engineering and materials science. In the most developed approach, researchers must first grow a nanowire crystal - a feat in itself - to produce a column of atoms 100 nanometres (one-thousandth the width of a human hair) across. Then they must connect the wire to a circuit sensitive enough to measure single electrons travelling through it. The whole experiment must be done at about one-hundredth of a degree above absolute zero, in a magnetic field 10,000 times that of Earth's.

Reproducing previous experiments is disproving several critical assumptions.

> In 2020, these observations came under scrutiny after replication experiments were conducted. Science published an experiment led by researchers at Pennsylvania State University in University Park contradicting the 2017 report4. My group reproduced patterns from the 2018 Nature study, but demonstrated that they need not originate from Majorana5. We did a cross-check on both ends of the same nanowire, but found a current peak on only one end. This violated the basic expectation from the theory that Majoranas always come in pairs. The rate of rebuttal is speeding up: researchers have not been able to confirm the findings6,7 of two separate papers claiming to have found Majorana regimes in nanowires8,9. And reports of current peaks in a new ironbased superconductor, Fe(Te,Se), that were attributed to Majoranas10-12 in Science and Nature Communications will need to become more nuanced after a Physical Review Letters publication this year13.

It's critical to remember that cutting-edge technology doesn't always work. You need to validate systems until they're proven.

## Replication Redux (2021)

Ozier, O. (2021). Replication Redux: The Reproducibility Crisis and the Case of Deworming. World Bank Research Observer, 36(1), 101–130. https://doi.org/10.1093/wbro/lkaa005. [ReplicationRedux.pdf](ReplicationRedux.pdf)

> In 2004, a landmark study showed that an inexpensive medication to treat parasitic worms could improve health and school attendance for millions of children in many developing countries. Eleven years later, a headline in The Guardian reported that this treatment, deworming, had been “debunked.” [...] In this paper, I explore what it means to “replicate” and “reanalyze” a study, both in general and in the specific case of deworming.

## Reproducibility in deep learning algorithms (2020)

Tomaszewski, J. E., Ward, A. D., Li, W., & Chen, W. (2020). Reproducibility in deep learning algorithms for digital pathology applications: a case study using the CAMELYON16 datasets. Proceedings of SPIE, 11603, 1160318. https://doi.org/10.1117/12.2581996.
