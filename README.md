# Sentiment-Analysis--LnT

# What is sentimental analysis and why companies use sentimental analysis, Description of concepts, theories.

Sentiment analysis, also known as opinion mining, is a natural language processing (NLP) technique used to determine the sentiment expressed in a piece of text. It involves analyzing and categorizing the subjective information present in text data to identify whether the expressed sentiment is positive, negative, or neutral.

Companies use sentiment analysis for various reasons, primarily to gain insights into customer opinions, market trends, and brand perception.

Understanding Customer Feedback: Sentiment analysis helps companies analyze customer feedback from various sources such as social media, customer reviews, surveys, and customer support interactions. By understanding the sentiment behind these communications, companies can identify areas for improvement, gauge customer satisfaction, and prioritize issues to address.

Monitoring Brand Reputation: Companies use sentiment analysis to monitor mentions of their brand across different platforms and gauge the overall sentiment associated with their brand. This helps them understand public perception, identify potential PR crises, and take proactive measures to manage their brand's reputation.

Product Improvement: Sentiment analysis enables companies to analyze feedback related to their products or services. By identifying positive and negative sentiment, businesses can gain insights into what aspects of their products or services customers like or dislike. This information is valuable for product development, feature prioritization, and enhancing the overall customer experience.


# Approach involved in the proposed solution, technical aspect of proposed solution.

The approach to the problem statement is straight, we scraped an airline tweets dataset and cleaned the data. We performed a 80%:20% Training-Validation Split. Then we fine-tuned a Roberta-Base model by freezing the weights of all the layers except the classification projection head layers which included 2 hidden layers. First hidden layer projects a 768 dimensional vector to another 768 dimensional vector and the second layer projects a 768 dimensional vector to a 3 dimensional output vector.

# Techstack used:

# Python Version 3.10.0
# numpy==1.26.3
# pandas==2.2.0
# scikit-learn==1.4.0
# tqdm==4.66.1
# torch==2.2.1
# transformers==4.37.2



# Detailed technical specifications

The training settings included:
AdamW Optimizer 
LR = 2e-3
ReduceLROnPlateau As Scheduler
And early stopping in case of no improvement on 7 epochs

We evaluated our model on the validation dataset as well having 3 labels : negative, neutral, positive review. We used Macro F1 and Weighted F1 to evaluate our model on the validation dataset

#For larger files, the drive link can be accessed
# https://drive.google.com/drive/folders/10Ag4k3R2JzbgAghaMypxpFTB4rJ5Jsd-


