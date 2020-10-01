## Exposing Fake COVID-19 News

<img src="CS 4641 Proposal Video Presentation.png">

### Introduction
Social media plays an important role in disseminating Covid-19 related information. However, although social media is great at disseminating information, there aren't strong controls on what information gets spread. The goal of our project is to create a model to detect Covid-19 related “fake news”, i.e. information that is factually inaccurate or even dangerous. Our model will be able to tell whether a social media post is Covid-19 related and from there, decide whether the post is factual.

Data scientists have created fake news classifiers in the past, but nothing on the same scale has been done for Covid-19 specific information. Creating an unbiased classifier tailored to check social media posts about this topic will be extremely helpful in preventing the spread of misinformation online


### Methods
Although some specifics are in flux, we already have a plan for the methods we'll use for this project. We're currently evaluating three datasets:

1. [Kaggle Fake News](https://www.kaggle.com/c/fake-news/data)
2. [TweetsCOV19](https://data.gesis.org/tweetscov19/#dataset)
3. [CoAID](https://github.com/cuilimeng/CoAID/tree/master/07-01-2020)

To train the classifier, we need to convert the text of the post into a vector representation. We plan to explore multiple techniques, including TF-IDF, Doc2Vec, and BERT

This project also has an unsupervised learning component. We'd like to perform k-means clustering on the vectorized representations of articles from the Kaggle dataset. We want to see if we can find a cluster corresponding to healthcare-specific fake news.

For the supervised portion, we aim to develop a classifier that can label social media posts as true or false. For this task, we will train a classifier with post vectors and input and truth / falsehood labels as output. We will try multiple models, including SVM, Random Forest, and Logistic Regression. We will choose the model based on which performs the best, in terms of accuracy and F1 score.

Our approach has some unique aspects. Unlike some approaches, we will look at not only the text of the post, but also the text of the comments associated with that post. We believe this can increase accuracy in label prediction.

One risk of the project stems from false positives. If this system is used to automatically remove posts, and it removes a true post, then we risk enabling arbitrary censorship. Resultantly, we recommend that this system be strictly used with human supervision, i.e the output is used to flag posts, after which a human must manually review.

We believe this project is achievable within 2 months. We don't expect there to be any associated costs, since our methods aren't computationally expensive to implement.

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
[https://spectrum.ieee.org/view-from-the-valley/artificial-intelligence/machine-learning/how-facebook-is-using-ai-to-fight-covid19-misinformation](https://spectrum.ieee.org/view-from-the-valley/artificial-intelligence/machine-learning/how-facebook-is-using-ai-to-fight-covid19-misinformation)


Fake News Detection: A Deep Learning Approach,
Aswini Thota, Priyanka Tilak, Simrat Ahluwalia, Nibrat Lohia,
[https://scholar.smu.edu/cgi/viewcontent.cgi?article=1036&context=datasciencereview](https://scholar.smu.edu/cgi/viewcontent.cgi?article=1036&context=datasciencereview)

CoAID: COVID-19 Healthcare Misinformation Dataset,
Limeng Cui, Dongwon Lee,
[https://arxiv.org/pdf/2006.00885.pdf](https://arxiv.org/pdf/2006.00885.pdf)
