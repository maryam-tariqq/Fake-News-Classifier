## Fake News Classifier System
Developed a fake news detection system to classify news as real or fake using Distilbert. The project uses ISOT Fake News Dataset and explores tranformer based text classification for idenitfying patterns.

The workflow includes dataset preparation, cleaning and preprocessing of news articles, tokenization using the DistilBERT tokenizer. As the model has a maximum input length, we uses token bases chunking. Since a long article can produce multiple chunks, each chunk is classified individually and the predictions are then aggregated to generate a single article-level prediction.

### Results
The final experiment used 1,000 articles from the ISOT Fake News Dataset, split into 70% training, 15% validation, and 15% test sets. The first four DistilBERT layers were frozen, while the remaining layers and classification head were fine-tuned for one epoch.

Article-level predictions were obtained by averaging the Fake-class probabilities across an article's chunks.

On the article-level test set, the experiment achieved 98.0% accuracy, 97.18% precision, 98.57% recall, and 97.87% F1-score.

### Interpreting the Results
The 98% accuracy reflects performance on the ISOT dataset, not general real-world misinformation detection.

ISOT contains dataset-specific differences between Real and Fake articles, including source, vocabulary, formatting, and writing style. The model may therefore learn some of these patterns alongside features useful for classification, which may contribute to the high performance.

### Important Limitation
The test set contained. 150 articles, so the repoted metrics are based on a small evaluation set.

### Takeaway
The project demonstrates DistilBERT-based fake-news classification, token-based chunking for long articles, and article-level prediction aggregation. The results are strong on the selected ISOT subset, while dataset-specific biases should be considered when assessing generalization.
