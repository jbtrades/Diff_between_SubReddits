# Project 3: Web APIs & NLP

# Galactic vs Stock Talk

**My Automoderator is the future of the internet but still deeply imperfect**

![](https://cdn0.tnwcdn.com/wp-content/blogs.dir/1/files/2019/08/reddit-deleted-posts-comments-threads-796x450.jpg)



*Humans and Technology...what's the worst that could happen?*
-------------------------------------------------------------------------------
**Banishing Tin foilers and tracking down Ponzies— Reporting for duty on the front lines, within the social site’s volunteer army.**


# Background:

**I’m a moderator for a popular Finance related subreddit….I’m lazy, so I built a script/model to detect non-related posts and automatically remove it from my precious forum.**


# Problem Statement:

Could I build an NLP model that reduces tinfoil posts on my assigned subreddit with high degree of accuracy?


# Data:

  - Reddit SubReddit Posts in the following;

	- Aliens SubReddit
	- Stocks SubReddit


| Index | title | subreddit |
| --- | --- | --- |
| **0** | Prophet Yahweh summons UFO for ABC News | Aliens |
| **1** | What's the best defense sector company to invest in? | Stocks |


# Methodology:

  - Data Cleaning - Removed Https, www, white spaces, symbols etc.
  - PRAW - Data Sourcing
  - NLP - Word Tokenizers
  - Modeling - Classification models


# EDA:

- Just, Like , Year were very common in both Aliens and Stocks reddits

- See EDA workbook in notebooks folder in for visuals


# Data Preprocessing:

   - Vectorizing - Countvectorizer , TfidfVectorizer

   Params = english stop words + ha, wa, im, doe , max_features=5000

   - RegexpTokenizer

   - WordNetLemmatizer


# Modeling:
  - Features = title
  - Models used = Log Reg, Random Forest, SVM C
  - Gridsearching + hyperparameter tuning


# Conclusions:
  - Overall my accuracy increased from Log reg(first model) to SVM my final model
  - Its safe to say Aliens and Stocks being the top words in their respective categorys helped classify the post
  - My aim was to maximise PPV or recall, it was achieved through the svm model with params {'C': 10.0, 'gamma': 0.1, 'kernel': 'rbf'} and TfidfVectorizer params 'english' stop words + "ha",'wa','im','doe'.


# Next Steps:
  - Remove common words that appear in greater frequencies in both subreddits
  - Add some numerical features such as title length and upper case words vs lower case
    
