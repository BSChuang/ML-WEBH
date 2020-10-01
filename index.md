## Exposing Fake COVID-19 News

<img src="CS 4641 Proposal Video Presentation.png">

### Introduction
With the emphasis of social media on our present day society, information is being spread faster than ever. Users can stay up to date with the internet’s latest trends, political activity, and possibly the hottest topic of 2020, Covid-19 related news. However, while great at quickly sharing news, social media also allows for anybody to post information as the truth, regardless if the facts are accurate. The goal of our machine learning project is to create a model to detect Covid-19 related “fake news”, or untrue information, presented as real news found in social media. Our model will be able to tell whether an article is related to Covid-19 and from there, decide whether the article presents factual information.

Users must remain vigilant and rely on their intuition or fact-check the articles they read to guarantee its validity. However, with the constant stream of information and posts, this rarely happens. Data scientists have created “fake news” classifiers in the past, but nothing on the same scale has been done with Covid-19 news. Creating an unbiased classifier tailored to check articles under this topic will be extremely helpful to determine the true developments regarding Covid-19.


### Methods
Although some specifics are still in flux, we have already established a high level plan for the completion of this project. We are currently evaluating three datasets as possible sources:

1. [Kaggle Fake News](https://www.kaggle.com/c/fake-news/data)
2. [TweetsCOV19](https://data.gesis.org/tweetscov19/#dataset)
3. [CoAID](https://github.com/cuilimeng/CoAID/tree/master/07-01-2020)

Each dataset has distinct advantages and disadvantages. CoAID is the most directly topical, containing various social media posts and labels regarding truth / falsehood. However, it also quite limited in size, which may ultimately limit the predictive power of our model. TweetsCOV19 is larger, but lacks truth / falsehood labels. However, the TweetsCov19 dataset may still be of use when it comes to topic modeling and unsupervised learning. The Kaggle dataset is the largest and most popular option, but does not correspond directly to our project's goals. Instead of containing data regarding misleading social media posts, it instead focuses on fake news articles. Despite this domain mismatch, we do believe that models trained on the Kaggle dataset will likely generalize to social media posts fairly well.

To actually train the classifier, we will first need to "vectorize" the input social media posts. In essence, this means converting the body text of the post into a numerical vector representation. We plan to explore a variety of techniques for this task, including TF-IDF, Doc2Vec, and BERT. The ultimate choice will likely require us balancing the performance of the classifier with the difficulty of implementing each encoding strategy.

Prior to the training of the classifier (which discriminates between true and fake news), we plan to use unsupervised learning to get a better feel for our data. We envision two main uses. First, we'd like to perform k-means clustering on the embedded representations of articles in the Kaggle dataset. It would be useful to see if fake news forms a distinct cluster, or if we can find a cluster corresponding to healthcare-specific fake news. Secondly, we believe unsupervised learning may be useful in discovering different sub-types of covid fake news. For this, we would like to use k-means clustering on the embedded representations of posts within the CoAID dataset to see how many distinct clusters form. We'd like to analyze these clusters and identify any distinct semantic attributes each cluster has.

For the supervised learning portion of the project, we aim to develop a classifier that can accurately label a given social media post as true or fake news. For this task, we will train a classifier of input-output pairs composed of the vector representation of each social media post and that post's corresponding truth / falsehood label. We will likely try a variety of models, including SVM, Random Forest, and Logistic Regression. The model chosen will ultimately depend on the which model tested results in the best performance.

One unique aspect of our approach is the data sources we will draw from when evaluating the truth of a social media post. Unlike some approaches, we will look at not only the body text of the post, but also the text of all the comments associated with that post. We believe that the way users engage with fake news is likely quite distinct from the interaction patterns of real news, offering the potential for increased accuracy in label prediction.

One risk associated with this project is the issue posed by false positives. If this system was used to automatically remove posts and a post was erroneously flagged as fake news, then the affected user would likely feel slighted by that automated system. In the worst case, this issue creates unnecessary and arbitrary censorship. As a result, we recommend that this system, once developed, is strictly used with a human-in-the-loop. In other words, we recommend that the model output is used only to flag potentially misleading posts, and that a human moderator must manually verify that the content of the post is false before the post is deleted.

We believe this project is completely achievable within the provided timeframe of 2 months. This includes all steps from data exploration, to model training, to results evaluation. We don't expect there to be any associated costs, as none of the techniques used are particularly costly or computationally expensive to implement.

### Results
By the end of this project, we want to create software in which users can upload a social media post to be scanned. From there, we will utilize machine learning principles to categorize the post as containing or not containing fake news about Coronavirus.

To guarantee we meet expectations, we have organized our checks for success as such:
- Mid-term check: use various clustering algorithms to determine if we are able to differentiate posts
- Final check: run application with existing datasets of posts and evaluate the performance

### Discussion

Ideally, our project will successfully categorize posts as ‘fake news’ or ‘not fake news’. If we are successful, our project could be used to flag fake news posts on social media for review. This would involve some room for error, as fake/real news can use similar phrases. Human review would allow for false positives without immediately taking down real new posts. Finally, our model would help control the spread of fake news and misinformation on social media sites, improving trust by the user. 


### References
How Facebook Is Using AI to Fight COVID-19 Misinformation,
Tekla S. Perry,
https://spectrum.ieee.org/view-from-the-valley/artificial-intelligence/machine-learning/how-facebook-is-using-ai-to-fight-covid19-misinformation


Fake News Detection: A Deep Learning Approach,
Aswini Thota, Priyanka Tilak, Simrat Ahluwalia, Nibrat Lohia,
https://scholar.smu.edu/cgi/viewcontent.cgi?article=1036&context=datasciencereview

CoAID: COVID-19 Healthcare Misinformation Dataset,
Limeng Cui, Dongwon Lee,
https://arxiv.org/pdf/2006.00885.pdf
