# From LDA to BERTopic: Advancing Topic Coherence in Analyzing Podcast Transcripts

## Overview
This project explores the application of topic modeling techniques on podcast transcripts as part of a research note for a Natural Language Processing class. The analysis compares Latent Dirichlet Allocation (LDA) and BERTopic models, focusing on their coherence scores and the effectiveness of transformer-based embeddings in improving topic analysis.

## Motivation
Podcasts contain rich and diverse content, making them ideal for analyzing nuanced topics in large datasets. This project aims to:
- Compare traditional (LDA) and modern (BERTopic) topic modeling techniques.
- Evaluate the coherence of topics generated by both models.
- Investigate how transformer-based embeddings enhance topic modeling performance.

## Citations
This project utilized the **Structured Podcast Research Corpus (SPORC)** dataset. We acknowledge the following work, and appreciate for providing a baseline for analysing podcast transcripts using modern NLP methods:

`@misc{litterer2024mappingpodcastecosystemstructured,
      title={Mapping the Podcast Ecosystem with the Structured Podcast Research Corpus}, 
      author={Benjamin Litterer and David Jurgens and Dallas Card},
      year={2024},
      eprint={2411.07892},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2411.07892}, 
}`

For more details about the dataset, please refer to their [arXiv paper](https://arxiv.org/abs/2411.07892).


## Key Findings
- **LDA Coherence Score**: 0.55 (Moderate)
- **BERTopic Coherence Score**: 0.63 (Good)
- BERTopic, leveraging transformer-based embeddings, outperforms LDA in semantic topic coherence, particularly in handling nuanced and varied content.

## Research Question
"How do LDA and BERTopic compare in generating semantically meaningful topics from podcast transcripts?"

## Features
- Preprocessing of podcast transcripts, including stop word removal and lemmatization.
- Implementation of LDA and BERTopic for topic modeling.
- Evaluation of model performance using coherence scores.
- Visualization of topic distributions and trends over time.

## Installation
### Prerequisites
Ensure you have Python 3.8 or above and the following libraries installed:
```bash
pip install pandas numpy matplotlib seaborn nltk spacy scikit-learn bertopic sentence-transformers umap-learn
```

### Clone the Repository
```bash
git clone https://github.com/yourusername/SPORC_TopicModelling.git
cd your-repo-name
```

## Usage
1. Preprocess the dataset using the provided scripts for cleaning and tokenization.
2. Run the `topic_modeling.py` script to generate and evaluate topics using LDA and BERTopic.
3. Visualize topic distributions and coherence scores using `visualizations.py`.

### Example Code
```python
from bertopic import BERTopic
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.decomposition import LatentDirichletAllocation

# Preprocess dataset
data = preprocess_transcripts("path/to/dataset.csv")

# Apply BERTopic
bertopic_model = BERTopic()
bertopic_topics, probs = bertopic_model.fit_transform(data["transcripts"])

# Apply LDA
lda_model = LatentDirichletAllocation(n_components=10, random_state=42)
lda_topics = lda_model.fit_transform(data["bow_matrix"])

# Evaluate and visualize
plot_topic_coherence(bertopic_model, lda_model)
```

## Results
- BERTopic generated more semantically coherent topics than LDA, as reflected by higher coherence scores.
- Transformer-based embeddings proved effective in handling diverse and nuanced podcast content.

## Visualizations
- **Topic Distributions**: Bar charts showcasing the most frequent topics.
- **UMAP Clustering**: Dimensionality reduction for visualizing topic embeddings.
- **Topics Over Time**: Trends in topic prevalence over specific periods (e.g., May-June 2020).

## Project Structure
```
|-- podcast/                # Please Create this Folder and Download the Sample Dataset 
|-- SPoRC_Analysis/           # Jupyter notebooks for exploration   
|-- README.md            # Project overview
```

**Sample DataSet**: Please download from this link: Hugging Face Library: https://huggingface.co/datasets/blitt/SPoRC/tree/main

## Future Work
- Explore additional transformer-based models (e.g., RoBERTa, BERT).
- Extend analysis to multilingual podcast datasets.
- Incorporate bias analysis and mitigation in topic modeling.

## Contributors
- **Nima Thing**: [LinkedIn](https://www.linkedin.com/nima-thing) | [GitHub](https://github.com/nimathing2052)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
