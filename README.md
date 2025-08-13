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
- Google Colab Notebook [here](https://colab.research.google.com/github/nuitrcs/AI_Week_RAG/blob/main/rag.ipynb)

## Working locally?
We don't have much time to help you get things to work locally, so I will assume you know mostly know how to create and manage environments. If you run into problems please switch to Google Colab.

After you clone this repo, you'll need to create a new virtual environment and install the relevant dependencies. Here's a quick how-to for `Anaconda` and for `uv`.

**Conda / Anaconda**

Create a new conda environment. Install the packages listed in the `dependencies` section of the *pyproject.toml* file. If you use the anaconda navigator, you can do this using the point and click interface (I will show this option to the class).

**uv / pyenv / etc.**

If you are using another environment management tool, I'll let you figure it out yourself. For example, if you have `uv` this is quite straightforward, once you clone the repo, on the repo's root directory in the terminal you have to do:
```bash
# MacOS /Linux
uv sync
source .venv/bin/activate

# Windows
uv sync
.venv\Scripts\activate
```


## Miscellaneous
--REVISE--

If you're running into threading conflicts due to `umap`clashing with `faiss` or `transformers`, this may help.

```python
# Helps with threading issues
import os
os.environ["OMP_NUM_THREADS"] = "1"
os.environ["MKL_NUM_THREADS"] = "1"
```