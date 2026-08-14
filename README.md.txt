# Turkish Universities Sentiment Analysis Dataset (Real + Synthetic)

This dataset contains **Turkish tweets related to universities** collected from the Twitter/X platform and labeled for **sentiment analysis**.

The dataset was created for the research study:

**"Deep Learning Based Sentiment Analysis of Turkish Universities on X"**

It includes both:
- **Real tweets collected via Twitter/X API**
- **Synthetic tweets generated using LLM-based paraphrasing** to balance the sentiment distribution

---

## Files

### 1) `real_dataset.csv`
Contains only real tweets related to Turkish universities, collected from publicly available Twitter/X accounts.

**Columns:**
- `type` : data type (tweet)
- `url` : tweet URL (source evidence)
- `tags` : sentiment label
- `text` : tweet content
- `createdAt` : tweet creation time
- `location` : location info (if available)
- `authorUserName` : tweet author username
- `university` : referenced university category

---

### 2) `real_synthetic_dataset.csv`
Contains both real and synthetic tweets merged into one dataset.

**Columns:**
- `text` : tweet content
- `tags` : sentiment label
- `is_synth` : indicates whether the sample is real or synthetic
- `university` : referenced university category

---

## Labels

### Sentiment (`tags`)
- `0` = Negative
- `1` = Positive

### Synthetic Flag (`is_synth`)
- `0` = Real tweet (collected via API)
- `1` = Synthetic tweet (LLM paraphrased)

---

## Data Collection and Labeling Process

1. Tweets were collected from **public Twitter/X accounts** via the Twitter/X API.
2. Approximately **7,500 tweets** were manually labeled with sentiment classes (`0`, `1`, and `9`).
3. A **BERTurk model** was fine-tuned using the manually labeled dataset.
4. The fine-tuned model was used to automatically label newly collected university-related tweets.
5. Automatically labeled tweets were manually reviewed to ensure label quality.
6. The real dataset was imbalanced (**~75% negative, ~25% positive**).
7. To balance the dataset, around **6,000 synthetic tweets** were generated using **LLM-based paraphrasing (ChatGPT-5)**.
8. Synthetic samples were manually reviewed to preserve sentiment meaning.
9. Duplicate and near-duplicate texts were filtered using **LSH MinHash clustering**.

---

## Dataset Statistics

- Real tweets: **11,020**
- Synthetic tweets: **6,168**
- Total samples: **17,188**

---

## Notes

- This dataset is shared for **research and educational purposes**.
- Tweets were collected only from publicly accessible accounts.
- Synthetic samples were created via paraphrasing to increase data diversity while preserving sentiment.

---

## Suggested Use Cases

- Sentiment analysis of Turkish universities on Twitter/X
- Turkish NLP benchmarking
- Text classification tasks
- Fine-tuning transformer-based models (BERTurk, ELECTRA, RoBERTa, etc.)
- Social media analysis and opinion mining

---

## Citation

If you use this dataset in academic work, please cite the Kaggle dataset page or the associated publication.

---

## License

Please check the Kaggle license selected for this dataset.
