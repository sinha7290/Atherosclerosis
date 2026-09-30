# Migration notes

This repository previously carried copies of lab-internal scripts
(`bone.py`). They only ran against one
filesystem and have been removed.

Helper functions the notebooks used now come from
[bioutils](https://github.com/sinha7290/bioutils):

| was | now |
|---|---|
| `bone.readList` | `bu.read_list` |
| `bone.saveList` | `bu.save_list` |
| `bone.printOLS` | `bu.ols_table` |
| `bone.getCode` | `bu.significance_code` |
| `bone.getPDF` / `closePDF` | `bu.open_pdf` / `bu.close_pdf` |
| `hu.plotCoef` | `bu.plot_coefficients` |
| `hu.censor` | `bu.censor` |
| `hu.uniq` | `bu.unique` |
| `StepMiner.fitstep` | `bu.step_threshold` |

## Calls that still need attention

- `bone.getEntries` - reads from the Hegemon database index
- `bone.processGeneGroupsDf` - requires a Hegemon analysis object

`bu.step_threshold` is an independent implementation of single-step StepMiner
thresholding, so thresholds can differ marginally and figures will not be
bit-identical.
