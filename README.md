# rIBD_WUR
test
**Authors: Langqing Liu & Zhou Wu**
## What does this repository do?
- Codes in this repository

`Beagle_phasing_IBD_calling.sh` This code shows an example of using Beagle to perform the **phasing** and IBD calling

`rIBD_pd.py` This code shows an example of using the python code to compute the **rIBD**

`plot_rIBD.R` This code shows an example of plotting the outcome of the pyton codes **this code is to be added to the repository**

### rIBD between population A,B, and C
<p align="center">
  <img src="https://github.com/wzuhou/rIBD_WUR/blob/main/Github_rIBD.png">
</p>

## How to use it?

### Prepare your input and env.

Example breeds:DrFw, DrFwB, DB
-Input files:
1. A ibd file generated by Beagle: LOD3_gal6_Merged.rnm.beagle.vcf.gz.10k.filtered.recode.phased_B5.vcf.gz.ibd
2. Three list files(A,B,C): List.DrFwB , List.DrFw, List.DB

`python rIBD.py -i example/LOD3_gal6_Merged.rnm.beagle.vcf.gz.10k.filtered.recode.phased_B5.vcf.gz.ibd -A example/Tibetan.list -B example/Zebu.list -O example/Yak.list -o Tibetan-Zebu-Yak.Chr28 -W 20000 -S 10000`


### Example

### Steps in the code
