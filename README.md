# Small molecule retention by Gram-negative bacteria based on a large-scale LC/MS screen

Predicts whether a small molecule accumulates inside Escherichia coli, the barrier that decides if a potent compound ever reaches its target in a Gram-negative cell. Le Goff and colleagues at Idorsia screened 13,056 compounds by mass spectrometry against a wild-type strain and an efflux-deficient TolC mutant and labelled 6,416 of them retention-positive or negative. Ersilia trained a LazyQSAR classifier on 6,407 of these, 2,879 retained, with a five-fold out-of-fold AUROC of 0.89. Retention in E. coli does not by itself confer antibacterial activity.

This model was incorporated on 2025-12-12.
Last packaged on 2026-11-23.

## Information
### Identifiers
- **Ersilia Identifier:** `eos5bsw`
- **Slug:** `ecoli-retention`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Activity prediction`
- **Biomedical Area:** `Antimicrobial resistance`, `Diarrheal diseases`
- **Target Organism:** `Escherichia coli`
- **Tags:** `Antimicrobial activity`, `Gram-negative bacteria`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `1`
- **Output Consistency:** `Fixed`
- **Interpretation:** Rank score of retention inside Escherichia coli combining uptake with escape from efflux, calibrated against the Ersilia reference library of 50K compounds. A score above 0.65 beats 99% of that library. Trained on 2879 retained compounds against 3528 non-retained.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| retention_rank | float | high | Rank score of the compound's predicted retention inside Escherichia coli. Calibrated against 50K compounds from the Ersilia reference library so that a score of 0.65 is better than 99% of them. Recommended threshold: 0.65. |


### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos5bsw](https://hub.docker.com/r/ersiliaos/eos5bsw)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos5bsw.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos5bsw.zip)
- **Apptainer**: [https://models-sif.s3.eu-north-1.amazonaws.com/eos5bsw_v2.sif](https://models-sif.s3.eu-north-1.amazonaws.com/eos5bsw_v2.sif)

### Resource Consumption
- **Model Size (Mb):** `42`
- **Environment Size (Mb):** `6954`
- **Image Size (Mb):** `3287.78`

**Computational Performance (seconds):**
- 10 inputs: `30.88`
- 100 inputs: `22.78`
- 10000 inputs: `95.4`

### References
- **Source Code**: [https://github.com/ersilia-os/lazy-qsar](https://github.com/ersilia-os/lazy-qsar)
- **Publication**: [https://doi.org/10.1038/s41598-025-10208-6](https://doi.org/10.1038/s41598-025-10208-6)
- **Publication Type:** `Peer reviewed`
- **Publication Year:** `2025`
- **Ersilia Contributor:** [miquelduranfrigola](https://github.com/miquelduranfrigola)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [GPL-3.0-or-later](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos5bsw
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos5bsw
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!
