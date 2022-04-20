# rIBD_WUR

**Authors: Zhou Wu & Langqing Liu**

## What does this repository do?
- Calcuate the relative haplotype sharing (rIBD) between three populations(A, B and C)

> Normalized IBD for one  group: nIBD=cIBD/tIBD (where cIBD=count of all haplotypes IBD between A and one group (B or C) and tIBD=total pairwise comparisons between A and one  group).
>
> rIBD between two pig groups: rIBD=nIBD<sub>AB</sub> – nIBD<sub>AC</sub>
>
> Adopted from *[Bosse, M. et al.(2014)](https://www.nature.com/articles/ncomms5392)*

- Codes in this repository

`Beagle_phasing_IBD_calling.sh` This code shows an example of using Beagle to perform the **phasing** and IBD calling

`rIBD_pd.py` This code shows an example of using the python code to compute the **rIBD**

`plot_rIBD.R` This code shows an example of **plotting** the outcome of the pyton codes 

## rIBD between population A,B, and C
<p align="center">
  <img src="https://github.com/wzuhou/rIBD_WUR/blob/main/Github_rIBD.png">
</p>

## How to use it? Prepare your input and env.
### Dependence: 
- python >= v3 (Tested in v3.8.5)
- python modules: pandas, pybedtools
- R 
- R package: ggplot2, gridExtra

### Example
```bash
python rIBD_pd.py -i Example/test_chr6.ibd -A Example/List.DrFwB -B Example/List.DB -C Example/List.DrFw -o rIBD_DrFwB_DB_DrFw -W 20000 -S 10000 -M 1
#expected output: Example/rIBD_DrFwB_DB_DrFw
```

Example breeds:DrFw, DrFwB, DB
- Input files:
1. A ibd file generated by Beagle: test_chr6.ibd
2. Three list files(A,B,C): A: List.DrFwB, B: List.DB , C: List.DrFw

- Parameters
1. Window size (-W): 20,000 bp; 
2. Step size (-S): 10,000 bp

- Method options

> Method `1` corresponds to *[Bosse, M. et al.(2014)](https://www.nature.com/articles/ncomms5392)*
> 
> Method `2` computed the weighted cIBD in each window 

- Output format  
1.Chr 2.Start 3.End 4.rIBD 5. weighted rIBD

---

## Visualization of the result
### Example to plot

Here we highlight the candidate region on Chromosome 6: 10000000-11000000

```bash
Rscript plot_rIBD.R rIBD_DrFwB_DB_DrFw 6 10000000 11000000
```

**Arguments:**
1. Input rIBD file (Example: rIBD_DrFwB_DB_DrFw. **NB**: Whole genome output or a songle chromosome output? Both would be possible.)
2. Chromosome of interest
3. Start position for region to be highlighted (in bp)
4. End position for region to be highlighted (in bp)

Output files is plot: Chr_RIBD.pdf   (*Optional*) + WG_RIBD.pdf (Only when the input contains more than two chromosomes) 
