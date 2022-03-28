# Content_Recommendation System
### Sony R.I.S.E. Challenge

This repository contains solution for Sony R.I.S.E. Challenge. The solution required creating a Content Recommendation System for suggesting top contents to watch for a particular user.

You can find the analysis, ideation and description of the final recommender system created below.

## Analysis

![Content Analysis](https://user-images.githubusercontent.com/25738903/160467681-aa3d910e-6072-4c13-b906-f8ae8d31e67b.PNG)


![Content_user_relationship](https://user-images.githubusercontent.com/25738903/160467740-49ec447f-0c68-4584-9e1e-9e7f85df7725.PNG)

## Ideation
- For creating a recommendation system, we focused on algorithms such as **Collaborative Filtering and Content Based Filtering**. (Collaborative Filtering works by filtering out items that a user might like based on reactions by similar users.)
- Since we didn't have individual content ratings given by each user to the content they have watched, we did not focus much on User based Collaborative Filtering
- We focused on recommending content to the users based on their watch history. For this we needed to find a way to decide which content are similar and combine their choices to create a list of recommendations.

## Solution
- To compare content, we reduced the content feature data to **embeddings**, by training a **supervised Autoencoder and a Predictor DNN**.
- The embeddings map the feature data into a space with lower dimensions and generally capture some latent structure of feature dataset.
- We extracted the generated embeddings and used them to calculate similarity between any two content.
- We used **cosine similarity and manhattan distance** to compare embeddings. We found cosine similarity to work a little better in our case.
- Once we could find similarity between contents, we just used a user's previous watch history to recommend Top 10 content similar to the same.

You can refer to the jupyter notebook for the solution.
