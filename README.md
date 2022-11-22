# munged-Fragalysis-targets
An small crosstabulation of what the public Fragalysis targets are.

> [Go to table](targets.md)

## Rationale
As of November 22 the targets in [Fragalysis](https://fragalysis.diamond.ac.uk/) do not bear protein metadata.
This is an attempt at rectifying it.

Two caveats:

* this is uncurated data —there's a chimp protein in the final table
* there are many _private_ targets, this is only the _public_ ones

## Contents
Files herein:

* `Fragalysis_targets.ipynb`: the notebook
* `targets_df.p` (and it's exports `targets.csv` and `targets.md`) is a pickled `pandas.DataFrame`
* `targets_blast.p` a `List[Bio.Blast.Record.Alignment]`
* `targets.fasta` the seqs as they are in Fragalysis
* `targets_mol.p` the mol data as in Fragalysis
