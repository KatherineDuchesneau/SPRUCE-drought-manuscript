# SPRUCE Drought Manuscript Analysis Code

Manuscript: Combined effects of warming and drought accelerate microbially
mediated organic matter decomposition and suppress methanogenesis in peatlands
Authors: Katherine Duchesneau et al.
Journal: Nature Communications, NCOMMS-26-018889-T
Code DOI (Zenodo): 10.5281/zenodo.19865237

## How to run

1. Set `PROJ` at the top of `Drought_Manuscript_Analysis.Rmd` to your local
   path. It is the only absolute path in the document.
3. Knit `Drought_Manuscript_Analysis.Rmd`. It runs top to bottom and reads
   nothing from outside `2Revisions_out/00_inputs/`.

## Run switches, all at the top of the setup chunk

REFIT_MAASLIN   refit every Maaslin2 model from the phyloseq objects
REFIT_LARGE     also refit the two large gene models (hours to overnight)
MAASLIN_CACHE   skip a refit when the stored fit matches the same inputs
RUN_NETWORK     TRUE fits SpiecEasi, FALSE reloads 08_network/se_FULL.RDS
RESAMPLE_N      replicate count behind the Figure 3 edge-recovery input
RUN_RESAMPLE    TRUE recomputes edge recovery when the plotted edge set no
                longer matches 00_inputs/Check_Fig3_edge_stability.csv;
                FALSE stops the knit
WIPE_OUTPUTS    delete 01_ to 08_ before the run; 00_inputs is never touched

## Files

Drought_Manuscript_Analysis.Rmd   all analyses, figures and tables
Drought_R_analyses.Rproj          RStudio project

## Folders

2Revisions_out/   the whole analysis, inputs and outputs
  00_inputs/      every file the Rmd reads
  01_metadata/    merged metadata, NOSC, porewater gas, enzyme, CAMPER counts
  02_phyloseq/    phyloseq objects this script creates
  03_maaslin/     every Maaslin2 fit
  04_suppl_data/  Supplementary Data 1-18
  06_figures/     all main and supplementary figure PDFs, named as they are
                  cited: Figure_1 to Figure_6, Figure_S1 to Figure_S9
  08_network/     SpiecEasi fit, association matrix, linking tables, Figure 3

## Supplementary Data

01 environmental, porewater and annual CH4 flux mixed models
02 enzyme activity mixed models
03 metabolite feature responses to water table drawdown
04 metabolite feature responses to temperature
05 class-level competitive tests on the metabolite coefficients
06 MAG taxonomy and genome quality
07 VIF for all dbRDA models
08 clustered MAG responses to temperature, water table and NOSC
09 cytochrome c gene responses to temperature in WS-OX genomes
10 metabolites linking warming-responsive MAGs to methanogens (Figure 3)
11 hydrogenase gene responses in WS-AN genomes, HydDB annotated
12 phenol-active gene responses in WS-OX genomes (Figure 4A)
13 phenol-active gene responses in WS-AN genomes (Figure 4B)
14 gene responses to temperature in methanogen-connected genomes (Figure 5)
15 methanogen KEGG module presence (hand-curated, copied from 00_inputs)
16 per-MAG mcrA models (Figure 6A)
17 phenol-active gene responses in methanogens (Figure 6B)
18 custom KEGG module definitions (hand-curated, copied from 00_inputs)

## Figures

Figure_1_dbRDA.pdf                        assembled four-panel Figure 1
Figure_1A_MAG_activity.pdf                MAG activity dbRDA
Figure_1B_metabolites.pdf                 metabolite composition dbRDA
Figure_1C_16S.pdf                         16S community dbRDA
Figure_1D_ITS.pdf                         ITS community dbRDA
Figure_2A_genome_response_tree.pdf        MAG responses on the phylogeny
Figure_2B_CO2_genome_scatter.pdf          porewater CO2 against genome group
Figure_2C_phylogenetic_tree.pdf           294 MAGs, phenol-active gene counts
Figure_3_network.pdf                      SpiecEasi metabolite-informed network
Figure_4A_WSOX_phenolic_genes.pdf         phenol-active gene responses, WS-OX
Figure_4B_WSAN_phenolic_genes.pdf         phenol-active gene responses, WS-AN
Figure_5_KEGG_enrichment.pdf              KEGG pathway enrichment
Figure_6A_mcrA_water_table.pdf            mcrA transcripts against drawdown
Figure_6B_methanogen_phenolic_genes.pdf   phenol-active genes in methanogens
Figure_S1_environmental_drivers.pdf       water table, moisture, temperature
Figure_S2_porewater_gas.pdf               porewater CO2, CH4 and their ratio
Figure_S3_enzyme_activity.pdf             phenol oxidase and hydrolase assays
Figure_S4_MAG_abundance_dbRDA.pdf         MAG relative abundance dbRDA
Figure_S5_cytochrome_c.pdf                cytochrome c genes in WS-OX genomes
Figure_S6_central_metabolism_genes.pdf    K00382, K01915 and K00873
Figure_S7_peptide_amino_acid_carbohydrate.pdf  class mean intensity by temperature
Figure_S8_methanogen_activity.pdf         porewater CH4 against methanogen activity
Figure_S8C_methane_flux.pdf               annual CH4 emission by year
Figure_S9_variation_partitioning.pdf      varpart Venn diagrams


