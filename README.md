# CTEPH_project
# Prognosis of patients with chronic thromboembolic pulmonary hypertension
*Authors:* I. Garanina, I. Anastasia, M. Kasyanova, A. Zenkova, M. Kuznetsov, S. Yarovoy <img src="\data\pictures\Bioinformatics_Institute.png" height="50"/>

**Introduction** Chronic thromboembolic pulmonary hypertension (CTEPH) is a precapillary form of pulmonary hypertension (PH), characterized by chronic obstruction of large and medium branches of the pulmonary arteries, as well as secondary changes in the microcirculatory bed of the lungs. Its prevalence worldwide is about 1.5-3% of the total PH cases. There are both medical and surgical treatments. 2-year survival is 12% (without treatment) [1]. With treatment, 2-year survival significantly improves, reaching approximately 80-90% after pulmonary endarterectomy (PTE) and around 70-80% with balloon pulmonary angioplasty (BPA), depending on patient characteristics and comorbidities. At the same time, about 37% of patients with CTEPH are considered inoperable. 

**Objective**: To study the factors determining the prognosis of patients with CTEPH on registry data collected in Russian cardiology center.

**Materials and methods**  The study had a single-center bidirectional cohort design: data were collected since 2012 and are still being collected by the National Medical Center of Cardiology of the Ministry of Health of Russia. Patients received different types of treatment: medication and surgery over several years. The study assessed the association between treatment and clinical deterioration or death using Cox or Negative-Binomial models [2, 3]. Due to the lack of data, multiple missing data imputation with a proportional odds model, predictive mean matching and logistic regression was performed for the baseline characteristics [4].
<img src="\data\pictures\Methods.png" height="150"/>

**Results** Data from 80 patients: 43 (54%) male and 37 (46%) female with median age of 54 years (Q1-Q3:  46-67) were included in the analysis. At the start of observation 2 (2.5%) patients belonged to I World Health Organization (WHO) functional class, 11 (14%) were in II class, 49 (62%) were in III class, 16 (20%) were in IV class and for 2 (2.5%) patients class was not estimated. Altogether 2 (2.5%) participants underwent BPA surgery, 4 (5%) - PTE surgery, 14 (17.5%) - PAH therapy,  29 (36%) - BPA and PAH, 6 (7.5%) - PTE and PAH, 1 (1%) - BPA and PTE, 9 (11%) - all three types of therapy and 15 (19%)  had no therapy at all.

*Table 1.* General baseline characteristics of the included subjects
| Characteristic         | N = 80        | Characteristic         | N = 80 |
|:----------------------:|:-------------:|:----------------------:|:------:|
| Age                   | 54 (46, 67)    | Sex                    | Male: 43 (54%), Female: 37 (46%) |
| 6-Min Walk Distance   | 340 (250, 410) | WHO functional class    | I: 2 (2.6%), II: 11 (14%), III: 49 (63%), IV: 16 (21%) |
| Unknown               | 35             | Unknown                | 2      |
| BNP Level            | 453 (83, 774)  | PTE                    | 19 (27%) |
| Unknown               | 53             | Unknown                | 9      |
| LCC Volume           | 12.4 (8.9, 15.6) | Cardiac Index          | 2 (2, 3) |
| Unknown               | 45             | Unknown                | 45     |
| Mean DLA             | 50 (46, 55)    | -                      | -      |
| Unknown               | 43             | -                      | -      |

To investigate the relationship between prognosis and several anamnestic factors measured at the start of treatment, multiple missing data imputation was performed for all predictors with less than 60% of missing values. The obtained dataset contained information about 55 different parameters of interest. Due to relatively small amount of deceased patients (18 people, 22.5%) we decided to use as an outcome not only time do death (OS), but also time to first clinical deterioration (TTCD) or the rate of such deterioration (CD count).

*Table 2.* Prognostic factors for analysis 
| Category                          | Type        | Variables |
|-----------------------------------|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Demographics**                  | **Numerical**  | Age |
|                                   | **Categorical** | Sex, WHO functional class |
| **Metabolic indicators**          | **Numerical**  | BNP Level, Blood Glucose, Total Cholesterol, Triglycerides, HDL Cholesterol, LDL Cholesterol, Uric Acid |
| **Heart function**                | **Numerical**  | ECHO TAPSE, ECHO PP Area, ECHO Front-Back Size, ECHO SDL Area, ECHO DZ Area, DPP Mean, SDL Area, DZ Area, Cardiac Index, LCC Volume, Arterial Oxygen Saturation, Venous Oxygen Saturation |
|                                   | **Categorical** | Tricuspid regurgitation degree |
| **Disease symptoms**              | **Numerical**  | 6-Min Walk Distance, Apnea Borg Scale, Pulse Ox Before Test, Pulse Ox After Test |
|                                   | **Categorical** | Dyspnea on exertion, Increased fatigue, Chest pain, Dizziness, Syncope, Cough, Leg swelling, WHO functional class, CHF Decompensation |
| **Medical history**               | **Categorical** | Hypertension, Ischemic heart disease, Chronic obstructive pulmonary disease, Bronchial asthma, Obstructive sleep apnea syndrome, Antiphospholipid syndrome, Systemic lupus erythematosus, Diabetes or impaired glucose tolerance, Chronic kidney disease stage 3A or higher, Atrial fibrillation or atrial flutter (any form), candidate for TPE, candidate for BPA |
| **Prior medications** (not PAH specific therapy) | **Categorical** | Diuretic drug, Anticoagulant therapy |

