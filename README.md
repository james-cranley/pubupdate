# README

## `pubupdate` grab your publications info

Uses this a mildly modified version of [this script](https://github.com/MrPike/orcid-to-bibtex) for the first step.

## Install

```bash
git clone git@github.com:james-cranley/pubupdate.git
cd pubupdate
conda env create -f environment.yaml
conda activate pubupdate
```

## Run

```bash
# Step 1: grabs publications associated with your ORCID
python orcid2bib.py <ORCID> -o pubs.bib

# Step 2: formats them into Academic Standard format, ready for copy/paste into LaTeX
python bib2cv.py pubs.bib pubs.xlsx --highlight-name Bloggs_J

# Step 3: get latest citations data from OpenAlex API
python citations.py <OpenAlexAuthorID> -o citations.txt
```

Example using my details

```bash
python orcid2bib.py 0000-0002-0408-5801 -o pubs.bib
python bib2cv.py pubs.bib pubs.xlsx --highlight-name Cranley_J
python citations.py A5023528834 -o citations.txt
```
