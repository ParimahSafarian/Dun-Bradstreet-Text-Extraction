# Dun & Bradstreet Text Extraction

Parimah Safarian **GitHub**: [ParimahSafarian](https://github.com/ParimahSafarian)


## Objectives

The primary goal of our research project is to extract text from a collection of images sourced from the Dun and Bradstreet Reference Book. This endeavor presents two primary challenges:

1. **Complex Page Layouts**: The intricate layout of the pages requires sophisticated handling to ensure accurate text extraction. To address this, we have explored and implemented solutions using Optical Character Recognition (OCR) technologies, specifically focusing on the Layout-Parser and TableParser packages. These tools have enabled us to navigate and interpret the structured layouts effectively, representing a significant step towards our overall objective.

2. **Special Character Recognition** (Future Work): A forthcoming challenge is the accurate recognition of special and non-standard characters within the extracted text. We plan to approach this by deploying machine learning models specifically fine-tuned for this purpose. Anticipated steps include employing preprocessing techniques to create a robust training dataset and applying rigorous post-processing methods to enhance recognition accuracy. This phase of the project is crucial for ensuring the high fidelity of text extraction, particularly given the specialized nature of the content within the Dun and Bradstreet Reference Book.

### Current Status

As of now, our efforts have been concentrated on addressing the layout complexity of the pages. We have achieved promising results in parsing and interpreting page structures, laying a solid foundation for the next stages of the project.

### Future Directions

The recognition of special and non-standard characters remains a significant area for future development. We anticipate that this will involve not only the fine-tuning of machine learning models but also the creation of a comprehensive strategy for data preprocessing and post-processing. This future work is critical for advancing our project's capabilities and achieving our ultimate objective of accurate and comprehensive text extraction.



## Documentation
In addition to this Github reposetory, there is a [Google doc](https://docs.google.com/document/d/1XhEDEBHu_nI9-5uBhKtf-2j4b-IWc5CIxe3zg9z-Mr4/edit?usp=sharing) with weekly progress and more detail. 
Or you can reach me: parimahsafarian@gmail.com 

I would recommend MacOS

## Data Sources

Our project utilizes a pivotal dataset comprising images from the **Dun and Bradstreet Reference Book**. This dataset includes:

- **Before 1863**: Simpler layout i.e.  table-like, without special characters, 
- **1864 to 1879**: 4-column layout, without special characters, includes fractional numbers,
- **1879 to1924 **: 5-column layout, with special characters, includes fractional numbers

**Format**: There exist PDF and jpeg format, you can also download image with text which may not have the desired accuracy.


### Data Annotation, Label Studio
#### Installation
Installation is quite straightforward with MacOS. I installed it [using Homebrew](https://labelstud.io/guide/install#Install-from-source). 
To run lable-studio just simply type label-studio start.
### Annotation
Create a project, upload data (I used jpeg format), as a template I used exactly the one in the [tutorial](https://www.youtube.com/watch?v=puOKTFXRyr4), but there is a suggestion in the Google doc that may be a better option. Annotate data. Export as a COCO file. 
### Preprepration
For our usage the model needs segmentation part to be trained. However, in the exported file in .json file Annotation I had segmentation = []. Because our annotations are rectangular, one can build segmentation based on bbox value. The corresponding code exists in the [jupyter notebook, Customizing Layout Models-Copy for our use](layout-parser/examples/Customizing Layout Models with Label Studio Annotation/Customizing Layout Models-Copy for our use.ipynb) 


### Dependencies and Packages
To be able to run the code create a virtual environment and install the packages with the versions specified in the "packages.txt" file.  

### Train the model
The main file is "Customizing Layout Models-Copy for our use" notebook. Clone the repository, build your virtual environment, make sure to exclude its folder in .gitignore .  Run the notebook and follow the steps written in markdown cells. You will be able to trian the model, but the process was so slow in my experience. Afterwards, you should be able to use the final_model.pth, etc. to digitalize the data. 









