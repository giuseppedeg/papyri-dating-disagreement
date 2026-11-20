# A palaeographic date is a distribution, not a point

Data and code for the paper *A palaeographic date is a distribution, not a point: expert disagreement as ground truth for the dating of Greek papyri* ().

Eighteen experts dated, from the script alone, 20 Greek documentary papyri whose writing date is known. Each expert gave a date range and a confidence level. We release their anonymised answers and a notebook that recomputes the results of the paper.

## Contents

| File | What it is |
|---|---|
| `expert_disagreement.ipynb` | All the experiments of the paper, section by section, with tables and figures |
| `data/expert_answers.csv` | The 360 expert answers (20 papyri x 18 experts) |
| `data/vlm_answers.csv` | The answers of four open vision–language models on the same crops |
| `figures/` | The figures, as written by the notebook |

## Data

`data/expert_answers.csv`, one row per papyrus and expert:

| Column | Meaning |
|---|---|
| `papyrus` | Papyrus id (P01–P20, sorted by true date) |
| `tm_number` | Trismegistos number |
| `true_date` | Year written in the document (BC years are negative) |
| `period` | Ptolemaic, Roman or Byzantine |
| `expert` | Anonymous expert id (E01–E18) |
| `expert_periods` | Periods the expert knows best (self-reported) |
| `date_from`, `date_to` | Earliest and latest plausible year given by the expert |
| `confidence` | Confidence self-estimate given by the expert, 1 (not confident) to 5 (extremely confident) |
| `requested_info` | Extra information that would help the expert (multiple choice, empty if none) |

`data/vlm_answers.csv`, one row per model, papyrus and sample: `model`, `papyrus`, `sample` (0–29, plus `greedy`), `date_from`, `date_to`, `confidence`. The paper uses the 30 sampled answers.

The images of the papyri are not included.

## Run

```bash
pip install -r requirements.txt
jupyter notebook expert_disagreement.ipynb
```

The notebook runs in a few minutes on a laptop.

## Citation

Paper under review. Citation will be added here.
