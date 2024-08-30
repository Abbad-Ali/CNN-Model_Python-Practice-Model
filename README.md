
# CNN Project

This project categorizes a large pool of unlabelled images into three categories: shoes, boots, and sandals. It uses a convolutional neural network (CNN) for feature extraction and a clustering algorithm to sort the images into categories.

## Overview

The Jupyter notebook in this project performs the following tasks:
1. **Preprocesses Images**: Resizes and normalizes images for feature extraction.
2. **Extracts Features**: Uses the ResNet50 model to extract features from images.
3. **Clusters Images**: Applies K-Means clustering to categorize images into three groups.
4. **Organizes Images**: Moves images to folders based on their cluster assignments.

## Dataset

The dataset used in this project consists of unlabelled images of shoes, boots, and sandals. You can use your own dataset or the one described below:

- **Dataset Name**: Shoe, Boot, and Sandal Images
- **Source**: (https://www.kaggle.com/datasets/hasibalmuzdadid/shoe-vs-sandal-vs-boot-dataset-15k-images?resource=download&select=Shoe+vs+Sandal+vs+Boot+Dataset)
- **Description**: The dataset includes various images of shoes, boots, and sandals. It is used to train the model and perform clustering.

### How to Download the Dataset

If you have access to a specific dataset link, you can download it from there. Ensure the dataset is in a format compatible with the script (e.g., JPEG or PNG images).

1. **Download the Dataset**:
   - Use the dataset link to download the images.
   - Extract the images to a folder on your local machine.

2. **Set Up Your Dataset**:
   - Place your unlabelled images in a folder named `shoe_boot_sandal`. The folder structure should look like:
     ```
     /path/to/your/dataset/
     └── shoe_boot_sandal/
         ├── image1.jpg
         ├── image2.jpg
         └── ...
     ```

## Usage

1. **Prepare Your Environment**:
   - Ensure you have Python 3.x installed.
   - Install the required packages using the commands below:

   ```bash
   pip install opencv-python-headless numpy tensorflow scikit-learn
   ```

2. **Configure Paths**:
   - Modify the `data_folder` variable in the notebook to point to the location of your images:
     ```python
     data_folder = '/path/to/your/dataset/shoe_boot_sandal'
     ```
   - Set the `output_folder` variable to the desired location for the categorized images:
     ```python
     output_folder = '/path/to/your/output/folder'
     ```

3. **Run the Notebook**:
   - Execute the Jupyter notebook. It will preprocess images, extract features, perform clustering, and organize images into folders based on their categories.

4. **Check Results**:
   - Navigate to the `output_folder` to view the categorized images. They will be organized into subfolders named `cluster_0`, `cluster_1`, and `cluster_2`.

## Code Explanation

### Feature Extraction

The `extract_features` function uses the ResNet50 model (pretrained on ImageNet) to extract features from the images. The features are flattened and prepared for clustering.

### Clustering

The `KMeans` algorithm is used to cluster the images into three categories. The number of clusters (`n_clusters`) is set to 3, corresponding to shoes, boots, and sandals.

### Organizing Images

The `move_images_to_folders` function organizes images into folders based on their cluster assignments. Each cluster will have its own folder.
