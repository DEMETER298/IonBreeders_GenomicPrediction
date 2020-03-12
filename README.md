# IonBreeders_GenomicPrediction version 1.0
Genomic prediction plugin for the Ion Torrent NGS platform.


[IonBreedersの使い方 日本語版 ver.1.0 ](https://github.com/DEMETER298/IonBreeders_GenomicPrediction/wiki)


# 1. Installation Instructions

## Download plugins
 The GenomicPrediction plugin of IonBreeders is provided as a zipped package containing files from the Latest Release project page on Github. The file name will be of the format IonBreeders_GenomicPrediction.zip.
1. Click the **`IonBreeders_GenomicPrediction.zip`** in the upper right and it will be displayed below **`View raw`** 
2. Click the **`View raw`** and save the zip file to you local computer. (right click on the Windows, one click on the Mac)
3. Don't unzip the downloaded IonBreeders_GenomicPrediction.zip file.

## Install

Automatic installation from the Torrent Browser Plugin

Follow these steps for automatic installation of a plugin from the Torrent Browser:
1.	In your Torrent Browser, click the gear menu (near the top right) and select Plugins

![1](https://user-images.githubusercontent.com/40309394/54818632-14aee380-4cdd-11e9-845c-7c7d8ac95a1f.png)
  
2.	In the Plugins tab, click the **`Install or Upgrade Plugin`** button: 

![2](https://user-images.githubusercontent.com/40309394/54819228-8fc4c980-4cde-11e9-92ba-1d4b64e70e64.png) 

3.	In the **`Install or Upgrade Plugin`** tab, select IonBreeders_GenomicPrediction.zip file, and click **`Upload and Install`**.  
 
![3](https://user-images.githubusercontent.com/40309394/54819317-e29e8100-4cde-11e9-91a8-3873b1263a93.png)



# 2. Plugin manuals
## 2-3 GENOMIC PREDICTION plugin
### 2-3-1 Function
(1)	Remove non-informative markers such as those with high missing rates and low allele frequencies. Missing genotype are input as the mean value of each marker.

(2)	Predict genetic values from the genotype data by constructing a GS model from the phenotyped and genotyped training population.

2-3-2 Input files
Prepare the marker genotype data of the training population and prediction target sample in CSV format as follows:  
Test data can be downloaded from [main page](https://github.com/DEMETER298/IonBreeders). Missing data should be descriped in "-" or "NA".


Prepare the genotype data for training.  
![image](https://user-images.githubusercontent.com/40309394/54862816-71fd7000-4d83-11e9-984d-ea21514f11e7.png)AA/AB/BB format (IMPUTATION output)  `ak_genotype_output_training.csv` 
  
![image](https://user-images.githubusercontent.com/40309394/54862819-7aee4180-4d83-11e9-938d-cd5c589c781f.png)A/B/H format 
      


Prepare the phenotypic data of the training sample as a CSV file in the following format:  
![image](https://user-images.githubusercontent.com/40309394/70031653-12808100-15ef-11ea-9df6-ae27ea4d472d.png) `ak_phenotype_training.csv`


Prepare the marker genotype data for prediction:
If you input AA/AB/BB genotype data for training, input same format genotype file for prediction as follow.`ak_genotype_output_test.csv`
![genotypeforprediction](https://user-images.githubusercontent.com/40309394/70032294-8cfdd080-15f0-11ea-8131-129a94d6f785.png)

3.	Execution:

(1)	From the list of plugins, click IonBreeders_GenomicPrediction.

(2)	Set each item on the screen as shown below.

![19](https://user-images.githubusercontent.com/40309394/70031556-d51bf380-15ee-11ea-932e-3130d69a6c94.png)




`Add text at the beginning of the sample name`: Add the sample name before the sample number.	

`Upper limit of fraction of missing data per marker`: Enter a value between 0.0 and 1.0; the default in 0.2.

`Lower limit of minor allele frequency per marker`: Enter a value between 0.0 and 1.0; the default is 0.

`Phenotype`: Select the phenotype from the Available Phenotype column.	

`GS Method`: Select the method among the options RR-BLUP(GBLUP), RKHS(Gaussian Kernel), LASSO, Linear Model, and Linear Model with Interaction (see description of each method below).

`Genotype input format`: Select the input file format from A/B/H or AA/AB/BB; default = AA/AB/BB:IMPUTATION output format.

`Training data (genotype)`: Select the genotype file for training (CSV format).	

`Training data (phenotype)`: Select the phenotype file for training (CSV format).		

`Genotype data for prediction`: Select the genotype file for prediction (CSV format).

`Add text at the beginning of the output file name`: Enter the desired file name.

(3)	Output
When execution is completed, the following items are displayed on the screen.

![20](https://user-images.githubusercontent.com/40309394/70030505-b3ba0800-15ec-11ea-99f5-f73b5b4c160f.png)

 
input files

`training_genotype.csv`: input training genotype file

`phenotype_training.csv`: input training phenotype file

`target_genotype.csv`: input genotype file for genetic prediction

`Training data (phenotype, tab-delimited)`: list of phenotypes of the training data.

[Results] 

`rice_rootpheno_1_out.csv`: output predicted value (CSV file) shown below.
 
![image](https://user-images.githubusercontent.com/40309394/70030240-21196900-15ec-11ea-95b6-0e793fcbe497.png)


**GS METHODS**

`RR-BLUP`:
We recommend this method when the trait is controlled by several QTLs with additive effects.

`RKHS`:
We recommend this method when the trait is controlled by several QTLs with additive and non-additive (e.g., epistatic) effects.

`LASSO`: We recommend this method when the trait is controlled by only a few or a small number of QTLs with additive effects.

`LM`: We recommend this method when the trait is controlled by a small number of KNOWN QTLs with additive effects.

`LM with Interaction`:
We recommend this method when the trait is controlled by a small number of known QTLs with interaction effects.

(4)	Output contents

When execution is completed, the following items are displayed on the screen.
 
![image](https://user-images.githubusercontent.com/40309394/54862697-d7506180-4d81-11e9-94f9-f2fbdd9164d0.png)


***

# Contact
Eri Ogiso-Tanaka, Ph.D. demeter@affrc.go.jp

Institute of Crop Science / National Agriculture and Food Research Organization
2-1-2, Kannondai, Tsukuba, Ibaraki 305-8518, Japan

# Version
Version 1.0

# Citing IonBreeders
Ogiso-Tanaka E, Yabe S and Tanaka T (2019) in press

**IonBreeders: semi-automated bioinformatics plugins toward genomics-assisted breeding.**

# License
NARO NON-COMMERCIAL LICENSE AGREEMENT Version 1.0

This license is for 'Non-Commercial' use of software for IonBreeders.

1. Scientific use of IonBreeders is permitted free of charge.
2. Modification of IonBreeders is only permitted to the person of downloaded and his colleagues.
3. The National Agriculture and Food Research Organization (hereinafter referred to as NARO) does not guarantee that defects, errors or malfunction will not occur with respect to IonBreeders.
4. NARO shall not be responsible or liable for any damage or loss caused or be alleged to be caused, directly or indirectly, by the download and use of IonBreeders.
5. NARO shall not be obligated to correct or repair the program regardless of the extent, even if there are any defects of malfunctions in IonBreeders.
6. The copyright and all other rights of IonBreeders belong to NARO.
7. Selling, renting, re-use of license, or use for business purposes etc. of IonBreeders shall not be allowed. For commercial use, license of commercial use is required. Inquiries for such commercial license are directed to demeter@affrc.go.jp.
8. The IonBreeders may be changed, or the distribution maybe canceled without advance notification.
9. In case the result obtained using IonBreeders in used for publication in academic journals etc., please refer the publication of IonBreeders in the publication (in preparation).


Copyright (C) 2019 [National Agriculture and Food Research Organization](https://www.naro.affrc.go.jp/english/index.html). All rights reserved.
