# Water Hyacinth Detection Project Test Cases
This document outlines the test cases for data processing in the Water Hyacinth Detection Project.
The data processing is applied to Landsat 8 satellite images to detect and monitor water hyacinth growth. 
Each test case covers different steps in the workflow, including image segmentation, cloud masking, indices extraction, binary labeling, and weather data correlation.
![image](https://github.com/user-attachments/assets/b1c74050-d8bc-46be-929a-71cd2e3f1136)
### Required: A notebook for each test case.
### 6.2. Data Processing
- Satellite: Landsat 8 (Atmospheric correction not required)
#### 6.2.1. Test Case 1.1: Image Segmentation
Input: Satellite images with identified boundary.
Expected Output: Binary mask where ROI (dam) is retained, surrounding areas blanked out.
Method: Print 3 randomly selected images before and after binary masking.
Validation: Visually check if the surrounding area is masked.

#### 6.2.2. Test Case 3.1: Cloud Masking
Input: Satellite images with clouds and shadows.
Expected Output: Cloud and shadow-free images.
Method: Apply Fmask algorithm to remove clouds and shadows.
Validation: Visualize top 3 images before and after applying Fmask.

#### 6.2.3. Indices Extractions
##### 6.2.3.1. Test Case 4.1: NIR, Blue, and Red Band Extraction
- Input: Raw satellite images.
- Expected Output: Correctly extracted pixel indices for each band.
- Method: Extract relevant pixel values from the dataset.
- Validation: Verify ranges with standard values.
##### 6.2.3.2. Test Case 4.2: NDVI and EVI Calculations
- Input: Extracted pixel indices.
- Expected Output: Accurate NDVI and EVI calculations.
- Method: Use Python libraries to calculate NDVI and EVI.
- Validation: Cross-check calculated values with library output.
##### 6.2.3.3. Test Case 4.3: Seasonal Feature Creation
- Input: NDVI and EVI values.
- Expected Output: Correct seasonal averages.
- Method: Group indices by season and calculate averages.
- Validation: Compare averages with known standard values.
##### 6.2.4. Test Case 5.1: Binary Labelling Assignment
- Input: NDVI, EVI, and threshold values.
- Expected Output: Binary-labelled pixel values.
- Method: Assign binary values based on threshold.
- Validation: Visualize images before and after binary labeling, emphasizing missed vegetation.
### Weather Data Processing
#### Test Case 6.1: Weather Data Correlation
- Input: Weather data and corresponding satellite image data.
- Expected Output: Matched weather data for each image.
- Method: Join data on date column and standardize date format.
- Validation: Check date accuracy and print quartile data.
#### Test Case 6.2: Handling Missing Values
- Input: Full dataset (weather and images).
- Expected Output: No missing values after imputation.
- Method: Calculate and impute missing values.
- Validation: Ensure no missing values remain after imputation.
#### Test Case 6.3: Encoding Categorical Data
- Input: Categorical data columns.
- Expected Output: Binary and one-hot encoded columns.
- Method: Use Sk-learn to encode data.
- Validation: Verify binary nature of the values.
