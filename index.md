## Exposing Fake COVID-19 News

### Introduction
With the emphasis of social media on our present day society, information is being spread faster than ever. Users can stay up to date with the internet’s latest trends, political activity, and possibly the hottest topic of 2020, Covid-19 related news. However, while great at quickly sharing news, social media also allows for anybody to post information as the truth, regardless if the facts are accurate. The goal of our machine learning project is to create a model to detect Covid-19 related “fake news”, or untrue information, presented as real news found in social media. Our model will be able to tell whether an article is related to Covid-19 and from there, decide whether the article presents factual information.

Users must remain vigilant and rely on their intuition or fact-check the articles they read to guarantee its validity. However, with the constant stream of information and posts, this rarely happens. Data scientists have created “fake news” classifiers in the past, but nothing on the same scale has been done with Covid-19 news. Creating an unbiased classifier tailored to check articles under this topic will be extremely helpful to determine the true developments regarding Covid-19.


### Methods
Expected
- Kaggle Fake News dataset
- SVM-based text classifier
- Word2Vec to vectorize posts
- K-means for topic modeling

Unique Aspects
- We’ll try to classify not only the body of the post, but also the comments

Risks
- We risk having too many false positives, resulting in arbitrary censorship of good posts

Costs
- No expected costs, all involved algos aren’t too computationally intensive

Timeframe
- Likely 1-2 months for data exploration, training, and results validation

### Results
By the end of this project, we want to create software in which users can upload a social media post to be scanned. From there, we will utilize machine learning principles to categorize the post as containing or not containing fake news about Coronavirus.

To guarantee we meet expectations, we have organized our checks for success as such:
- Mid-term check: use various clustering algorithms to determine if we are able to differentiate posts
- Final check: run application with existing datasets of posts and evaluate the performance

### Discussion

Ideally, our project will successfully categorize posts as ‘fake news’ or ‘not fake news’. If we are successful, our project could be used to flag fake news posts on social media for review. This would involve some room for error, as fake/real news can use similar phrases. Human review would allow for false positives without immediately taking down real new posts. Finally, our model would help control the spread of fake news and misinformation on social media sites, improving trust by the user. 


### References
How Facebook Is Using AI to Fight COVID-19 Misinformation
Tekla S. Perry
https://spectrum.ieee.org/view-from-the-valley/artificial-intelligence/machine-learning/how-facebook-is-using-ai-to-fight-covid19-misinformation

Fake News Detection: A Deep Learning Approach
Aswini Thota, Priyanka Tilak, Simrat Ahluwalia, Nibrat Lohia
https://scholar.smu.edu/cgi/viewcontent.cgi?article=1036&context=datasciencereview

CoAID: COVID-19 Healthcare Misinformation Dataset
Limeng Cui, Dongwon Lee
https://arxiv.org/pdf/2006.00885.pdf
