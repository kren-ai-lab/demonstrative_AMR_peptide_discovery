# Toward Explainable and Adaptive Artificial Intelligence Systems for Antimicrobial Peptide Discovery under Resistance Pressure

This repository contains the source code and relevant information for the implementations and use cases presented in the work: <br>
Ana Luisa Islas-Ávila<sup>1</sup>, Julián García-Vinuesa <sup>2</sup>, Nicole Soto-García<sup>2</sup>, Michelle Soto-García<sup>3</sup>, Bárbara Gutiérrez-Cárdenas<sup>2</sup>, Alejandro Inostroza-Munoz<sup>4</sup>,
Mehdi D. Davari<sup>4</sup>, Leandro Murgas<sup>2</sup>, Roberto Uribe-Paredes<sup>2</sup>, Alicia Martínez-Rebollar<sup>1</sup>, Julieta Sepulveda-Yanez<sup>5,6</sup>, and David Medina-Ortiz<sup>2,4,∗</sup>

Toward Explainable and Adaptive Artificial Intelligence Systems for Antimicrobial Peptide Discovery under Resistance Pressure. <br>


<sup>*1*</sup><sub>Departamento de Ciencias Computacionales, Tecnológico Nacional de México/CENIDET, Interior Internado Palmira SN, 62490, Morelos, México.</sub> <br>
<sup>*2*</sup><sub>Departamento de Ingeniería En Computación, Universidad de Magallanes, Avenida Bulnes 01855, 6210427, Punta Arenas, Chile.</sub> <br>
<sup>*3*</sup><sub>Escuela de Diseño, Facultad de Arquitectura, Música y Diseño, Universidad de Talca, Av. Lircay SN, 3460000, Talca, Chile.</sub> <br>
<sup>*4*</sup><sub>Department of Bioorganic Chemistry, Leibniz Institute of Plant Biochemistry Weinberg 3, 06120 Halle, Germany.</sub> <br>
<sup>*5*</sup><sub>Facultad de Ciencias de la Salud, Universidad de Magallanes, Av. Pdte. Manuel Bulnes 01855, 6210427, Punta Arenas, Chile.</sub> <br>
<sup>*6*</sup><sub>Centro Asistencial de Docencia e Investigación, CADI, Universidad de Magallanes, Av. Los Flamencos 01364, 6210005, Punta Arenas, Chile.</sub> <br>
<sup>*\**</sup><sub>Corresponding author</sub> <br>

---
## Table of Contents
- [A summary of the proposed work](#summary)
- [Requirements and instalation](#requirements)
- [Raw data and preprocessing](#data)
- [Implemented pipeline](#pipeline)
---

<a name="summary"></a>

# Protein language models and machine learning facilitate the identification of antimicrobial peptides.

Therapeutic peptides have emerged as promising candidates for combating antimicrobial resistance, particularly against multidrug-resistant pathogens for which conventional antibiotics are becoming increasingly ineffective. Although artificial intelligence has accelerated antimicrobial peptide discovery through predictive modelling, generative design, and large-scale *in silico* screening, many current workflows remain fragmented, weakly interpretable, and only loosely connected to experimental feedback. In this Perspective, we propose a methodological framework for resistance-aware antimicrobial peptide discovery built upon three complementary principles: explainable and uncertainty-aware prediction, biologically constrained and rule-guided generative design, and iterative design-test-learn workflows capable of continuously incorporating new evidence. Rather than introducing new predictive or generative models, we focus on how existing methodologies can be organised into adaptive and transparent discovery systems that support candidate prioritisation, optimisation, and iterative refinement under evolving resistance pressures. To illustrate the practical implementation of these concepts, we further present a demonstrative workflow integrating interpretable prediction, uncertainty-aware prioritisation, rule extraction, and adaptive model updating. Collectively, this framework provides a roadmap for advancing antimicrobial peptide discovery from isolated predictive tasks toward integrated and evidence-driven discovery ecosystems.

<a name="requirements"></a>
    <h2>
        Requirements and Install process
    </h2>

The requirements are summarized in the [environment.yml](environment.yml) file. Some requirements are summarized below:

- Python version 3.12
- scikit-learn
- shap

Once this repository is cloned, please run the following command:

```
    conda env create -f environment.yml
```
<a name="data"> </a>
    <h2>
        Raw data and collection process
    </h2>

- All data was collected from the [Peptipedia v2.0 database](https://app.peptipedia.cl/)
- The raw data is available on the folder [collected_sequences](collected_sequences)

<a name="examples"> </a>
    <h2>
        Notebook examples
    </h2>

Examples of how to apply the AMP demonstrative case study are available as jupyter notebook examples, please see:

- Preparing AMP dataset: [notebooks/01_preparing_amp_dataset.ipynb](notebooks/01_preparing_amp_dataset.ipynb)
- Dataset description and exploratory analysis: [notebooks/02_amp_dataset_description.ipynb](notebooks/02_amp_dataset_description.ipynb)
- Distance-aware training with uncertainty estimation: [notebooks/03_amp_training_uncertainty.ipynb](notebooks/03_amp_training_uncertainty.ipynb)
- Explainability and interpretable rule extraction: [notebooks/04_amp_explainability_shap_rules.ipynb](notebooks/04_amp_explainability_shap_rules.ipynb)
- Rule-aware prioritization and candidate ranking: [notebooks/05_amp_rule_aware_prioritization.ipynb](notebooks/05_amp_rule_aware_prioritization.ipynb)
- External candidate screening and illustrative Design–Test–Learn loop: [notebooks/06_amp_external_screening_dtl_loop.ipynb](notebooks/6_amp_external_screening_dtl_loop_patched.ipynb)
- Multipanel figure: [notebooks/07_generate_amp_demonstrative_case.ipynb](notebooks/07_generate_amp_demonstrative_case_figure_nature_v3.ipynb)

<a name="implementation"></a>

<h2>
    Implemented explainable and adaptive AMP discovery workflow
</h2>

The results of the implemented workflow is represented in the following figure:

![alt text](paper_figures/figure_amp_demonstrative_case_multipanel.png)

**llustrative implementation of an explainable and adaptive antimicrobial peptide discovery workflow.**  **A.** Physicochemical, compositional, structural propensity, and entropy-related descriptors were extracted from a curated antimicrobial peptide dataset and used to characterize differences between antimicrobial and non-antimicrobial sequences. **B.** Ensemble-based predictive modelling combined with SHAP analysis enabled identification of the most influential descriptors driving antimicrobial activity predictions. **C.** Prediction uncertainty was estimated from ensemble variability, allowing confident predictions to be distinguished from ambiguous regions of sequence space. **D.** Global explanatory signals were translated into explicit and interpretable decision rules through surrogate modelling, generating human-readable design constraints. **E.** Candidate prioritization combined predicted antimicrobial probability, uncertainty estimates, and rule-support scores, enabling simultaneous identification of high-confidence candidates, exploratory candidates located in uncertain regions, and sequences supported by interpretable design criteria. **F.** An external screening stage followed by pseudo-feedback integration illustrates how newly acquired evidence can be incorporated into iterative model refinement, exemplifying the design--test--learn paradigm proposed in this Perspective.

## License

**GPL-3.0-or-later**. See [LICENSE](LICENSE).
