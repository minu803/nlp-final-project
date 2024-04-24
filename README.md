# Words that Move Markets: Leveraging TF-IDF and Machine Learning to Forecast Stock Market Trends from Financial News

## Introduction
In the complex world of financial markets, individual investors often find themselves at a disadvantage due to a lack of deep understanding and expertise that professional analysts possess. To bridge this gap, this project leverages Natural Language Processing (NLP) to extract valuable investment insights from financial news articles. Utilizing a comprehensive dataset from HuffPost, which encompasses about 210,000 articles from January 2012 to September 2022, this analysis focuses on the stocks of the "Magnificent Seven" (M7) companies—Alphabet, Amazon, Apple, Meta, Microsoft, Nvidia, and Tesla. These firms, which accounted for approximately 32% of the economic profit of all listed U.S. firms as of 2022, play a crucial role in the U.S. economy and are key indicators of broader economic health and market trends.

## Research Question
The primary aim of this study is to explore the predictive power of linguistic patterns in financial news articles on stock market movements. Using the term frequency-inverse document frequency (TF-IDF) metric, this research seeks to identify and quantify the impact of specific terms and phrases found in the coverage of the M7 companies. The study is driven by the following research questions:
- **Primary Research Question:** Can linguistic patterns in financial news, as quantified by TF-IDF metrics, predict stock market conditions—specifically distinguishing between bull and bear markets for the M7 companies?
- **Secondary Research Questions:**
  - What specific terms or phrases from the financial news are most strongly associated with shifts in the stock prices of the M7 companies?
  - How do variations in the frequency and significance of these terms correlate with the performance indicators of bull and bear markets?

## Data
The analysis utilizes two primary data sources:
- **News Articles:** The dataset includes around 210,000 articles from HuffPost, covering news from January 2012 to September 2022.
- **Stock Data:** Weekly stock data from Yahoo Finance for the M7 companies, used to track the weekly percentage change in stock index price, categorizing weeks as 'bull' or 'bear' based on the performance.

## Method
### Data Collection
- **HuffPost News Data:** Sourced from Kaggle, this dataset comprises approximately 210,000 news headlines collected between 2012 and 2022, used to analyze a decade of news coverage.
- **Yahoo Finance API:** Used to retrieve weekly stock price information for the M7 companies, covering the same period as the news articles.

### Data Processing
#### News Data Preprocessing
- **Filtering and Cleaning:** Articles were filtered to include only those relevant to the M7 companies. Promotional content and duplicates were removed, reducing the dataset to 1,390 significant articles.
- **Text Aggregation:** News texts were aggregated weekly, concatenating all articles published within the same week.

#### Stock Data Preprocessing
- **Data Retrieval:** Daily stock prices were retrieved and adjusted for corporate actions to get the 'adjusted close prices.'
- **Index Construction:** An equal weight index was created for the seven companies to standardize the comparison of collective stock performance over time.

### Linguistic Analysis
- **TF-IDF Computation:** This technique evaluates the importance of a word within documents relative to the corpus. The formula used is:
  - TF (Term Frequency) = (Number of times keyword appears in a document) / (Number of words in the document)
  - IDF (Inverse Document Frequency) = log((Number of documents) / (Number of documents containing the keyword))
  - TF-IDF = TF * IDF
- This method identifies significant words that are prevalent in specific documents but rare across all documents, highlighting their unique importance to the topic.

### Statistical Analysis (Machine Learning)
#### Machine Learning Models
- **Logistic Regression:** Used to predict market conditions (bull or bear) based on the TF-IDF scores of terms found in financial news articles. It assesses the likelihood of market movements based on the linguistic cues within the news.
- **Multinomial Naive Bayes (MNB):** Applies Bayes' theorem with the "naive" assumption of independence between features. MNB is effective for text data where frequency and presence of words predict the classification.
- **Gradient Boosting Machines (GBM):** Uses an ensemble of decision trees to predict market trends, improving predictions by minimizing errors through gradient descent.

#### Evaluation Metrics
- **Accuracy:** Measures the overall correctness of the model = (TP + TN) / (TP + TN + FP + FN)
- **Precision:** Measures the accuracy of positive predictions = TP / (TP + FP)
- **Recall:** Measures the coverage of actual positive samples = TP / (TP + FN)
- **F1-Score:** Harmonic mean of precision and recall = 2 * (Precision * Recall) / (Precision + Recall)

These algorithms and metrics help quantify the predictive power of linguistic features extracted from financial news on stock market trends, specifically focusing on their ability to distinguish between bull and bear market conditions.

## Conclusion
This research endeavors to demystify the complex language of finance and provide individual investors with actionable insights derived from the linguistic patterns in financial news. By demonstrating how specific terms and their frequencies correlate with market trends, this study enhances our understanding of how information dissemination affects market behavior and offers new avenues for predictive analytics in finance.


