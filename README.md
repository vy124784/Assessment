# Assessment
write a program in Python to indicate the degree of profanity for each sentence in a file containing Twitter tweets by various users.

Assumptions:

1. The tweets are in a text file where each line represents a tweet.
2. The set of words that indicate racial slurs is provided in a separate file, with one slur per line.
3. We will use a simple bag-of-words approach to count the number of racial slurs in each tweet.
4. We will assume that partial matches of a slur within a word will be counted as a match. For example, if "butt" is a racial slur, then the word "butterfly" will also count as a match.

In this code, we first load the set of racial slurs from a file and the tweets from another file. Then we define a function count_racial_slurs to count the number of racial slurs in a tweet. Finally, we loop through each tweet and print the degree of profanity based on the number of racial slurs found in the tweet.

We use a simple classification scheme where the degree of profanity is labeled as "None" if there are no racial slurs in the tweet, "Low" if there is one racial slur, "Medium" if there are 2 to 3 racial slurs, and "High" if there are more than 3 racial slurs. We can adjust the thresholds and labels as per our requirements.
