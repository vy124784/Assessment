# Assessment
write a program in Python to indicate the degree of profanity for each sentence in a file containing Twitter tweets by various users.

Assumptions:

The tweets are in a text file where each line represents a tweet.
The set of words that indicate racial slurs is provided in a separate file, with one slur per line.
We will use a simple bag-of-words approach to count the number of racial slurs in each tweet.
We will assume that partial matches of a slur within a word will be counted as a match. For example, if "butt" is a racial slur, then the word "butterfly" will also count as a match.

Code:
# Load the set of racial slurs from a file
with open('racial_slurs.txt', 'r') as f:
    racial_slurs = set([line.strip() for line in f])

# Load the tweets from a file
with open('tweets.txt', 'r') as f:
    tweets = [line.strip() for line in f]

# Define a function to count the number of racial slurs in a tweet
def count_racial_slurs(tweet):
    count = 0
    for word in tweet.split():
        if word.lower() in racial_slurs:
            count += 1
    return count

# Process each tweet and print the degree of profanity
for tweet in tweets:
    num_racial_slurs = count_racial_slurs(tweet)
    if num_racial_slurs == 0:
        print("Tweet: ", tweet)
        print("Degree of profanity: None\n")
    elif num_racial_slurs == 1:
        print("Tweet: ", tweet)
        print("Degree of profanity: Low\n")
    elif num_racial_slurs <= 3:
        print("Tweet: ", tweet)
        print("Degree of profanity: Medium\n")
    else:
        print("Tweet: ", tweet)
        print("Degree of profanity: High\n")
In this code, we first load the set of racial slurs from a file and the tweets from another file. Then we define a function count_racial_slurs to count the number of racial slurs in a tweet. Finally, we loop through each tweet and print the degree of profanity based on the number of racial slurs found in the tweet.

We use a simple classification scheme where the degree of profanity is labeled as "None" if there are no racial slurs in the tweet, "Low" if there is one racial slur, "Medium" if there are 2 to 3 racial slurs, and "High" if there are more than 3 racial slurs. We can adjust the thresholds and labels as per our requirements.
