[Versión en Español](README.md)


# Image Classification for Agriculture 🌱
This project aims to develop a classification model for the semantic segmentation of aerial images within an agricultural context. The main problem it solves is the automatic identification and classification of different types of land cover and use (land classes) 
from images. This is fundamental for crop monitoring, water resource management, land use planning, and precision agriculture. A Logistic Regression classifier is trained to predict the class of each pixel, creating a segmentation mask.

## Technologies Used 🐍
- pandas: For manipulating and structuring tabular data (creating the dataset from image pixels).
- numpy: For efficient numerical operations, especially with image pixel arrays.
- matplotlib: For visualizing images and data plots.
- seaborn: For statistical and class count visualizations.
- scikit-learn (sklearn): For implementing the classification model (LogisticRegression) and its evaluation (ConfusionMatrixDisplay, accuracy_score).
- Pillow (PIL): For opening and manipulating images (Image).
- opencv (cv2): Used for image processing operations.
- colormap: For converting RGB to HEX colors and vice versa, essential for manipulating segmentation masks.
- os y glob: For navigating and listing files in the directory system.
- json: For reading class configuration files.
- skillsnetwork: A specific library for downloading data from IBM Cloud.


## Installation Considerations ⚙️
To set up and run the project, you need several Python libraries that are important to install in your chosen environment; in this case, conda is used.

conda install -y matplotlib scikit-learn seaborn pandas numpy pillow

conda install -c conda-forge -y opencv colormap
conda install -c intel -y scikit-learn

pip install skillsnetwork

The code uses an await skillsnetwork.prepare(...) command which downloads and unzips the image dataset. This command must be executed in an environment that supports await (such as a Jupyter Notebook or IPython).

## Usage Example 📎
This code performs a series of steps to classify agricultural image pixels, following this execution flow:
 1. Image Data Download and Loading: It starts by downloading a dataset (using IBM Cloud for this case), where the get_data function processes classes.json files and loads the images.
 2. Dataset Creation: The create_DataSet function transforms the images and their masks into a pandas DataFrame, where each row represents a pixel with its respective properties.
 3. Class Distribution Visualization: Bar charts are used to visualize the distribution of classes (represented by HEX color values) in the training and test datasets.
 4. Classifier Training and Evaluation: A Logistic Regression model is trained using the RGB values of the original image as features to predict the HEX class.
 5. Test Image Segmentation and Visualization: Finally, the trained model is used to predict the class of pixels in a new test image.

## NOTE ⚠️
This project has two compilation methods, depending on where and how you want to evaluate it. This primarily affects how the database is obtained: one method considers access via Jupyter Notebook (or similar environments), 
and the other uses traditional queries for script-based usage.
Both files are attached for testing; version 2 is the code with the manual method for querying the databases.

## Contributions 🖨️
If you're interested in contributing to this project or using it independently, consider:
- Forking the repository.
- Creating a new branch (git checkout -b feature/your-feature).
- Making your changes and committing them (git commit -am 'Add new feature').
- Pushing your changes to the branch (git push origin feature/your-feature).
- Opening a 'Pull Request'.


## License 📜
This project is under the MIT License. Refer to the LICENSE file (if applicable) for more details.
