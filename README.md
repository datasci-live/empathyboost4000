# empathyboost4000
Internet empathy? Join us this weekend as we use ML to send immediate, empathic replies to people writing "cries for help" on Reddit.

## EmpathyBoost4000 Challenge:
Reddit is a network of communities based on people's interests. The site has hundreds of different communities (called subreddits) and many of these subreddits have tens of thousands of members. Surprisingly often, someone will post a comment that amounts to a cry for help. Recent posts in the “CS Career Questions” subreddit (~500k members) have had titles including:

- “Anxiety is getting the best of me over this”
- “I feel like I suck at my job”
- “Job search prep is overwhelming”
- “Was too afraid to tell team I was blocked; week went by and lied about progress”
- “Am I screwed?”

Sometimes, as was the case with example #1, the “AutoModerator” jumps in (based on keywords and regex matches) to provide relevant mental health information. Mostly the AutoModerator does not jump in. Unfortunately, too often the top community replies are not particularly empathic. 

For example, with ~1,000 upvotes, the top reply to example #4 was “Don’t do this again. Raise red flags early. Raise questions early. Don’t lie to your team members.” While that may be sage advice, the person that posted the comment (called “OP” for Original Poster) probably already knows that would have been a better course of action. OP was probably hoping for an empathic response rather than advice. (Maybe OP should have tried 7cups.com before Reddit?)

## Challenge Statement:
Your challenge is to build EmpathyBoost4000, a machine learning-based bot for Reddit. The bot will detect “cries for help,” provide an immediate empathic response to OP, and ‘nudge’ the authors of future replies to empathize with OP before sharing any advice. To gather continuous feedback, the bot will ask Reddit viewers to upvote or downvote the bot’s reply based on relevance. This feedback will be incorporated to improve the accuracy over time. Apply the bot to the CS Career Questions subreddit.
Recommended Path

- Interact with the Reddit API so you can read and write posts
-- Basic version: Use this tutorial or similar to get started. Extra: set this so that it runs every 5 minutes (this might occasionally miss a post, and will sometimes not be the first to respond).
-- Advanced version: Fork this repo and customize the bot for this use case.
Gather the text for a bunch of posts that you think are ‘cries for help’ and a bunch that are not. Manually label posts as containing ‘cries for help.’
-- Basic version: do a keyword search on Reddit, build an HTML parser to extract the text from the post page.
-- Intermediate version: Use the Reddit API to capture the last year’s worth of posts. Use keyword search, regex to search for ‘cries for help.’
- Split the posts you labeled as ‘cries for help’ into sentences. Manually label specific sentences as ‘cries for help’ or not. Next, you’ll label many of the other sentences in the posts you’ve captured. To save time, rank order sentences based on sentence embeddings. (Assess the similarity between sentences labeled as ‘cries for help’ and all unlabeled sentences. Sort so that unlabeled sentences that are semantically similar to a ‘cry for help’ sentence are at the top.) Stop when you believe you have labeled almost all the ‘cry for help’ sentences in the dataset.
- Explore the data. Determine how you will classify new sentences as ‘cries for help’ or not. Pay special attention to the % of false positives, since the Reddit community will not take kindly to spam.
- Configure the bot you created in step 1 to read new posts, split posts (title and body) into sentences, and assess if any sentence looks like a ‘cry for help.’ If at least one sentence looks like a ‘cry for help,’ send a bot message.
- Set up a system to review the upvotes / downvotes on your bot messages after 72 hours. Add sentences that were predicted to be ‘cries for help’ to your labeled dataset as either ‘cries for help’ or not based on community upvote / downvote feedback.
- Rejoice! You’ve now built an automod that will improve people’s lives, and improve in accuracy over time with no additional effort from you!

## Future work
If we finish everything within the time limit, and want to keep going, here are some additional ideas:
- Go beyond sentence embeddings and similarity measures to improve NLP.
- Utilize subreddits like r/Anxiety and r/depression to gather more examples of ‘cries for help’
- Send different messages depending on the situation.
- [[Your ideas go here]]
