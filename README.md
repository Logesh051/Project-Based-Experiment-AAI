<H3>NAME: Logesh.N.A</H3>
<H3>REGISTER NO.: 212223240078</H3>
<H3>DATE: 08-08-2026</H3>

<H1 Align="center">Project Based Experiment</H1>

<H3>Objective:</H3>

### To perform sentiment analysis on a small Facebook text dataset using VADER and count the number of occurrences of the name "Tom" in the extracted text.

<H3>Program:</H3>

```python
import pandas as pd
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

nltk.downloader.download('vader_lexicon')

file = "FacebookPosts.xlsx"

xl = pd.ExcelFile(file)
dfs = xl.parse(xl.sheet_names[0])
dfs = list(dfs['Timeline'])

sid = SentimentIntensityAnalyzer()

for data in dfs:
    ss = sid.polarity_scores(data)
    print(data)
    for k in ss:
        print(k, ss[k])

count = 0

for data in dfs:
    count += data.lower().count("tom")

print("Number of occurrences of Tom:", count)
```

<H3>Output:</H3>

<img width="910" height="392" alt="image" src="https://github.com/user-attachments/assets/a2a4d8f4-3dcc-4bf7-904b-7774de6af48c" />


The program also displays the sentiment scores (negative, neutral, positive, and compound) for each Facebook post.

<H3>Inference:</H3>

From this experiment, I learned how to perform basic sentiment analysis on text data using the VADER sentiment analyzer. I also learned how to extract text from an Excel dataset and count the occurrences of a specific word or name. The name "Tom" occurred 18 times in the given dataset.
