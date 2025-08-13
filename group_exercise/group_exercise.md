# Group Exercise

Now is your turn to create a RAG system from beginning to end!

## Instructions

1. I will provide 3 datasets to you, each with possible research questions to explore. Pick only one question.
2. You will coalesce in teams, each team will be assigned one of the 3 datasets (this may be flexible, depending on interest and number of people).
3. If you need or want to modify your question, that is fine! Just make sure the whole team is on board.
4. As a team, you must decide how to tackle that research question with your dataset and with your knowledge of RAG.
5. Build the RAG system from scratch, and present it as a tool for answering the research question.
6. We will stop at xx:xx. We will then present the final product and share any tips or challenges we encountered as a team.

### Team Notes
- Make sure everyone in your team has time and space to express themselves, and that all opinions and ideas are considered equally.
- Remember that some people speak softer, or with fewer words. Loudest is not always more valid!
- Strive for a 'flat' team structure. But if you want some organization, you can have 'facilitator' roles (I try to avoid the term 'leader', as it often results in counterproductive results for true innovation and team collaboration).
- Be flexible, be open, and have fun!

### Optional
- If you have an exciting dataset you want to try RAG on, and a research question accompanying it, feel free to propose a new group!
- You may want to experiment with other models for embedding or generation. For example, nomic-ai's embedding models are pretty popular, you can check others [here](https://huggingface.co/spaces/mteb/leaderboard). Note that if you use other models you must consider a few extra things, for example size (some are a few GBs in size), security (they must be from trusted institutions, some will require to run extra code that you must trust), task specificity (you may need to add to your queries that you are doing semantic search, for example) and modality (are they for text, for images, for sound, multimodal?).

## Choosing an index
For large datasets, try HNSW.

## Cases

### Option A: Shakespeare's Plays

**Dataset:** Shakespeare's plays

The file `shakespeare_plays.csv` contains the text of (all?) Shakespeare's plays. I got it from
[this kaggle user](https://www.kaggle.com/datasets/guslovesmath/shakespeare-plays-dataset). I've also prepared two other versions of the dataset you may want to use (see `supplementary.ipynb` for preparation):
- `shakespeare_plays_by_speech.ipynb`, which is separated by dialogue turn (speech), instead of by lines.
- `shakespeare_plays_by_context.ipynb`, which adds $5$ lines before and after to account for context.

**Question 1**

Did associations we have today to certain words or concepts hold in Shakespeare's times? For example, does the word 'darkness' take the same meaning in Shakespeare's plays as it does in our modern parlance?
- I thought about this when reading the following line in King Lear: "Meantime we shall express our darker purpose. Give me the map there. Know that we have divided in three our kingdom". It seems like "darker" is being used as "more serious" or "more private", but definitely with no connotations to "evil" or "treacherous" as we may think today.

**Question 2**

Do male and female characters express or experience agency in the same way? To what extent fate and external forces overwrite a character's capacity to realize their will?
- Hint: if you want to make sure you get a number of relevant results per character sex, you can separate your data and make an index for each category.


### Option B: Scientific Methods

**Dataset:** arXiv

This data is from the [arxiver project](https://huggingface.co/datasets/neuralwork/arxiver). It contains abstracts and full text of arXiv papers from 2023. I've prepared a small subsample of $500$ articles, around $25$ MB in size, to conform to GitHub's size limits. However, I recommend you download the full dataset (see `load_arxiv.ipynb` for help) if possible. It shoudl be about $5$ GB. Most papers are astronomy or AI related (sorry, that was the creator's choice, not mine), but there might be enough of other topics.

You will need to decide as a team if you should embed only abstracts, full paper text, or chunk the full paper into paragraphs or sections and embed those.

**Question 1**

What is the relationship between the development of novel tools and methods in AI and scientific demands and/or discoveries? For example: do scientific questions elicit new AI methodology, or do established AI models limit its application to science?

**Question 2**

How are common scientific methods or concepts treated and evolved across disciplines, and can we identify such commonality for the mutual benefit of the fields involved? For example, pick one of:
- Sampling and randomization techniques
- Data sharing protocols
- Simulation frameworks for inference
- Specific algorithmic tasks like dimensionality reduction

Then compare how different fields approach it: contrast methods, terminology, and underlying assumptions and philosophy.

### Option C: The Wikipedia corpus

**Dataset:** Wikipedia

This dataset is available through Hugging Face, [here](https://huggingface.co/datasets/wikimedia/wikipedia). I've prepared a small subsample for you in case you can't download it yourself (see `data` folder).
The subsample is not too big because of the GitHub file limitations. But you can download more of the data yourself. I made a little notebook to help you with that (see `load_wikipedia.ipynb`).

Wikipedia is such a rich set, you can build a RAG to answer a wide variety of research questions! Below I have some examples for you, but if you have one you want to explore go ahead. Just make sure it is well posed and specific, and that everyone in the group agrees with it.

**Question 1**

What role have dreams played in humanity's cultural practices? For example, are they used as metaphors for creativity and innovation in art and science? Are they linked to religious experience? Do they play a role in the creation and transmission of myths? Are there commonalities across cultures around the world?

**Question 2**

Is there a common structure to "revolutions", broadly understood? For example, do revolutions in science follow a similar process as revolutions in political systems? What elements does the agrcultural revolution share with the writing/literacy revolution? Are there non-human revolutions (for example, geological or evolutionary events) following similat patterns?
