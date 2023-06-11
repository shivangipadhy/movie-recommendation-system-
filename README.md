# movie-recommendation-system-
Building a movie recommendation system on py, using concepts of Ml and data science, 

These days, we are constantly being recommended products, and the recommendation system is responsible for anything that appears in our feeds. 

the Netflix or Instagram systems. 
The most effective recommendation system may contribute to greater customer satisfaction. 
In general, there are two types of types. 
You essentially try to recreate the entire forecast using 1. the collaborative filtering 2. the content-based filtering, which is essentially a user matrix cross-product with item matrix. 

and once you've worked it out, you can utilise predictions to entice customers to use your app or buy your goods.

So what is collaborative filtering?? – is a technique to filter out content that user might like on the basis of reactions of similar users.

And content-based filtering- uses item features to recommend other items similar to what the user likes, based on their previous actions. 

There are two data sets on which we r working on the one is move data frame and ratings data frame of course you can use any other dataset like the IMBD. we are working close to 10 thousand ratings.

You can get an access to your data set by    rating_df.head()    to get access to our rating and, id dataset . 

The following code brings out the number of unique users   and  number of unique movies  :
Then we multiply these two and get the amount of sparsity
n_users len(ratings_df.userId.unique())
n items len(ratings_df.movield.unique())
print("Number of unique users:", n users)
print("number of unique movies:", items)
print("the full rating matrix will haver", users_items, "elements.") 



I'll be using the Pi Torch or, more generally, the Matrix Factorization Model Initialization & Training / Tuning Model Torch.

Get my numbers in there, and this will be the fundamental structure of a matrix factorization where I am initialising the embeddings over here. You can think of this as a lookup table or a matrix that resembles a vec.

 We're going to try to find a more precise weight for each of these traits, so i'm setting all the weights uniformly to near to 0.05. These are tunable parameters that we have over here, so think of them as our light since variables there.
Note that this is not really good practise because I am essentially just reading in the ratings data frame from the previous cell when in reality the parameter here should be the ratings. We're just plugging in some data and we have a predict function over here that I don't think we'll be using, but I think it's implicitly used within the overall PyTorch algorithm. Over here, this is just some cleaning up the data sets we have here.
amount of epochs Set that to 120, please.
As you can see, we have a GPU that is active, and we initialise the model with specific users, specific things, and specific weights to operate with. 
Our dataset can be read.

for it in tode(range(num_epochs))
losse []
for x, y in train loader:
if cuda
yx.cuda(), y.cuda)
optimizer.zero grad()
outputs model(x)
loss loss fn(outputs.squeeze(), y.type(torch.float32))
losses.append(loss.Item())
loss.backward()
optimizer.step()
print("iter ().format(it), "Loss:", sum(losses) len(losses))
/usr/local/lib/python3.7/dist-packages/ipykernel_launcher.py:1: TodeDeprecationarning

Here we are training the data model, where the y are ratings and x user id, id, and this is what we are running our data asset on. 

In the end you see the weights of their data set have been changed, 

Final step we r utilising our model item weight factors convert it to NumPy array. 
Then we use the concept of clustering and cluttered to 10, 

So if a person likes a movie there is a probability that the person may like the other movie too. 
