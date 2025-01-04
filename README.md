# Single-Cell RNA Sequencing Analysis Pipeline for Gastric Cancer (in progress)

## Project Overview
This repository presents an advanced computational pipeline for analyzing single-cell RNA sequencing (scRNA-seq) data from gastric cancer samples. Our analysis framework builds upon and extends the methodologies discussed in recent gastric cancer research, particularly focusing on the GEO dataset GSE158631. The pipeline integrates state-of-the-art techniques for cell population identification, gene expression analysis, and pathway enrichment.

## Key Features
- Comprehensive preprocessing and quality control
- Multi-modal dimensionality reduction analysis
- Advanced clustering algorithms implementation
- Automated marker gene identification
- Gene Ontology (GO) enrichment analysis
- Interactive visualization tools
- Reproducible workflow

## Installation and Setup

### Clone the Repository
```bash
git clone git@github.com:BulutHamali/scRNAseq-Pipeline-GastricCancer.git
```

Dependencies
Required Python packages:

-pandas (data manipulation)
-numpy (numerical computations)
-scanpy (single-cell analysis)
-anndata (annotated data)
-matplotlib & seaborn (visualization)
-scikit-learn (machine learning)
-umap-learn (dimensional reduction)
-scipy (scientific computing)
-gprofiler-official (functional enrichment)

Install all dependencies:
```sh
pip install -r requirements.txt
```

Pipeline Components
1. **Data Processing Module**
```python
pythonCopyfrom src.preprocessing.data_processor import GastricCancerProcessor
processor = GastricCancerProcessor('data/raw/counts_matrix.csv')
processor.preprocess()
processor.normalize()
processor.filter_cells()
```


2. **Dimensional Reduction**
```python
pythonCopyfrom src.analysis.dimension_reducer import DimensionReducer
reducer = DimensionReducer(processed_data)
reducer.run_pca()
reducer.run_umap()
reducer.run_tsne()
```

3. **Clustering Analysis**
```python
pythonCopyfrom src.analysis.cluster_analyzer import ClusterAnalyzer
analyzer = ClusterAnalyzer(reduced_data)
analyzer.perform_clustering(methods=['leiden', 'louvain', 'kmeans'])
analyzer.evaluate_clusters()
```
4. **Biological Interpretation**
```python
pythonCopyfrom src.analysis.gene_analyzer import GeneAnalyzer
gene_analyzer = GeneAnalyzer(clustered_data)
gene_analyzer.find_markers()
gene_analyzer.perform_go_analysis()
```


## Documentation

Detailed tutorials and examples can be found in the 'analysis' directory
Pipeline results are stored in the 'results' directory
Documentation for each module is available in the 'documentation' directory

### Project Structure
```sh
scRNAseq-Pipeline-GastricCancer/
├── analysis/                # Analysis notebooks and scripts
├── data/                   # Data directory
│   ├── raw/               # Raw count matrices and metadata
│   └── processed/         # Processed and normalized data
├── results/               # Analysis results
│   ├── figures/          # Generated visualizations
│   └── tables/           # Statistical outputs and gene lists
├── src/                   # Source code
│   ├── preprocessing/    # Data preprocessing modules
│   ├── analysis/        # Core analysis functions
│   └── visualization/   # Plotting and visualization tools
└── documentation/         # Project documentation and reports
```

## Contributing
Contributions to improve the pipeline are welcome. Please read the contribution guidelines before submitting pull requests.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
Based on scRNA-seq data from GEO (GSE158631)
Inspired by current methodologies in single-cell analysis
Developed using open-source bioinformatics tools

## Author
Bulut Hamali

## Contact
For questions or collaboration opportunities, please open an issue or contact through GitHub.




