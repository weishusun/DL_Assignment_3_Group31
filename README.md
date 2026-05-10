# Assignment 3 — Image Captioning (VizWiz)

PyTorch image captioning project on the VizWiz-Captions validation set. Group XX, due 20 May 2026.


## Structure

```
Assignment_3_GroupXX/
├── data/                  # images, annotations, processed (git-ignored)
├── notebooks/             # 1 shared + 5 individual
├── src/                   # dataset, vocabulary, metrics, utils
├── checkpoints/           # model weights (git-ignored)
├── results/<name>/        # per-member metrics & samples
├── report/                # final report + meeting notes
└── docs/                  # division of work
```

## Setup

```bash
git clone https://github.com/<org>/Assignment_3_GroupXX.git
cd Assignment_3_GroupXX

conda create -n vizwiz python=3.10 -y
conda activate vizwiz

# Install PyTorch matching your CUDA version: https://pytorch.org/get-started/locally/
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121
pip install -r requirements.txt

python -c "import nltk; nltk.download('punkt'); nltk.download('punkt_tab')"
```

## Download Data

```bash
wget https://vizwiz.cs.colorado.edu/VizWiz_final/images/val.zip -P data/
unzip data/val.zip -d data/images/ && rm data/val.zip

wget https://vizwiz.cs.colorado.edu/VizWiz_final/caption/annotations.zip -P data/
unzip data/annotations.zip -d data/annotations/ && rm data/annotations.zip
```
Expected layout after extraction:

```
data/images/val/VizWiz_val_*.jpg   (7,750 images)
data/annotations/val.json
```
## Phases

- **Phase 1** — Shared data prep in `notebooks/00_shared_data_preparation.ipynb` (all members).
- **Phase 2** — Each member trains Model 1 in their own notebook. Group meeting after.
- **Phase 3** — Each member trains Model 2 in the same notebook, reflecting on group discussion.




## Evaluation

Mandatory: BLEU-1, BLEU-2, BLEU-3, BLEU-4. Optional: METEOR, CIDEr, qualitative samples.

