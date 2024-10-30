# Optimizing Rural Waste Management: Leveraging High-Resolution Remote Sensing and GIS for Efficient Collection and Routing —— Huangtu Datasets specification

## 1. Introduction to Huangtu Dataset

- **Study area**
The study area is Huangtu Town (31°31ʹ–31°40ʹN, 104°26ʹ–104°33ʹE) in Sichuan Province, Southwest China, which covers an area of 84.54$`km^2`$ and has a population of approximately 37017 residents (Department of Rural Surveys, National Bureau of Statistics of the People’s Republic of China, 2020). Huangtu's geography is separated by hills and dam regions, and its boundary covers two watersheds of the Anchang and Caoxi Rivers, with a subtropical humid monsoon climate.
- **Study the basis of regional selection**
    - Huangtu is representative of many other towns in China with diverse geographical environments and low population density. From 2011 to 2019, the population density of the town remained at about 500 people/$`km^2`$ . This typical and complex feature provides a valuable opportunity to evaluate our decentralized waste collection and routing models and strategies.
    - Our previous research on Huangtuzhen provided useful information for the optimization of this study, which can be used to add environmental constraints to the model framework.
- **Thesis and author unit**
    - The dataset has been thoroughly introduced and published in the article "Optimizing Rural Waste Management: Leveraging High-Resolution Remote Sensing and GIS for Efficient Collection and Routing"

## 2. Dataset Overview

  The core content of this dataset is very high-resolution (VHR) remote sensing imagery, sourced from Google Earth Engine (GEE) in 2020. These VHR images include three optical bands: red, green, and blue, with an 18-level zoom. To ensure image quality, this dataset underwent a series of rigorous preprocessing operations, including image stitching, cropping, and bit-depth adjustment. Additionally, the images were reprojected to the Universal Transverse Mercator (UTM) projection and resampled to a 1-meter spatial resolution to enhance visual clarity and geospatial accuracy.

  In addition, the dataset includes grayscale label images that were first manually annotated, with the results of a deep learning semantic segmentation model integrated in certain details. After the integration, the labels were manually checked and optimized again to ensure their accuracy and completeness. Different grayscale values in the label images represent the corresponding land cover types, facilitating model training and usage.

## 3. Dataset Composition

  This dataset includes **VHR sample block images** and **PNG format grayscale label images**. These grayscale images correspond to the 30 VHR image sample blocks, which cover the area of Huangtu Town with ultra-high resolution. Each sample block is sized at 1000 × 1000 pixels. The sample blocks are used to train image segmentation models and comprehensively reflect the rural landscape of Huangtu County, covering five typical environmental features: buildings, roads, water bodies, farmland, and forests.

  The PNG format grayscale label images contain polygonal coverage features representing six characteristics: background, buildings, roads, farmland, green spaces, and water bodies. In addition, the dataset separately includes grayscale label images consisting of linear features representing farmland boundaries. These linear features are used to accurately delineate the geographic boundaries of farmland. Thus, farmland areas are displayed not only as regions composed of polygonal coverage but also further clarified by boundary lines to specify their geographic limits.

## 4. Land Cover Labels

  The land cover labels are represented as PNG format grayscale images, used to annotate land cover types within the VHR sample block images. The grayscale images consist of two files: one named "Complete Land Cover Labels", which contains polygonal coverage features for six characteristics—background, buildings, roads, farmland, green spaces, and water bodies; and another named "Farmland Boundary Labels", which contains only the background and farmland boundary linear features, used to accurately delineate the geographic boundaries of farmland.

  The labels were first manually annotated, then integrated with the results of a deep learning segmentation model in certain details, and finally manually checked and optimized again to ensure the accuracy and completeness of the label boundaries.

————————————————————————————————————————————

├──Complete Land Cover Labels gray-scale value───│

├──0 │\------------ │────── Background───────│

├──1 │\------------ │───────Buildings────────│

├──2 │\------------ │────────Roads─────────│

├──3 │\------------ │────────Forests ────────│

├──4 │\------------ │─────── Farmland ─────── │

├──5 │\------------ │────── Water bodies────── │

————————————————————————————————————————————

├── Farmland Boundary Labels gray-scale value───│

├──0 │\------------ │──────Background──────│

├──1 │\------------ │────── Farmland ───────│

————————————————————————————————————————————

## 5. Land Cover Annotation Principles

To ensure accuracy and consistency in data labeling, this dataset follows a set of precise annotation principles tailored to each land cover type:

1. **Farmland**: Annotation includes all boundaries intersecting with farmland areas, outlining contours as closely as possible to visible edges; for connected farmland areas, only the outermost boundary is marked.
2. **Forest**: Forest primarily include forests as the annotated areas, outlining forest boundaries to match visible contours; for contiguous forested areas, only the outer boundary is marked.
3. **Buildings**: Building annotations are based on the rooftop outline, following the external contours without considering sidewalls or shadows; for connected buildings, each visually distinct structure is annotated separately.
4. **Roads**: Roads are annotated along the actual road edges, ignoring trees or shadow obstructions; if a segment is obscured for more than 20 pixels, it is divided and annotated as two separate segments.
5. **Water Bodies**: Water bodies are annotated based on clear water edges, ensuring accurate representation. Distinct water areas separated by barriers such as sandbars or vegetation are annotated as independent water bodies.

## 6. **Article citation format**

## 7. **Dataset Access and Usage**

- **The dataset is shared via Baidu Netdisk:**

       Link：https://pan.baidu.com/s/1rRB9EmtZdCBsSTrsfWh6yA?pwd=cdut 
       Access code:cdut

- **The dataset is shared via Google Drive:**

       Link:https://drive.google.com/drive/folders/18wN2XmZPFAia8orKet3-bi0yoP6rO7hp?usp=sharing

  The dataset folder contains three subfolders: **"Complete Land Cover Labels"**, **"Farmland Boundary Labels"**, and **"VHR Images"**. Each of these subfolders includes thirty images, with corresponding filenames across all three folders. The images are named following the format"**htz_clip[*]**", where the placeholder " **[*]**" represents the specific index of each image. This consistent naming structure ensures that the images in each folder directly correspond to one another, facilitating easy comparison and usage for research purposes.

## 8. **Acknowledgements**

  We would like to express our sincere gratitude to Graduate Quality Engineering Construction Funding Program of Chengdu University of Technology (2024YAL016) for the support of this project.

  We also acknowledge the efforts of all contributors, whose input and collaboration greatly contributed to the success of this research.

**Chengdu University of Technology:**

Xi Cheng, Zhiyong Han, Miaomiao Liu, Jieyu Yang, Zhuojun Zeng, Deng Pan

**Aerospace Information Research Institute (Chinese Academy of Science) :**
Zhanfeng Shen, Haoyu Wang

**Key Laboratory of Development and Application of Rural Renewable Energ (Ministry of Agriculture, China)：**

Guozhong Shi
