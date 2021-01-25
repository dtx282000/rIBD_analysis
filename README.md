# rIBD_WUR

**Authors: Langqing Liu & Zhou Wu**

## What does this repository do?
- Codes in this repository

`Beagle_phasing_IBD_calling.sh` This code shows an example of using Beagle to perform the **phasing** and IBD calling

`rIBD_pd.py` This code shows an example of using the python code to compute the **rIBD**

`plot_rIBD.R` This code shows an example of plotting the outcome of the pyton codes **this code is to be added to the repository**

## rIBD between population A,B, and C
<p align="center">
  <img src="https://github.com/wzuhou/rIBD_WUR/blob/main/Github_rIBD.png">
</p>

## How to use it? Prepare your input and env.
### Dependence: 
- python > v3 (Tested in v3.8.5)
- python modules: pandas, pybedtools
- R 
- R package: ggplot2

### Example

Example breeds:DrFw, DrFwB, DB
- Input files:
1. A ibd file generated by Beagle: LOD3_gal6_Merged.rnm.beagle.vcf.gz.10k.filtered.recode.phased_B5.vcf.gz.ibd
2. Three list files(A,B,C): A: List.DrFwB, B: List.DB , C: List.DrFw

- Parameters
1. Using the method option: 1, which corresponds to *Bosse, M. et al.(2014)*
4. Window size: 20,000 bp; step size: 10,000 bp

`python rIBD.py -i Example/LOD3_gal6_Merged.rnm.beagle.vcf.gz.10k.filtered.recode.phased_B5.vcf.gz.ibd -A Example/List.DrFwB -B Example/List.DB -C Example/List.DrFw -o rIBD_DrFwB_DB_DrFw -W 20000 -S 10000 -M 1` 


### Steps in the code
