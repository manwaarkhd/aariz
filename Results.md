## Results

This section reports the performance of different models evaluated on the Aariz cephalometric dataset. The comparative results are summarized in the table below, with metrics including Mean Radial Error (MRE) and Success Detection Rates (SDR) at clinically relevant thresholds (2.0 mm to 4.0 mm).

| Paper        | MRE ± SD (mm)    | SDR 2.0mm (%) | SDR 2.5mm (%) | SDR 3.0mm (%) | SDR 4.0mm (%) |
|--------------|--------------:|----------:|----------:|----------:|----------:|
| [Khalid et al. (2024)](https://doi.org/10.1016/j.eswa.2024.124840)  |  |  |  |  |  |
| [Khan et al. (2024)](https://doi.org/10.1007/978-3-031-66958-3_1)  | 1.92 ± 7.85 | 78.44 | 85.47 | 89.49 | 94.44 |
| Khan et al. (2025)  | 1.69 ± 3.36  | 81.18 | 87.28 | 90.82 | 94.82 |

The **baseline model** presented in Khan et al. (2025) forms the foundation of this dataset’s methodology. It achieves an overall MRE of 1.69 mm, with 81.18% of landmarks falling within the clinically acceptable threshold of 2.0 mm.

### Category-wise Performance:
- **Soft tissue landmarks**: Achieved excellent performance, with all six registering MRE < 2.0 mm.
- **Dental landmarks**: Performed consistently well, with minor deviations exceeding the 2.0 mm threshold.
- **Skeletal landmarks**: Were generally more difficult, with most of the MREs > 2.0 mm falling in this category.

### Landmark Level Performance:
- **Top-Performing Landmarks**: Landmarks with MRE < 1.0 mm in either validation or test sets include Me, Pog, S, Gn, UIT, Li, Ls, Sn, Pn. Notably, four landmarks reached 100% SDR in both sets.
- **Challenging Landmarks**: Landmarks with MRE > 2.0 mm in either set include N, Or, R, Ar, Co, Go, LPM, LMT, UPM, UMT. Despite higher MREs, these still achieved moderate SDRs between 49.00% and 87.34% within the 2.0 mm range.

#### Baseline -  Validation Set Results

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


#### Baseline - Test Set Results

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
