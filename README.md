# Tranformer-Networks-Attention-is-All-you-Need-
This project investigates the efficacy of the ELECTRA transformer model in detecting fake news, focusing on leveraging sentiment analysis to enhance detection accuracy. Using datasets like GoEmotion, LIAR, and Sentimental LIAR, this study explores the statistical relationship between sentiment scores and news veracity, evaluates the impact of incorporating sentiment features, and compares the performance of ELECTRA models trained on different datasets. The findings contribute to advancing fake news detection by integrating sentiment analysis with state-of-the-art transformer models.
## Datasets
The following datasets were used:
### GoEmotion Dataset:
Comprises 58,000 Reddit comments annotated across 27 emotion categories.
Preprocessed to merge positive and negative emotions into binary classes (positive/negative) while excluding neutral emotions.
Post-processed using upsampling to address class imbalance.
### LIAR Dataset:
Contains 12,836 short statements from PolitiFact spanning 10 years.
Includes metadata such as speaker, context, and job title.
Labels were binarized (e.g., "half-true" and "mostly true" merged into "true").
### Sentimental LIAR Dataset:
An extension of the LIAR dataset with sentiment scores assigned using Google's NLP API.
Includes emotional undertones scored based on sadness, anger, disgust, fear, and joy.
Preprocessing steps included text normalization (removal of HTML tags, special characters, stop words), tokenization using ELECTRA's tokenizer, and scaling sentiment scores for feature integration.
## Method
The methodology involved:
### Exploratory Data Analysis (EDA):
Examined text length distributions and label imbalances across datasets.
Performed statistical analysis (T-tests) to explore relationships between sentiment scores and news labels.
### Model Architecture:
ELECTRA Small Transformer Model: A computationally efficient transformer with 12 layers.
Fine-tuned for both sentiment classification and fake news detection tasks.
### Training Process:
Pretrained ELECTRA models were fine-tuned on GoEmotion for emotion classification and Sentimental LIAR for sentiment classification.
Sentiment features were integrated with metadata (e.g., speaker, context) for fake news classification.
### Evaluation Metrics:
Accuracy, precision, recall, F1-score, AUC-ROC metrics were used to evaluate model performance.
### Experiments:
#### Experiment 1: Baseline ELECTRA model without additional features.
#### Experiment 2: ELECTRA model with sentiment features only.
#### Experiment 3: ELECTRA model with sentiment features combined with metadata.
## Results
Key findings include:
A weak but statistically significant correlation between sentiment scores and fake news labels (p-value < 0.05).
Incorporating sentiment features alone slightly reduced performance compared to the baseline.
Combining sentiment features with metadata significantly improved performance:
### Best accuracy: 64%
### AUC-ROC score: 0.89
ELECTRA models trained on GoEmotion outperformed those trained on Sentimental LIAR for emotion classification tasks due to better dataset quality and annotation consistency.
## Future Work
Future directions include:
Developing hybrid models that integrate multimodal data (e.g., visual or network-based features) alongside text and metadata.
Addressing class imbalance issues through advanced sampling techniques or loss function modifications.
Exploring other transformer-based architectures (e.g., RoBERTa or DeBERTa) for comparison.
Implementing explainable AI techniques to improve model transparency in decision-making processes.
This structure provides a clear overview of your project while detailing datasets, methods, results, and future directions comprehensively.
