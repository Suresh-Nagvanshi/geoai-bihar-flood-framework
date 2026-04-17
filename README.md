# Bihar GeoAI Flood Framework

A geospatial AI pipeline for flood-risk prediction in Bihar using Google Earth Engine, multi-source raster features, and a U-Net-based segmentation model.

## Overview

This project builds a flood-risk framework for Bihar by combining elevation, monsoon rainfall, soil moisture, and urban land-cover rasters into aligned training patches. The model learns pixel-level flood labels from these inputs and produces flood susceptibility predictions for the region.

## Key Features

- Google Earth Engine-based data extraction.
- Multi-source raster alignment and patch generation.
- U-Net segmentation model for flood-risk mapping.
- Custom flood labeling logic based on terrain, rainfall, soil moisture, and urbanization.
- Training and evaluation workflow with metrics such as F1, IoU, PR-AUC, and Grad-CAM visualization.

## Data Sources

The framework uses geospatial layers such as:

- Elevation from SRTM.
- Monsoon rainfall from CHIRPS.
- Soil moisture from SMAP.
- Urban land cover from ESA WorldCover.
- Bihar administrative boundary from FAO GAUL.

## Repository Workflow

1. Mount Google Drive in Colab.
2. Authenticate Google Earth Engine.
3. Export raster layers to Drive.
4. Build aligned training patches.
5. Generate flood labels.
6. Train the segmentation model.
7. Evaluate performance and visualize outputs.

## Project Structure

```text
.
├── notebooks/
│   └── 02_gee_feature_export.ipynb
├── data/
│   └── processed/
├── models/
├── outputs/
└── README.md
```

## Installation

### Requirements
- Python 3.10+
- Google Colab or Jupyter Notebook
- Google Earth Engine account
- `rasterio`, `numpy`, `matplotlib`, `tensorflow`, `geemap`

### Example setup

```bash
pip install rasterio numpy matplotlib tensorflow geemap
```

## How to Run

### In Colab

1. Open the notebook.
2. Mount Google Drive.
3. Authenticate Earth Engine.
4. Run the export cells to create TIFF rasters.
5. Run the patch generator and training cells.

### Typical commands

```python
from google.colab import drive, auth
drive.mount('/content/drive')
auth.authenticate_user()
```

```python
import ee
ee.Authenticate()
ee.Initialize(project='your-project-id')
```

## Model Outputs

The project currently reports metrics including:

- F1 score
- IoU
- PR-AUC
- Grad-CAM coverage for monsoon contribution

## Results

Current experiments show strong flood-risk detection performance for the Bihar framework. Replace this section with your latest validated metrics and figures before final publication.

## Future Work

- Add more hydrometeorological predictors.
- Improve patch labeling strategy.
- Test alternative segmentation architectures.
- Expand evaluation across multiple flood seasons.
- Add uncertainty estimation and explainability summaries.

## Citation

If you use this repository in research, please cite the project and any upstream datasets used in the pipeline.

## License

Add your preferred license here.
