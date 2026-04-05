# Food-Recommender-System

## Environment Setup

This project uses a Conda environment called `recsys`.

The installation is split into steps on purpose. In particular, **PyTorch is installed separately** to avoid common Windows DLL issues when using `sentence-transformers`.

### 1. Prerequisites

Install:

- Anaconda or Miniconda
- Python 3.11 through Conda

Recommended on Windows:

- Close **Jupyter**, **VS Code**, and any running Python processes before installing packages
- Use **Anaconda Prompt** for setup

---

### 2. Create the environment

```bash
conda create -n recsys python=3.11 -y
conda activate recsys
python -m pip install -U pip setuptools wheel
```

### 3. Install base requiremnts

```bash
python -m pip install -r requirements.txt
python -m pip install --no-deps recmetrics
```

### 4. Install spaCy
```bash
python -m pip install spacy
python -c "import spacy; print(spacy.__version__)"
```

### 5. Install PyTorch separately
```bash
python -m pip install --index-url https://download.pytorch.org/whl/cpu torch torchvision torchaudio
python -c "import torch; print(torch.__version__)"
```


### 6. Install Sentence Transformers
```bash
python -m pip install sentence-transformers
python -c "from sentence_transformers import SentenceTransformer; print('ok')"
```

### 7. Register the Jupyter kernel
```bash
python -m ipykernel install --user --name recsys --display-name "Python (recsys)"
```
### 8. Final Verification
```bash
python -c "import spacy; import torch; from sentence_transformers import SentenceTransformer; print('all good')"
```