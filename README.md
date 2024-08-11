# WingSpan - Canteen Recommendation System

**Collaborative filtering** is a technique that can filter out items that a user might like based on similar users.
It works by searching a large group of people and finding a smaller set of users with tastes similar to a particular user. It looks at the items they like and combines them to create a ranked list of suggestions
# User based collaborative filtering- 
- User-user collaborative filtering is one kind of recommendation method which looks for a similar user based on the items users have already liked or are positively interested in.Suppose customer id 1 gives a high rating to vendor id 23,42,113 and customer id 2 gives a high rating of 23, 50,42 and customer id 3 only gives a high rating of 42 so there is a high chance that customer id 3 also gives a high rate to vendor id 23 because they all are similar users.
- To find user similarity between two users we can use cosine similarity.
- Cosine similarity means the similarity between 2 vectors of inner product space, it is measured by the cosine of the angle between two vectors.
 **Similarity = (A.B) / (||A||. ||B||)**where A and B are vectors.
Suppose I have to recommend a new top 5 similar vendor to user id 2, so I have a similarity matrix and we go in the similarity matrix is user id 2 and find a top 5 similar values corresponding to the user id 2 . where they give a rating value and not visited by the user 2 and combine them then pick all those vendors and recommend to user 2. 
**§ Steps involved in user-based collaborative filtering**
1. Converting customer id that is a string in integers.
2. Get some important columns from the dataset.
3. split the data set into train and test data.
4. These datasets will be used for prediction and evaluation. A Dummy train will be used later for the prediction of the vendors which has not been rated by the user. To ignore the vendor rated by the user, we will mark it as 0 during prediction. The vendors not rated by the user are marked as 1 for prediction.
A Dummy test will be used for evaluation. To evaluate, we will only make predictions on the vendors rated by the user. So, this is marked as 1. This is just the opposite of a dummy train.
5. Find the similarity between two users using a cosine similarity matrix.
6. Predict user rating on the vendor using dot product between similarity matrix and pivot table data.
7. We do not want to recommend the same vendor that the user already visited. We are interested only in the vendor not rated by the user we will ignore the vendor rated by the user. This is where we will use our dummy train matrix that we previously built.
8. Multiply the dot product result with a dummy train to get the final prediction score.
9. Combine all users which are similar to the given input user and sort them to find top vendors based on the similarity matrix score.
 
# Item-based collaborative filtering- 
- It works on Item-item similarity or in our case we can say vendor-vendor similarity based on the rating of the vendor, food quality, delivery time, and many more. For example, say customer 1 orders food from vendor 4 to serve pasta, pizza, and Italian food, and also order from vendor 10 to serve pasta, French fries, and shakes that means there is a high chance next time coatomer id 1 order food along with pasta so recommended vendor to customer id 1 who has pasta in their menu.

![image](https://github.com/user-attachments/assets/986e280e-81ab-44ac-bdd9-e1f8b945a96b)
