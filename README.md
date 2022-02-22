# SLAMD-FIB-Case-Study

This repository contains the underlying source data and results for the use case presented at the FIB conference 2022. 

## Title: ACCELERATING THE SEARCH FOR ALKALI ACTIVATED CEMENTS WITH SEQUENTIAL LEARNING 

Christoph Völker1), Sabine Kruschwitz1,2),  Benjami Moreno Torres1),  Ghezal Ahmad Zia1),  Rafia Firdous3), Dietmar Stephan3)
1) Bundesanstalt für Materialforschung und -prüfung, Unter den Eichen 87, 12205 Berlin, Germany
2) Technische Universität Berlin, Department of Civil Engineering, Non-destructive testing of building materials, Gustav-Meyer-Allee 25, 13355 Berlin, Germany
3) Technische Universität Berlin, Department of Civil Engineering, Building Materials and Construction Chemistry, Gustav-Meyer-Allee 25, 13355 Berlin, Germany


## Abstract

With 8% of man-made CO2 emissions, cement production is an important driver of the climate crisis. By using alkali-activated binders part of the energy-intensive clinker production process can be dispensed with. However, because numerous chemicals are involved in the manufacturing process here, the complexity of the materials increases by orders of magnitude. Finding a properly balanced cement formulation is like looking for a needle in a haystack. We have shown for the first time that artificial intelligence (AI)-based optimization of cement formulations can significantly accelerate research. 
The „Sequential Learning App for Materials Discovery“ (SLAMD) aims to accelerate practice transfer. With SLAMD, materials scientists have low-threshold access to AI through interactive and intuitive user interfaces. The value added by AI can be determined directly. For example, the CO2 emissions saved per ton of cement can be determined for each development cycle: the more efficient the AI optimization, the greater the savings. 
Our material database already includes more than 120,000 data points of alternative cements and is constantly being expanded with new parameters. We are currently driving the enrichment of the data with a life cycle analysis of the building materials. 
Based on a case study we show how intuitive access to AI can drive the adoption of techniques that make a real contribution to the development of resource-efficient and sustainable building materials of the future and make it easy to identify when classical experiments are more efficient.


## Description of the data

The data has been extracted from Xie et al. [1], who gave an extensive overview of alkali activated concrete mixes consisting of 1756 individual AAC mixes from 111 studies. The authors assess the influential features on the slump and mechanical properties of the mixes. They also propose an approach to assess the compressive strength of the hardened mixes according with the curing temperature.    The data contains the original reference, the concrete composition in terms of weight ratios of the precursors and detailed chemical information of the powders and activator substances. The activators considered in the compilation are the most used in the studies: Na2SiO3 as out-of-the-shelf dissolution and  NaOH. The features of the first activator are defined by the information provided for its commercial distribution, and the provided features defining the NaOH varies depending on the chosen way to add the substance to the mix (flakes or a dissolution in water made ex profeso) and which ones of the molarity / concentration / silica modulus are the variables of the scientific paper.
The types of powders included in the mixes are mainly flying ashes (FA) -with subclass divisions-, ground granulated blast furnace slag (GGBFS), silica fume (SF), metakaolin (MK), ordinary Portland cement (OPC) rice husk ashes (RHA), palm oil fuel ashes (POFA), etc. This binders are described in terms of the percentual molecular composition corresponding with the most common molecules found in this class of compounds (SiO2, Al2O3, Fe2O3, CaO, MgO, Na2O, K2O, SO3, TiO2, P2O5, SrO, Mn2O3)    and the loss on ignition (LOI).  These values come usually from a X-ray diffraction spectroscopy (XRD) conducted either by the researcher team or by the seller in case that any of these powders are commercially available. Also, the fine modulus and the specific gravity are included when available.
The mixing features consist of binder mass, binder density, aggregate mass and density, alkali activator proportions and amounts, superplasticizer amount, additional water amount, curing conditions (medium, temperature and time) and values that define the geometry and size of the specimen. 
For the SL task, the data were grouped into nine coherent subsets, each having common material descriptors and containing compressive strength data that refers to the same sample geometries and time points. The data sets are summarized in Table 2.
For each mix the CO2 emissions were calculated based on material composition and heat treatment, without considering logistical and transport-related emissions. The values are based on the following equation:

CO_2  emissions (kg/m^3 )=∑_i▒w_i ·m_i+(0.6417·T-16.0417)·t          				(1)

where:

wi   	CO2 emissions (kg) to produce 1 kg of the mix component i
mi   	mass of a mix component i in kg/m3 of fresh concrete
T  	Curing Temperature if higher than 25° Celsius
t 	Curing duration in days

The first part of the equation sums the carbon footprint wi weighted with the mass of the individual precursor materials qi . The underlying information was extracted from [2] and is summarized in Table 1. The second part of the equation represents the cumulative emissions from heat treatment. It is modeled as a simple linear function that contains the curing temperature T and duration t and is applied only to materials with a curing temperature higher than 25 degrees Celsius. 

OPC	Flying Ashes	GGBFS	Silica Fume	Metakaolin	Aggregates	Superplasticizer	NaOH  Dry	Na2SiO3 solution	Na2SiO3 Dry
w (kg/ m3)	0.84	0.004	0.052	0.014	0.33	0.0048	1.88	1.915	0.36	1.222
Table 1: CO2 footprint of in kg/m3 for the precursor materials. 

## References

[1] T. Xie, P. Visintin, X. Zhao und R. Gravina, „Mix design and mechanical properties of geopolymer and alkali activated concrete: Review of the state-of-the-art and the development of a new unified approach,“ Construction and Building Materials, p. 256 (2020) 119380; DOI: https://doi.org/10.1016/j.conbuildmat.2020.119380, 17. April 2020. 

[2] A. Alsalman, L. N. Assi, R. S. Kareem, K. Carter und P. Ziehl, „Energy and CO2 emission assessments of alkali-activated concrete and Ordinary Portland Cement concrete: A comparative analysis of different grades of concrete,“ Cleaner Environmental Systems, Bd. 3, Nr. 100047, p. https://doi.org/10.1016/j.cesys.2021.100047., 2021. 

