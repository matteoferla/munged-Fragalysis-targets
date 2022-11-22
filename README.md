# munged-Fragalysis-targets
An small crosstabulation of what the public Fragalysis targets are.

> [Go to table](targets.md)

## Nota Bene
The target names may differ from Uniprot preferred name because:

* The target names in Fragalysis may end in an 'A', this is a SGC/CMD thing and is how protein are stored in Scarab
* The protein/gene goes by multiple names —this is normal
* The target may be a viral protein expressed as a single polyprotein chain that is cleaved by a protease
* The target may be know as the domain

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
* `targets_blast.p` a `Dict[str, Bio.Blast.Record.Alignment]`
* `targets.fasta` the seqs as they are in Fragalysis
* `targets_mol.p` the mol data as in Fragalysis

## Potential improvements

Some entries lack sequences. This is because they predate when
Rachael implemented the sequence in the API.

The taking of the first hit in the blast search is a poor choice —i.e. chimp
The `Bio.Blast.Record.Alignment` instances in 
`targets_blast.p` have an attribute `.hsps`, which is a `List[Bio.Blast.Record.Hsp]`.
The first couple may have close scores...

The Uniprot XML schema is byzanthine thing. The JSON conversions are likewise confusing.
I have missed a lot of juicy things.

I stored in some cells of the `pandas.DataFrame` values as tuples, which was a mistake.
I thought that `.fillna(tuple())` was okay but it is as unwelcome as `.fillna(list())`.
But majorly, these do no export well, but I am not a fan of pipe seperated fields.
