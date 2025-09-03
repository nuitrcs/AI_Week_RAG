# Building Retrieval Augmented Generation (RAG) Systems

## Repo Structure
The files and folders we care about are:
- `rag_001.ipynb`
- `rag_002.ipynb`
- `RAG_basics.pptx`
- `data` folder
- `group_exercise` folder
- `system_prompt` folder

If you are working locally, the following files will help you create a virtual environment. If you don't know what this is, ignore these files:
- `.python-version`
- `pyproject.toml`
- `uv.lock`


## Working on Google Colab?
- RAG - Part 1 [here](https://colab.research.google.com/github/nuitrcs/AI_Week_RAG/blob/main/rag_001.ipynb)
- RAG - Part 2 [here](https://colab.research.google.com/github/nuitrcs/AI_Week_RAG/blob/main/rag_002.ipynb)

## Working locally?
We don't have much time to help you get things to work locally, so I will assume you know mostly know how to create and manage environments. If you run into problems please switch to Google Colab.

After you clone this repo, you'll need to create a new virtual environment and install the relevant dependencies. Here's a quick how-to for `conda`, the `Anaconda Navigator` and for `uv`.

### Conda

On the command line, run:
```bash
conda create --name rag-workshop-env -c conda-forge python=3.11 jupyter pandas transformers sentence-transformers datasets
```
Followed by:
```bash
conda install --name rag-workshop-env -c pytorch faiss-cpu=1.12.0
```

Now, if you have ollama installed already in your computer, and you want to use it. The also run:
```bash
conda activate rag-workshop-env
```
followed by
```bash
pip install ollama
```

### uv / pyenv / etc.

If you are using another environment management tool, I'll let you figure it out yourself. For example, if you have `uv` this is quite straightforward, once you clone the repo, on the repo's root directory in the terminal you have to do:
```bash
# MacOS / Linux
uv sync
source .venv/bin/activate

# Windows
uv sync
.venv\Scripts\activate
```


## Miscellaneous

If you're running into threading conflicts due to `umap`clashing with `faiss` or `transformers`, this may help.

```python
# Helps with threading issues
import os
os.environ["OMP_NUM_THREADS"] = "1"
os.environ["MKL_NUM_THREADS"] = "1"
```