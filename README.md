# <i> Aariz: </i> A Benchmark Dataset for Automatic Cephalometric Landmark Detection and CVM Stage Classification
<p align="justify">
The accurate identification and precise localization of cephalometric landmarks enable the classification and quantification of anatomical abnormalities. The traditional manual way of marking cephalometric landmarks on lateral cephalograms is monotonous and time-consuming job. Endeavours to develop automated landmark detection systems have persistently been made, however, they are inadequate for orthodontic applications due to unavailability of a reliable dataset. We proposed a new state-of-the-art dataset to facilitate the development of robust AI solutions for quantitative morphometric analysis. The dataset includes 1000 lateral cephalometric radiographs (LCRs) obtained from 7 different radiographic imaging devices with varying resolutions, making it the most diverse and comprehensive cephalometric dataset to date. The clinical experts of our team meticulously annotated each radiograph with 29 cephalometric landmarks, including the most significant soft tissue landmarks ever marked in any publicly available dataset. Additionally, our experts also labelled the cervical vertebral maturation (CVM) stage of the patient in a radiograph, making this dataset the first standard resource for CVM classification. The radiographs from each imaging device are uniformly distributed into train, validation and test sets. We believe that this dataset will be instrumental in the development of reliable automated landmark detection frameworks for use in orthodontics and beyond.

## Updates
- **31/07/2025**: Aariz has officially made its debut in [Nature Scientific Data](https://doi.org/10.1038/s41597-025-05542-3).
- **21/05/2025**: The [dataset](https://doi.org/10.6084/m9.figshare.27986417.v1) is now **publicly available**, offering the research community access to 1000 annotated cephalometric X-rays with 29 anatomical landmarks & CVM stages.
- **19/12/2022**: Aariz joins [CEPHA29 Challenge](https://biomedicalimaging.org/2023/challenges/) on Automatic Cephalometric Landmark Detection, held under **IEEE International Symposium on Biomedical Imaging (ISBI)**.

<div align="center">
  <img src="docs/dataset-example-images.svg">
</div>
<div align="center"> A diverse collection of sample images from various imaging devices along with their cephalometric landmarks and CVM stage </div>

# Usage Guide
To create an object of the dataset class and use it to read images and their corresponding annotations, you can first import the <code>AarizDataset</code> and then instantiate the class with the appropriate parameters, such as the <code>dataset_folder_path</code> containing the images and annotations, the <code>mode</code> for which to read the files i.e <code>TRAIN</code>, <code>VALID</code> and <code>TEST</code>.
```
from dataset import AarizDataset
dataset = AarizDataset(dataset_folder_path="folder/to/dataset", mode="TRAIN")
images, landmarks, cvm_stages = dataset[0]
```

# CEPHA29 Challenge 2023
To facilitate the development of robust AI solutions for morphometric analysis, we also organised the <a href="http://vision.seecs.edu.pk/CEPHA29/">CEPHA29 Automatic Cephalometric Landmark Detection Challenge</a> in conjunction with <a href="https://2023.biomedicalimaging.org/en/CHALLENGES.html">IEEE International Symposium on Biomedical Imaging</a> (ISBI 2023). This is a great opportunity for researchers and practitioners in the field to test their algorithms on a standardized platform. We believe that by hosting our dataset as a challenge, we can promote the development of new and innovative solutions to problems in the field.

# Acknowledgements
We would like to express our heartfelt gratitude to all of the clinicians at <a href="https://www.riphah.edu.pk/dental-sciences/">Islamic International Dental College</a> for their tireless efforts and contributions to the annotation process of this dataset. This research would not have been possible without the support of <a href="https://www.riphah.edu.pk">Riphah International University</a>, Islamabad, Pakistan. We also extend our sincere thanks to the patients who provided consent for the use of their cephalometric images. Finally, we would like to acknowledge the valuable feedback and suggestions provided by the anonymous reviewers, which helped us improve the quality of this dataset.

# Citation
If you use our dataset in your research or projects, please consider citing our papers:
```BibTeX
@article{khalid2025benchmark,
  title={A Benchmark Dataset for Automatic Cephalometric Landmark Detection and CVM Stage Classification},
  author={Khalid, Muhammad Anwaar and Zulfiqar, Kanwal and Bashir, Ulfat and Shaheen, Areeba and Iqbal, Rida and Rizwan, Zarnab and Rizwan, Ghina and Fraz, Muhammad Moazam},
  journal={Scientific Data},
  volume={12},
  number={1},
  pages={1336},
  year={2025},
  publisher={Nature Publishing Group UK London}
}
```
