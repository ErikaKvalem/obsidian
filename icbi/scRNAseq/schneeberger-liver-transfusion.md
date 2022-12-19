---

mindmap-plugin: basic

---

# analyses

## 01_make_h5ad.py

## 03_scvi.py
- Read annotated data
   - path to annotated data
   - read h5ad
- Select the cpus to be used
- Annotate highly variable genes
   - scanpy.pp.highly_variable_genes
- Summary of associated AnnData
   - scvi.data.view_anndata_setup(model.adata)
- Mapping will be created between data fields used by scvi to their respective locations in adata
   - scvi.data.setup_anndata
      - Per batch
         - Compute log mean
         - Compute log variance
- Single-cell Variational Inference
   - scvi.model.SCVI
- Standard scanpy preprocessing (for comparison)
   - sc.pp.normalize_total
   - sc.pp.log1p
   - sc.tl.pca
- Compute a neighborhood graph of observations
   - sc.pp.neighbors
- ...

## 04_cell_type_annotation

## 10_myeloid_analysis

## 11_neutro_analysis.py

## 12_nk_and_t_analysis.py

## 20_de_analysis.py

## 40_t0_vs_t1.py

## 41_liver_quality.py

## 90_overview_plots.py

## CONCEPTS
- Scanpy
   - AnnData
      - Object: adata
         - matrix (pd dataframe): adata.X
         - annotation (pd dataframe): adata.obs
            - access: adata.obs_names
         - variables (pd dataframe):adata.var
            - access: adata.var_names
         - unstructured annotation (dict) : adata.uns
   - anndata.AnnData
      - parameters
         - obsm
            - Key-indexed multi-dimensional observations annotation of length number of observations.