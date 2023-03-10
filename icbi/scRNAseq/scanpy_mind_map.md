---

mindmap-plugin: basic

---

# scanpy

## Preprocessing and clustering 3k PBMCs
- PBMCs
   - Human peripheral blood mononuclear cells (PBMCs)
- Healthy donor

## AnnData object
- Read count matrix
- anndata
   - matrix-like data
      - nxd
   - n observations
      - d-dimensional vectors
         - each dimension = variable/feature
   - indexed n row &  d columns
   - e.g scRNA-seq
      - row  = cell (barcode)
      - column = gene (gene id)
      - For each cell & gene
         - Metadata
            - donor info
            - alternative gene symbol
      - Unstructured metadata

## color palettes
-
-
      -
      - 1. Handle sparsity (matriz dispersa)
      -
-
      -
      - 2. Handle unstructured data
      -
-
      -
      - 3. Handles observation & feature-level metadata
      -
-
   - 4. User friendly
- [anndata tutorial documentation](https://anndata-tutorials.readthedocs.io/en/latest/getting-started.html)