For all predictors and outcomes, univariate Cox or Negative-Binomial models were created and ranged based on p-value within the group with the same type of outcome. Three factors included in top 10 models with lowest p-value for all 3 outcomes were: Leg edema (OS HR with 95%CI: 2.34 [0.9-6.05]; TTCD HR with 95%CI: 2.05 [1.19-3.53];  CD count RR with 95%CI: 2.33 [1.35-4.04]), symptoms of CHF decompensation (OS HR with 95%CI: 2.17 [0.83 - 5.68], TTCD HR with 95%CI: 1.76 [1.01 -3.05];  CD count RR with 95%CI: 1.79 [1.02-3.16]) and Cholesterol levels (OS HR with 95%CI: 0.52 [0.3-0.9]: , TTCD HR with 95%CI: 0.71 [0.5-1];  CD count RR with 95%CI: 0.65 [0.47-0.9]). Given that leg edema is one of CHF decompensation symptoms we proposed two major groups of anamnestic prognostic factors for further investigation: level of cholesterol and CHF decompensation symptoms. However, it should be noted, that after BH corrections for multiple testing, none of the p-values were significant.

Time-dependent Cox models adjusted for sex, age, and Leiden/prothrombin gene mutations showed no significant associations with OS. For BPA surgery (HR [95% CI]: 7.93 [3.75-16.76], p < 0.001) and PAH therapy (HR [95% CI]: 4.00 [1.65-9.71], p < 0.01) higher risk of deterioration was revealed compared with other treatment options.

**Discussion**
The study demonstrated that POLET registry data aligns with international CTEPH registries [5,6]. Most patients had WHO functional class III at diagnosis, and less than half were eligible for PTE. The rest underwent BPA and/or pulmonary arterial hypertension (PAH) therapy. Despite these treatment limitations, the five-year survival rate in our cohort was approximately 80%, a relatively high level compared to global standards.
A key finding was the identification of cholesterol levels and CHF decompensation symptoms as potential prognostic markers. While cholesterol is linked to cardiovascular risk, its role in CTEPH prognosis remains unclear and may be influenced by metabolic comorbidities. CHF decompensation symptoms correlated with worse outcomes, emphasizing the need for early heart failure management.
The observational nature of our study limits direct comparisons between treatment groups. Patients receiving PAH therapy or BPA were, in effect, compared to those undergoing PTE. Our results do not suggest that BPA and PAH therapy worsen prognosis but rather that PTE recipients tend to have better outcomes. This may reflect patient selection biases, as some experienced deterioration due to PTE ineligibility or were undergoing preliminary treatment before surgery.
Several limitations should be acknowledged: non-random patient selection, small sample size, missing data, and dynamic calculation of clinical deterioration, which may introduce variability. As mortality data accumulate, future analyses will provide a more robust assessment of survival outcomes and treatment effects, underscoring the need for continued research to refine risk stratification and improve CTEPH management.


**References** 

1. Inami, Takumi et al. “A new era of therapeutic strategies for chronic thromboembolic pulmonary hypertension by two different interventional therapies; pulmonary endarterectomy and percutaneous transluminal pulmonary angioplasty.” PloS one vol. 9,4 e94587. 11 Apr. 2014, doi:10.1371/journal.pone.0094587

2. Therneau T (2024). A Package for Survival Analysis in R. R package version 3.8-3, https://CRAN.R-project.org/package=survival.

3. Jackman S (2024). pscl: Classes and Methods for R Developed in the Political Science Computational Laboratory. University of Sydney, Sydney, Australia. R package version 1.5.9, https://github.com/atahk/pscl/.

4. Guth S et al. Current strategies for managing chronic thromboembolic pulmonary hypertension: results of the worldwide prospective CTEPH Registry. ERJ Open Res. 2021 Aug 16;7(3):00850-2020.

5. Ghofrani HA et al. Riociguat treatment in patients with chronic thromboembolic pulmonary hypertension: Final safety data from the EXPERT registry. Respir Med. 2021 Mar;178:106220.

6. van Buuren S, Groothuis-Oudshoorn K (2011). “mice: Multivariate Imputation by Chained Equations in R.” Journal of Statistical Software, 45(3), 1-67. https://doi.org/10.18637/jss.v045.i03. 
A case-control study. Psychiatry and clinical neurosciences, 74(2), 112–117. https://doi.org/10.1111/pcn.12944;

8. Khan, W. I., & Ghia, J. E. (2010). Gut hormones: emerging role in immune activation and inflammation. Clinical and experimental immunology, 161(1), 19–27. https://doi.org/10.1111/j.1365-2249.2010.04150.x.
