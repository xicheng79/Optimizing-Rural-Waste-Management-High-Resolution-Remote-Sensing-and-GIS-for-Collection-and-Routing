## **Optimizing Rural Waste Management: Leveraging High-Resolution Remote Sensing and GIS for Efficient Collection and Routing ── ── ── Datasets specification**

### 1. Dataset Overview
The core content of this dataset is very high-resolution (VHR) remote sensing imagery, sourced from Google Earth Engine (GEE) in 2020. These VHR images include three optical bands: red, green, and blue, with an 18-level zoom. To ensure image quality, this dataset underwent a series of rigorous preprocessing operations, including image stitching, cropping, and bit-depth adjustment. Additionally, the images were reprojected to the Universal Transverse Mercator (UTM) projection and resampled to a 1-meter spatial resolution to enhance visual clarity and geospatial accuracy.

In addition, this dataset includes grayscale label images that were generated by processing the VHR images with a deep learning semantic segmentation model, automatically extracting pixel regions corresponding to specific target features. Based on the initial segmentation results, further manual editing and optimization were performed to ensure label accuracy and completeness. Different grayscale values in the label images represent corresponding land cover types, facilitating model training and usage.


### 2. Dataset Composition

This dataset includes **VHR sample block images** and **PNG format grayscale label images**. These grayscale images correspond to the 30 VHR image sample blocks, which cover the area of Huangtu Town with ultra-high resolution. Each sample block is sized at 1000 × 1000 pixels. The sample blocks are used to train image segmentation models and comprehensively reflect the rural landscape of Huangtu County, covering five typical environmental features: buildings, roads, water bodies, farmland, and forests.

The PNG format grayscale label images contain polygonal coverage features representing six characteristics: background, buildings, roads, farmland, green spaces, and water bodies. In addition, the dataset separately includes grayscale label images consisting of linear features representing farmland boundaries. These linear features are used to accurately delineate the geographic boundaries of farmland. Thus, farmland areas are displayed not only as regions composed of polygonal coverage but also further clarified by boundary lines to specify their geographic limits.


### 3. Land Cover Labels

The land cover labels are represented as PNG format grayscale images, used to annotate land cover types within the VHR sample block images. The grayscale images consist of two files: one named "Complete Land Cover Labels", which contains polygonal coverage features for six characteristics—background, buildings, roads, farmland, green spaces, and water bodies; and another named "Farmland Boundary Labels", which contains only the background and farmland boundary linear features, used to accurately delineate the geographic boundaries of farmland.

The initial labels were automatically generated by a deep learning semantic segmentation model, identifying and extracting pixel regions corresponding to these environmental features. Based on the initial segmentation results, manual editing and optimization were performed to ensure the accuracy and completeness of label boundaries.
————————————————————————————————————————————————————

├──Complete Land Cover Labels gray-scale value│        
                                                  
├──0 │\------------ │ Background                 
                                                 
├──1 │\------------ │ Building                    
                                                   
├──2 │\------------ │ Road                         
                                                   
├──3 │\------------ │ Green space                  
                                                   
├──4 │\------------ │ Farmland                     
                                                   
├──5 │\------------ │ Water body                  

————————————————————————————————————————————————————

├──Farmland Boundary Labels gray-scale value│

├──0 │\------------ │ Background

├──1 │\------------ │ Farmland

————————————————————————————————————————————————————



### 4. Data Processing Workflow

The processing of this dataset involves multiple steps to ensure data quality and accuracy. The specific workflow is as follows:
1. **Image Stitching**: To achieve complete VHR image coverage, multiple small-range remote sensing images were stitched together to generate extensive image data. This step ensures continuity across sample areas, aiding in accurate land feature extraction.
2. **Image Cropping**: The stitched images were cropped into multiple sample blocks (patches) of 1000 × 1000 pixels, with each block covering the land features of a specific area.
3. **Bit-depth Adjustment**: The bit depth of the images was standardized to ensure data consistency. This step harmonizes bit depth differences from various image sources.
4. **Projection Transformation**: To ensure geographical coordinate accuracy, the images were projected into the Universal Transverse Mercator (UTM) coordinate system. This transformation guarantees consistency in coordinates across different geographic regions, providing reliable support for geospatial analysis.
5. **Resampling**: Spatial resampling was applied to adjust the images to a 1-meter resolution. This process enhances the spatial resolution, making land features more distinct and improving the model's ability to recognize small-scale features in segmentation tasks.

### 5. Dataset Applications

This dataset holds significant potential in various remote sensing applications, suitable for the following scenarios:

1. **Remote Sensing Analysis and Land Feature Recognition**
   The high-resolution images and detailed land cover labels in this dataset provide reliable data support for the identification and classification of multiple land features, such as buildings, roads, water bodies, farmland, and green spaces. Researchers can use this dataset to train and evaluate deep learning models for automatic feature recognition and extraction, supporting various remote sensing analysis tasks.

2. **Resource Management in Rural Areas**
   The dataset can be used to analyze building distribution, road layout, and environmental features in rural areas, helping to assess waste generation patterns and providing a basis for setting up waste collection points and planning collection routes. Such analyses offer practical applications in optimizing resource management, improving processing efficiency, and reducing environmental impact.

3. **Path Planning and Transportation Optimization**
   This dataset supports path planning and transportation optimization studies in rural settings. Based on the geospatial information in this dataset, researchers can apply path optimization algorithms to generate optimal routes for resource collection and transportation, reducing travel distance, lowering energy consumption, and enhancing overall transport efficiency.

4. **Environmental Protection and Ecological Analysis**
   The detailed land classification information in this dataset aids in environmental analysis and ecological protection efforts in rural areas. Researchers can analyze ecological features, such as water bodies and green spaces, and their spatial distribution to evaluate the impact of human activities on the natural environment, providing support for ecological protection and environmental management.

### 6. Dataset Access and Usage

Dataset access URL:<a href="黄土镇VHR影像及标签灰度图" title="黄土镇VHR影像及标签灰度图">Optimizing Rural Waste Management: Leveraging High-Resolution Remote Sensing and GIS for Efficient Collection and Routing ──  Datasets </a>
