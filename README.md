# Testing performance of standard sklearn classifiers on scRNA-seq dataset
The code was written from scratch in order to compare the performance of a number of models on a single cell RNA-sequencing dataset in a systematic way. I have designed the code to load and preprocess the data and the architecture in which the models are tested, the results are collected, displayed and visualized. 
Scikit-learn library was used to train and test machine learning models, Numpy and Pandas were used to work with the datastructures, Matplotlib and Mglearn were used to visualize the results. 

![image](https://user-images.githubusercontent.com/78618639/168481847-bd5f6db7-c6ad-4aff-8acd-ae9ec8560606.png)

_Figure 1. Visual representation of the performance of different algorithms on the AMB dataset._

The selection of the models and the hyperparameters to test is the result of the group work with Maxymillian Martys and Marijn Vroegh within the course Jung, M., Saygili, G., Stowell, D., Zamberlan, F. & Schmalzried, D. (2022). 

The dataset used contains single cell RNA sequencing data. I’ve chosen this data because I find molecular biology fascinating and I’m actually taking a number of biology courses just for fun. The dataset is Allen Mouse Brain (AMB), as preprocessed by Michielsen, Reinders & Mahfouz (2021, p. 11), available here https://zenodo.org/record/4557712 . For my research project I also used the code for the second dataset from the same repository, PBMC-FACS, but because the code is almost the same (for the research purposes I use the same procedure for different data), I decided to not include it here. 

The idea of this research project was to see how accurate would be the readily available ML algorithms with the low accessibility threshold (free of charge, no calculus required, only basic programming required) in the task of scRNA-seq data classification. The state-of-the-art architectures like the hierarchical progressive learning classifier by Michielsen, Reinders & Mahfouz, specifically designed for this type of data, are, of course, preferable, but might be more challenging. If the task at hand requires the performance demonstrated by these more accessible models than one could use them instead. 

For comparison of more algorithms on a bigger sample of datasets see Huang & Zhang (2021). 

The limitations of the code is that more things should have probably been measured in a systematic way. One could run every tuned algorithm multiple times on some sample of the data and then measure the mean time. The GridSearchCV() does include the mean train and mean test computational time data, however this data was slightly different from what is measured and recorded by the code now. More research is needed in order to see if this difference is significant and what is its nature (the inner functioning of GridSearchCV() should then be uncovered more in detail, for example). I decided to not use the GridSearchCV() metrics and measure the time on my own because this way the process of measurement is more transparent, it’s transparent what is measured (the documentation on GridSearchCV() does not include the description of what time is actually measured). 

![image](https://user-images.githubusercontent.com/78618639/168481964-8f39fad1-96e9-4ddc-928c-f42828eee952.png)

_Figure 2. Algorithms ranked according to computational time needed for training on the AMB dataset._

References:

Jung, M., Saygili, G., Stowell, D., Zamberlan, F. & Schmalzried, D. (Feb. - Jul. 2022). Research Workshop CSAI [university course]. Bachelor program Cognitive Science and Artificial Intelligence, Tilburg University, The Netherlands.

Huang, Y., & Zhang, P. (2021). Evaluation of machine learning approaches for cell-type identification from single-cell transcriptomics data. Briefings in Bioinformatics, 22(5), https://doi.org/10.1093/bib/bbab035 

Michielsen, L., Reinders, M. J., & Mahfouz, A. (2021). Hierarchical progressive learning of cell identities in single-cell data. Nature communications, 12(1), 1-12.
