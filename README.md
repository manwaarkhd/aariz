<h2 align="center"><i> Aariz: </i> A Benchmark Dataset for Automatic Cephalometric Landmark Detection and CVM Stage Classification</h2>
<p align="center">
  <a href="https://arxiv.org/abs/2212.04808"><strong> Preprint (arXiv) </strong></a>
  ·
  <a href="https://doi.org/10.1038/s41597-025-05542-3"><strong> Journal Article </strong></a>
  ·
  <a href="https://doi.org/10.6084/m9.figshare.27986417.v1"><strong> Dataset (Figshare) </strong></a>
</p>
<p align="justify">
<i>Aariz</i> is a benchmark dataset comprising <b>1000 lateral cephalometric radiographs (LCRs)</b>, acquired from 7 different radiographic imaging devices with varying resolutions, making it one of the most diverse and comprehensive cephalometric datasets available to date. Each radiograph has been meticulously annotated by clinical experts with <b>29 cephalometric landmarks</b>, featuring a rich set of dental and soft-tissue points. In addition to landmark annotation, <b>Cervical Vertebral Maturation (CVM) stages</b> are labelled for each patient, positioning Aariz as the first standard resource for CVM classification. To ensure fair evaluation and reproducibility, the dataset is uniformly partitioned into train, validation, and test sets, stratified across all imaging devices. 
</p>

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

# Results

This section presents the average performance on both the validation and test sets of the Aariz dataset, comparing several published methods with our proposed baseline model. The evaluation metrics include **Mean Radial Error (MRE)** with its **Standard Deviation (SD)**, and **Success Detection Rate (SDR)** at multiple clinically relevant thresholds (2.0 mm, 2.5 mm, 3.0 mm, and 4.0 mm). The best results for each metric are highlighted in bold. 

