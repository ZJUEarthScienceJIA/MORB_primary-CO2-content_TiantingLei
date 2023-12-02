# Overview
This repository contains data source and codes used in the paper entitled “Prediction of CO2 content in oceanic basalts via machine learning approach” by T. Lei et al. We constructed a supervised machine learning (ML) model capable of accurately predicting CO2 concentrations in individual mid-ocean ridge basalts (MORBs) based on selected elemental concentrations of the compiled undegassed MORB glasses and melt inclusions (MIs) dataset. Our findings underscore the potential of ML as a powerful tool to uncover hidden structural patterns in complex geological data, shedding light on the intricate interplay between carbon, mantle composition, and Earth's long-term geological processes. We compiled 3 data sources and 1 code to generate the diagrams in Fig. 1-Fig. 3 and Table 1, and supplementary figures and tables. Here is the list of data and code files.

# Data files
This file contains model dataset, implication dataset and results for ML. 
1. Model dataset -- This file contains two tables. The first table (named ‘model_dataset’) is the model dataset, encompassing CO2 content, sampling depth, major elements (SiO2, TiO2, Al2O3, FeOT, MnO, MgO, CaO, Na2O, K2O, and P2O5), and trace elements (Rb, Nb, Ba, La, Ce, Sm, Th and U) for the MORB glasses and MIs without significant degassing from previous publications. While all sample data contain CO2 content and nearly complete major element data, some trace elements are missing for a portion of the samples. Samples with a sum of major elements content less than 95% or significant deficiencies in selected trace elements (Rb, Nb, Ba, La, Ce, Sm, Th and U) were filted out to exclude unreliable samples. We used the stratified random sampling approach with a sampling error reduction function to randomly split the whole model dataset into a training dataset (90%) and a testing dataset (10%) with the hold-out method. And the second table (named ‘test_data_result’) lists the predicted results of the testing dataset.
2. Implication dataset -- This file contains one table, named ‘implication_dataset’. We compiled global composition of MORB glasses and melt inclusions data for missing initial CO2 data (called on ‘implication’ data, n = 4970), which were filtered out for significant deficiencies in the major (a sum of major elements content less than 95%) and selected trace elements (Rb, Nb, Ba, La, Ce, Sm, Th and U), enable more accurate predicts the concentration of CO~2~ in MORB prior degassing via the ML model.
3. Case validation dataset -- This file contains three tables and they contain the geochemistry data of the MORB cases, which are used to validation the reliability of our ML model. In the first table (named ‘Gakkel_DMORB’), sample 13-1_18 D-MORB (depleted MORB) shows the highest measured CO~2~ content of the MORBs from Shaw et al. (2010) and consistent with the calculated CO2 contents of primary undegassed melts based on their melting model, which was suggested to degas least or even undegas (Shaw et al., 2010). The second table (named ‘Indian_EMORB’) contains the geochemistry data the Dr 30 MORBs. Zhou et al. (2022) report the definitive samples of pyroclastic debris sampled from a cratered terrain on the SWIR and they are the result of shallow mixing of an alkaline magma with entrained MORB crystal mush from beneath the flank of a rift valley. Including samples’ vesicularity and assuming the vesicles contained only CO2, the Dr 30 lavas and scoria have total CO~2~ at the depth of eruption ranging from 0.79 wt% to 4.10 wt% (Zhou et al., 2022).In the third table (named ‘Pacific_DMORB_and_EMORB_mantle’), sample GL08-73-4 D-MORB, trace element depleted but isotopically enriched, shows the highest measured CO2/Ba ratio of the MORBs from Shimizu et al. (2023) and was suggest to the most reliable pre-degassed sample (Shimizu et al., 2023). And they recovered CO2/Ba ratio of the Pacific E-MORB (enriched MORB) mantle source with combining the highest CO2/Ba ratio and a model that considers near-fractional melting of mantle sources. Based on the Pacific E-MORBs data from Shimizu et al. (2023), we use ML to predict the primary CO2/Ba ratio for the Pacific E-MORB mantle source.

# Code files
XGBoost_main.py – This file contains the code of model training using the ML algorithms of Extreme Gradient Boosting (XGBoost), prediction via ML model.

# Requirements
The codes used in this paper were compiled on the Python 3.11. 
	
# Contributions
Tianting Lei\Email : leitt1106@zju.edu.cn

