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

# Results
This section presents the average performance on both the validation and test sets of the Aariz dataset, comparing several published methods with our proposed baseline model. The evaluation metrics include **Mean Radial Error (MRE)** with its **Standard Deviation (SD)**, and **Success Detection Rate (SDR)** at multiple clinically relevant thresholds (2.0 mm, 2.5 mm, 3.0 mm, and 4.0 mm). The best results for each metric are highlighted in bold. 

<table>
  <thead>
    <tr>
      <th rowspan="2" style="text-align:left;">Method</th>
      <th rowspan="2" style="text-align:center;">MRE ± SD <br> (mm)</th>
      <th colspan="4" style="text-align:center;">SDR (%)</th>
    </tr>
    <tr>
      <th style="text-align:center;">2.0 mm</th>
      <th style="text-align:center;">2.5 mm</th>
      <th style="text-align:center;">3.0 mm</th>
      <th style="text-align:center;">4.0 mm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left;">
        <a href="https://doi.org/10.1007/978-3-031-66958-3_1">Khan et al.</a> (2024)
      </td>
      <td style="text-align:center;">1.92 ± 7.85</td>
      <td style="text-align:center;">78.54</td>
      <td style="text-align:center;">85.72</td>
      <td style="text-align:center;">89.64</td>
      <td style="text-align:center;">94.49</td>
    </tr>
    <tr>
      <td style="text-align:left;">
        <a href="https://doi.org/10.1016/j.eswa.2024.124840">Khalid et al.</a> (2024)
      </td>
      <td style="text-align:center;">1.87 ± 4.01</td>
      <td style="text-align:center;">75.17</td>
      <td style="text-align:center;">82.43</td>
      <td style="text-align:center;">88.78</td>
      <td style="text-align:center;">93.01</td>
    </tr>
    <tr>
      <td style="text-align:left;">
        <a href="">Khan et al.</a> (2025)*
      </td>
      <td style="text-align:center;"><b>1.69 ± 3.36</b></td>
      <td style="text-align:center;"><b>81.18</b></td>
      <td style="text-align:center;"><b>87.28</b></td>
      <td style="text-align:center;"><b>90.82</b></td>
      <td style="text-align:center;"><b>94.82</b></td>
    </tr>
  </tbody>
</table>

<p><em>* Baseline model, currently under-review</em></p>

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
