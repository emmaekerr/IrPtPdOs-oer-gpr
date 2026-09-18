# Data-Driven Composition Discovery in Rutile IrO<sub>2</sub>-Based Mixed-Metal Oxides for Enhanced Oxygen Evolution Catalysis

Supplementary code for the manuscript:

**Data-Driven Composition Discovery in Rutile IrO<sub>2</sub>-Based Mixed-Metal Oxides for Enhanced Oxygen Evolution Catalysis**
Emma Kerr,<sup>1,#</sup> Manish Kothakonda,<sup>2,3,#</sup> Kiran Srinivasan Hamkins,<sup>2,4,#</sup> Sungsoon Kim,<sup>4</sup> Nancy N. Kariuki,<sup>5</sup> Deborah J. Myers,<sup>5</sup> Michal Bajdich,<sup>2,\*</sup> Kirsten Winther,<sup>2,\*</sup> Jihyun Baek,<sup>4,6,\*</sup> and Xiaolin Zheng<sup>1,4,\*</sup>

<sup>1</sup> Department of Energy Science and Engineering, Stanford University, Stanford, California 94305, United States
<sup>2</sup> SUNCAT Center for Interface Science and Catalysis, SLAC National Accelerator Laboratory, Menlo Park, California 94025, United States
<sup>3</sup> Department of Chemical Engineering, Stanford University, Stanford, California 94305, United States
<sup>4</sup> Department of Mechanical Engineering, Stanford University, Stanford, California 94305, United States
<sup>5</sup> Chemical Sciences and Engineering Division, Argonne National Laboratory, Lemont, Illinois 60439, United States
<sup>6</sup> Department of Mechanical Engineering, National University of Singapore, Singapore

<sup>#</sup> These authors contributed equally. <sup>\*</sup> Corresponding authors.

This repository contains the Gaussian Process Regression (GPR) workflow used to model
oxygen evolution reaction (OER) overpotential as a function of Pt/Pd/Ir/Os composition,
including leave-one-out cross-validation, exhaustive screening of the composition
simplex, candidate ranking for the next round of experiments, a learning curve, single-
element sensitivity slices, and a SHAP analysis.

## Contents

| File | Description |
| --- | --- |
| `26_07_17_PublishedCode.ipynb` | Full analysis notebook (Part 1: LOOCV + screening; Part 2: retraining on all 55 samples) |
| `EC data_std dev.csv` | Experimental dataset: compositions, measured overpotentials, standard deviations |
| `requirements.txt` | Python dependencies |

Running the notebook writes the manuscript figures (SVG/PDF/EPS/PNG) into the working
directory.

## Requirements

Developed and run on Python 3.9. Install dependencies with:

```bash
pip install -r requirements.txt
```

## Usage

```bash
jupyter notebook 26_07_17_PublishedCode.ipynb
```

Run the cells in order. The cells share state: later blocks (ranking, learning curve,
sensitivity analysis, SHAP) reuse the fitted model and arrays created by the earlier
ones, so they are not independently executable.

The GPR fits are numerical optimizations; minor differences in predicted values across
scikit-learn versions are possible.

## Data

`EC data_std dev.csv` contains the experimental electrochemical measurements described
in the Methods section of the manuscript: [one or two sentences on how the data were
acquired, and the column definitions].

## Citation

If you use this code, please cite:

> Kerr, E.; Kothakonda, M.; Srinivasan Hamkins, K.; Kim, S.; Kariuki, N. N.; Myers, D. J.;
> Bajdich, M.; Winther, K.; Baek, J.; Zheng, X. Data-Driven Composition Discovery in
> Rutile IrO2-Based Mixed-Metal Oxides for Enhanced Oxygen Evolution Catalysis.
> [Journal], [Year]. doi:[DOI]

## Contact

Questions about the code and data: Michal Bajdich (bajdich@stanford.edu),
Kirsten Winther (winther@slac.stanford.edu), Jihyun Baek (jbaek@nus.edu.sg),
Xiaolin Zheng (xlzheng@stanford.edu).

## License

Released under the MIT License — see `LICENSE`.
