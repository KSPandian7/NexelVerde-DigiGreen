# NexelVerde-DigiGreen

## EcoSat: A GIS-Powered Environmental Monitoring Platform

- EcoSat is a geospatial intelligence platform designed to detect and quantify key environmental changes as,
  
   -  Deforestation
   -  Industrialization
   -  Plastic Waste Accumulation
   -  Water Scarcity
   -  River Encroachment
     
 - For the above issues the data will be fetched by comparing satellite imagery across time.
   
 - Built as part of the DigiGreen Hackathon 2025,<br>
 
    The project executes with,
   -  Deep Learning
   -  Remote Sensing
   -  GIS techniques
 - The above mentioned studies helps to analyze high-resolution satellite data and generate actionable insights to support environmental conservation efforts.

## Problem Statement 

- In the era of rapid industrialization and digital transformation, our environment is facing unprecedented challenges like <strong>plastic pollution, e-waste, deforestation, water scarcity, and climate change.</strong>

- EcoSat addresses this challenge by leveraging <strong>Earth Observation Data and Modern Machine Learning Techniques</strong> to automatically detect and visualize environmental degradation over time.

## Project Objectives

🌳 Detect deforestation and industrialization by <strong>analyzing land cover changes </strong>over time.<br>

🛰️ Identify and quantify <strong>plastic waste accumulation using satellite imagery of water bodies</strong> and urban zones.<br>

🚱 Analyze water scarcity and monitor river area encroachment and <strong>track shifts in natural watercourse boundaries.</strong><br>

💻 Present changes in an interpretable format with spatial overlays, area quantification, and time-based rate analysis.<br>

🔚 Build a user-friendly web-based frontend that allows users to upload satellite image pairs and view analysis results, including segmented change maps, rate of change, and classified areas.<br>


## Project Workflow
<p align="center">
  
<img width="700" height="500" src="https://github.com/KSPandian7/NexelVerde-DigiGreen/blob/main/COLLECT%20REAL-WORLD%20DATA%20(3).png">
</p>
<br>

<strong>1. Collect Real World Data </strong>- Satellite imagery, historical GIS layers, and ground-level photographs are gathered for the targeted regions.<br>

<strong>2. Database</strong> - The collected data is stored using NoSQL databases (e.g., MongoDB) for efficient access and scalability.<br>

<strong>3. Image Preprocessing & Comparison </strong>- Historical and recent images are aligned and preprocessed using geospatial overlays to standardize spatial resolution and format.<br>

<strong>4. Build</strong> - A deep learning model is trained to detect changes in land cover and classify them into categories like deforestation, industrialization, plastic waste, and water scarcity.<br>

<strong>5. Results Generation</strong> - The model generates output masks, metrics, and statistical summaries. Key outputs include heatmaps, impact indicators, and encroachment maps.<br>

<strong>6. Report </strong>- The results are integrated into an interactive frontend interface that enables users to view, and filter reports relevant to specific regions and timeframes.<br>
<br>
<p align="center">
  <strong>Technical aspects of workflow</strong>
</p>
<br>

<p align="center">
 
   <img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/3ec3b222-1707-467c-8dd6-bb8464a1704b" align="center" />
</p>   
<br>

## Temporal Analysis: Image-to-Insight Pipeline

- EcoSat performs environmental change detection by comparing satellite images of the same geographic region captured at different points in time.
  
- The process begins by selecting two temporally separated satellite images of the target area—for instance, images from the Thirumangalam–Sirumangadu region showing changes within a 5.7 km perimeter.
  
- These images undergo preprocessing, including georeferencing, normalization, cloud removal, and vegetation/water index calculations (NDVI, NDWI), followed by cropping to the polygonal region of interest.
  

![WhatsApp Image 2025-07-14 at 00 06 06_abd459ef](https://github.com/user-attachments/assets/db9e42bf-5a69-4ecf-8ba8-62c4abbb98a0)
![WhatsApp Image 2025-07-14 at 00 06 07_946bc6c2](https://github.com/user-attachments/assets/d79fa0ed-6dce-472d-8cf1-c01cc8343229)

- The core analysis is carried out using a Siamese UNet deep learning model, which identifies and segments areas of significant land cover change.
  
- These changes are classified into categories such as deforestation, industrialization, water expansion, or plastic waste accumulation based on spectral and spatial characteristics.
  
- A post-processing classifier interprets these results, distinguishing features like industrial sheds, new water bodies, or pollution zones.
  
-  Once segmented and labeled, the affected areas are quantified in square kilometers or hectares, and rates of change are calculated based on the time difference between the two images. For example, a detected shift of 0.9 km² from undeveloped land to industrial structures over five years indicates a development rate of 0.18 km² per year.
  
-  Finally, all outputs are visualized using overlays, heatmaps, and interactive charts. This end-to-end pipeline transforms raw satellite imagery into actionable spatial intelligence for environmental monitoring and planning.

## Workflow Summary

1.  Acquire temporally separated satellite images for the same location.
2.  Preprocess images: align, crop, normalize, calculate indices (NDVI/NDWI).
3.  Input the pair into a Siamese UNet deep learning model.
4.  Generate a pixel-level change mask and classify changes.
5.  Calculate area and rate of change over time.
6.  Visualize the results and generate exportable reports and maps.

## Model Architecture

We use a Siamese UNet model that takes a pair of satellite images as input and outputs a binary or multi-class change mask. The encoder is based on EfficientNet-B4, pretrained on ImageNet, and the decoder follows a standard UNet architecture with skip connections.A binary classifier for plastic waste presence trained on annotated water body images.NDWI-based water mask analyzer to identify dry zones and water recession.River boundary detector using edge detection + temporal overlay comparisons.

## Tech Stack

### Core Technologies

1. Deep Learning: PyTorch, TensorFlow, Albumentations
2. Satellite Data: Google Earth Engine, SentinelHub, Landsat 8
3. GIS and Raster Processing: Rasterio, GDAL, GeoPandas, OpenCV
4. Database: MongoDB,NoSQL
5. Frontend : Leaflet.js, React.js
6. Cloud: AWS
7. Backend/API: Flask or FastAPI
8. Visualization: Matplotlib, Folium, QGIS

## Future Enhancement

While EcoSat currently offers robust capabilities for detecting deforestation, industrialization, plastic accumulation, and water scarcity using satellite imagery, there are several directions we plan to explore to extend its value. In the near future, we aim to integrate real-time data streaming from platforms like Google Earth Engine to support dynamic updates rather than static comparisons. Additionally, we plan to implement advanced cloud-removal techniques and seasonal normalization to improve model consistency across different climates and times of year. Our team is also exploring support for additional change categories, such as agricultural expansion and wetland loss. On the user interface side, we envision building a fully interactive dashboard that allows users to upload their own image pairs, visualize changes through a time slider, and export detailed PDF reports for local policy use. Long term, EcoSat could evolve into a mobile-friendly tool that provides rapid alerts to environmental authorities when significant land use changes are detected, enabling more timely interventions and conservation decisions.
 
## Conclusion

EcoSat was developed with the goal of transforming raw satellite imagery into actionable environmental insights. By combining the power of deep learning with geospatial data analysis, the platform enables efficient detection of critical land-use changes—such as deforestation, industrialization, plastic accumulation, water scarcity, and river encroachment—across time. This tool is designed to support researchers, environmental agencies, and policymakers in understanding the pace and scale of ecological transformation. As we continue to expand its capabilities and refine its accuracy, EcoSat represents a meaningful step toward scalable, data-driven environmental monitoring for a more sustainable future.
