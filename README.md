# Data Science for Civil Engineers: Coursework

My coursework for **CE49X Data Science for Civil Engineers** at Boğaziçi University, Spring 2025.
The course gave starter code and datasets for each assignment. This repository keeps only the
assignments I worked on, and each section says clearly which part is mine.

## Projects

| Folder | Topic | Method | Result |
|---|---|---|---|
| [`final_project`](final_project) | Life cycle assessment of 20 construction products | Python package, data validation, tests, analysis notebook | Steel causes about 34% of total carbon; a wood beam emits about six times less CO2e than a steel beam |
| [`labs/lab5`](labs/lab5) | Predicting concrete compressive strength from the mix design | Linear regression on 1,030 samples, 8 features | R² = 0.63, MSE = 96 MPa² on the test set |
| [`labs/lab6`](labs/lab6) | Classifying construction documents into 5 types | Text features with TF-IDF and metadata features, Naive Bayes pipeline | 100% accuracy on a synthetic dataset |
| [`labs/lab3`](labs/lab3) | Wind climate of Berlin and Munich from ERA5 data | Time series cleaning, monthly and seasonal statistics | Berlin is windier in every season, and both cities are calmest in summer |
| [`labs/lab2`](labs/lab2) | Soil test data | Missing values, outlier removal, descriptive statistics | Clean soil pH summary |
| [`labs/lab4`](labs/lab4) | Scientific plotting | Matplotlib, 3D surfaces | Plotting exercise |

### Notes on the results

- **Lab 5** is a simple baseline. Concrete strength depends on age and mix in a strongly non-linear
  way, so a linear model explains only about 63% of the variance. Non-linear models such as
  gradient boosting or neural networks are the natural next step for a surrogate model of
  material strength.
- **Lab 6** reaches 100% only because the course dataset is synthetic and the classes use very
  different words. The value of this lab is the pipeline that combines text and metadata, not the score.

## Who did what

| Part | Starter from the course | My work |
|---|---|---|
| Final project | Package layout, calculation core, tests, sample data | Rewrote data validation, changed visualisation and tests, wrote the full analysis notebook, all results and the reports. Details in [`final_project/README.md`](final_project/README.md) |
| Lab 2, Lab 3 | Starter script | Completed and rewrote the analysis |
| Lab 4 | Exercise notebook | My own plotting script |
| Lab 5, Lab 6 | Task description and dataset | All code |

The git history goes back to the course and shows the instructor's commits and my own commits with their original dates.

**Use of AI:** the coursework code dates from 2025, as the git history shows. In November 2026 I used
Claude, an AI assistant made by Anthropic, to clean up this repository and draft the README files.

## Running the code

```bash
pip install -r requirements.txt
cd labs/lab5 && python lab5.py
cd final_project && pytest
```

Each lab script reads its data from `datasets/` with a relative path, so run it from its own folder.

## Credits

- Course, starter code and teaching datasets by the CE49X instructor, Eyüphan Koç
  ([@eyuphankoc](https://github.com/eyuphankoc)), from the public course repository
  [CE49X-Spring25](https://github.com/eyuphankoc/CE49X-Spring25), shared under the MIT License.
  See [`LICENSE`](LICENSE).
- Concrete Compressive Strength dataset by I-Cheng Yeh, from the UCI Machine Learning Repository,
  licensed under CC BY 4.0. Its source is described in
  [`datasets/concrete_strength/Concrete_Readme.txt`](datasets/concrete_strength/Concrete_Readme.txt).
  Yeh, I-C. (1998), Modeling of strength of high-performance concrete using artificial neural
  networks, *Cement and Concrete Research*, 28(12), 1797-1808.
- Wind data: contains modified Copernicus Climate Change Service information 2025. Neither the
  European Commission nor ECMWF is responsible for any use that may be made of the Copernicus
  information or data it contains. Hersbach, H. et al. (2020), The ERA5 global reanalysis,
  *Quarterly Journal of the Royal Meteorological Society*, 146, 1999-2049.