| Paper        | MRE ± SD (mm)    | SDR 2.0mm (%) | SDR 2.5mm (%) | SDR 3.0mm (%) | SDR 4.0mm (%) |
|--------------|--------------:|----------:|----------:|----------:|----------:|
| [Khan et al.](https://doi.org/10.1007/978-3-031-66958-3_1) (2024) | 1.92 ± 7.85 | 78.54 | 85.72 | 89.64 | 94.49 |
| [Khalid et al.](https://doi.org/10.1016/j.eswa.2024.124840) (2024)| 1.87 ± 4.01 | 75.17 | 82.43 | 88.78 | 93.01 |
| [Khan et al.]()                                            (2025)*| **1.69 ± 3.36** | **81.18** | **87.28** | **90.82** | **94.82** |

\* *Baseline model, currently under-review*

## Category-wise Performance:
- **Soft tissue landmarks**: Achieved excellent performance, with all six registering MRE < 2.0 mm.
- **Dental landmarks**: Performed consistently well, with only minor deviations exceeding the 2.0 mm threshold.
- **Skeletal landmarks**: Were generally more difficult, with most of the MREs > 2.0 mm falling in this category.

## Landmark Level Performance:
- **Top-Performing Landmarks**: Landmarks with MRE < 1.0 mm in either validation or test sets include Me, Pog, S, Gn, UIT, Li, Ls, Sn, Pn. Notably, four landmarks reached 100% SDR in both sets.
- **Challenging Landmarks**: Landmarks with MRE > 2.0 mm in either set include N, Or, R, Ar, Co, Go, LPM, LMT, UPM, UMT. Despite higher MREs, these still achieved moderate SDRs between 49.00% and 87.34% within the 2.0 mm range.

### Baseline -  Validation Set Results

| Landmark | MRE ± SD (mm)     | SDR 2.0mm (%) | SDR 2.5mm (%) | SDR 3.0mm (%) | SDR 4.0mm (%) |
|----------|---------------:|--------------:|--------------:|--------------:|--------------:|
| A        | 1.10 ± 0.81   | 86.67 | 93.33 | 94.67 | 99.33 |
| ANS      | 1.37 ± 1.03   | 79.33 | 88.67 | 91.33 | 96.67 |
| B        | 1.04 ± 0.97   | 90.00 | 94.67 | 95.33 | 98.00 |
| Me       | 0.63 ± 0.52   | 97.33 | 99.33 | 99.33 | 100.00 |
| N        | 2.24 ± 14.89  | 88.67 | 92.67 | 96.00 | 98.00 |
| Or       | 1.43 ± 1.39   | 80.00 | 87.33 | 91.33 | 95.33 |
| Pog      | 0.81 ± 0.66   | 94.00 | 97.33 | 98.00 | 100.00 |
| PNS      | 1.63 ± 1.39   | 75.33 | 80.00 | 87.33 | 95.33 |
| Pn       | 0.89 ± 0.63   | 92.67 | 98.00 | 99.33 | 100.00 |
| R        | 2.73 ± 2.42   | 52.00 | 60.67 | 70.00 | 80.00 |
| S        | 1.12 ± 3.99   | 97.33 | 98.00 | 98.67 | 99.33 |
| Ar       | 5.54 ± 23.03  | 80.67 | 84.00 | 87.33 | 91.33 |
| Co       | 4.82 ± 14.98  | 60.00 | 72.00 | 76.67 | 88.00 |
| Gn       | 0.63 ± 0.52   | 97.33 | 98.67 | 99.33 | 100.00 |
| Go       | 2.97 ± 8.79   | 62.67 | 72.00 | 81.33 | 90.00 |
| Po       | 1.95 ± 2.12   | 69.33 | 78.00 | 84.00 | 92.00 |
| LPM      | 2.09 ± 2.52   | 73.33 | 78.67 | 82.00 | 88.00 |
| LIT      | 1.28 ± 2.62   | 91.33 | 94.00 | 94.00 | 97.33 |
| LMT      | 1.73 ± 2.05   | 76.67 | 83.33 | 87.33 | 89.33 |
| UPM      | 2.06 ± 2.44   | 64.67 | 75.33 | 80.67 | 90.00 |
| UIA      | 1.41 ± 0.96   | 75.33 | 84.67 | 94.00 | 98.67 |
| UIT      | 0.80 ± 0.74   | 95.33 | 98.67 | 98.67 | 98.67 |
| UMT      | 1.89 ± 1.99   | 70.67 | 78.67 | 83.33 | 89.33 |
| LIA      | 1.49 ± 1.21   | 76.00 | 84.67 | 90.67 | 94.67 |
| Li       | 0.98 ± 0.73   | 91.33 | 94.67 | 96.67 | 100.00 |
| Ls       | 1.33 ± 6.34   | 94.00 | 96.67 | 98.67 | 99.33 |
| N’       | 1.10 ± 0.86   | 87.33 | 92.67 | 94.67 | 99.33 |
| Pog’     | 1.09 ± 0.90   | 86.00 | 91.33 | 95.33 | 98.67 |
| Sn       | 0.80 ± 0.61   | 96.00 | 98.00 | 98.67 | 100.00 |
| Average  | 1.68 ± 3.52   | 82.11 | 87.79 | 91.20 | 95.40 |


### Baseline - Test Set Results

| Landmark | MRE ± SD (mm)     | SDR 2.0mm (%) | SDR 2.5mm (%) | SDR 3.0mm (%) | SDR 4.0mm (%) |
| -------- | -------------: | ------------: | ------------: | ------------: | ------------: |
| A        | 1.00 ± 0.71   | 90.67 | 95.33 | 98.00 | 99.33 |
| ANS      | 1.42 ± 1.36   | 77.33 | 85.33 | 90.67 | 96.67 |
| B        | 1.03 ± 0.80   | 88.00 | 96.00 | 96.00 | 99.33 |
| Me       | 0.66 ± 0.48   | 99.33 | 99.33 | 99.33 | 100.00 |
| N        | 1.17 ± 0.98   | 86.00 | 92.67 | 95.33 | 96.67 |
| Or       | 2.05 ± 8.56   | 76.00 | 87.33 | 94.67 | 98.00 |
| Pog      | 0.71 ± 0.53   | 96.00 | 98.67 | 98.67 | 100.00 |
| PNS      | 1.65 ± 1.72   | 75.33 | 82.00 | 88.67 | 94.67 |
| Pn       | 0.87 ± 0.61   | 92.00 | 98.67 | 99.33 | 100.00 |
| R        | 2.74 ± 2.43   | 46.00 | 59.33 | 67.33 | 79.33 |
| S        | 0.98 ± 2.77   | 97.33 | 99.33 | 99.33 | 99.33 |
| Ar       | 5.62 ± 22.13  | 70.67 | 76.00 | 80.00 | 86.00 |
| Co       | 5.23 ± 16.80  | 54.67 | 66.00 | 73.33 | 86.67 |
| Gn       | 0.57 ± 0.37   | 99.33 | 100.00 | 100.00 | 100.00 |
| Go       | 2.05 ± 2.40   | 64.67 | 75.33 | 81.33 | 88.00 |
| Po       | 1.99 ± 2.14   | 68.67 | 78.67 | 84.67 | 89.33 |
| LPM      | 2.47 ± 3.75   | 68.00 | 76.67 | 82.00 | 86.00 |
| LIT      | 1.25 ± 2.07   | 88.67 | 92.67 | 96.00 | 97.33 |
| LMT      | 2.01 ± 2.64   | 74.67 | 80.67 | 85.33 | 89.33 |
| UPM      | 2.71 ± 3.57   | 60.67 | 68.67 | 74.67 | 78.67 |
| UIA      | 1.48 ± 1.12   | 75.33 | 87.33 | 92.00 | 98.67 |
| UIT      | 0.85 ± 0.86   | 93.33 | 96.67 | 98.00 | 98.00 |
| UMT      | 2.07 ± 2.45   | 69.33 | 77.33 | 80.00 | 86.00 |
| LIA      | 1.50 ± 1.05   | 72.67 | 85.33 | 91.33 | 97.33 |
| Li       | 1.48 ± 0.45   | 81.33 | 87.33 | 95.33 | 97.33 |
| Ls       | 0.84 ± 1.45   | 93.33 | 96.00 | 98.00 | 99.33 |
| N’       | 1.23 ± 1.20   | 85.33 | 88.67 | 93.33 | 96.00 |
| Pog’     | 1.24 ± 1.36   | 85.33 | 90.00 | 91.33 | 96.00 |
| Sn       | 0.99 ± 3.30   | 97.33 | 98.67 | 98.67 | 99.33 |
| Average  | 1.71 ± 3.20   | 80.25 | 86.76 | 90.44 | 94.23 |


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

@article{khalid2022cepha29,
  title={Cepha29: Automatic cephalometric landmark detection challenge 2023},
  author={Khalid, Muhammad Anwaar and Zulfiqar, Kanwal and Bashir, Ulfat and Shaheen, Areeba and Iqbal, Rida and Rizwan, Zarnab and Rizwan, Ghina and Fraz, Muhammad Moazam},
  journal={arXiv preprint arXiv:2212.04808},
  year={2022}
}
```
