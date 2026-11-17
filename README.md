# Review Insights: understanding what tourists say about accommodations

Building AI course project

## Summary

Review Insights classifies guest reviews of tourist accommodations as positive or negative and detects the topics guests mention most (cleanliness, location, price, noise). It helps small hosts decide what to improve and how to communicate their strengths.

## Background

Small hotels, hostels and holiday apartments receive hundreds of online reviews, but reading them all is slow and it is hard to see patterns. Reputation is one of the main drivers of bookings in tourism, so understanding customer feedback is a core marketing task.

* Owners of small businesses rarely have time or tools to analyse reviews.
* Averages such as "4.2 stars" hide what guests actually like or dislike.
* Marketing messages are often not based on what customers really value.

My motivation is personal. When I was planning a trip with friends, I spent hours reading reviews to find out whether an apartment was really quiet and close to the centre. The star rating told me almost nothing, and the useful information was buried in dozens of comments. I realised that the host probably had the same problem from the other side: all the answers about what to improve were in the reviews, but nobody had time to read them.

As a marketing student, I am interested in how companies listen to their customers and build their reputation. I wanted to explore how AI can help small tourism businesses turn what guests say into practical decisions.

## How is it used?

The user (a host, hotel manager or marketing assistant) uploads or pastes a set of reviews. The tool then shows:

1. The share of positive and negative reviews.
2. The words and topics most associated with negative reviews (for example "noise", "dirty", "wifi").
3. The words and topics most associated with positive reviews (for example "location", "friendly", "breakfast").

The owner can use this to fix recurring problems and to highlight real strengths in the listing description and advertising.

Guests are also affected: better feedback analysis can lead to better accommodation quality.

## Data sources and AI methods

The data would come from publicly available review datasets, for example [Inside Airbnb](http://insideairbnb.com/get-the-data/), which publishes listing and review data for many cities (the license of the data should be checked on the site before use).

AI methods covered in the course:

* **Bag-of-words** to turn each review into word counts.
* **tf-idf** to give more weight to words that are distinctive of a review and less to very common words.
* **Naive Bayes classifier** to classify reviews as positive or negative, using a labelled sample (for example reviews with high or low scores).
* **Training and test sets** to check that the model works on reviews it has not seen, compared with a baseline (always predicting the majority class).

| Step | Description |
| ---- | ----------- |
| 1 | Collect and clean reviews |
| 2 | Convert text to bag-of-words / tf-idf |
| 3 | Train and test the classifier |
| 4 | Show the most relevant words per class |

## Challenges

* Reviews are written in many languages, and the model would need to be trained for each one.
* Sarcasm, irony and mixed opinions ("nice place but dirty bathroom") are hard for a bag-of-words model, since it ignores word order.
* Reviews are not a representative sample of all guests, and some can be fake or biased.
* Accuracy can be misleading if most reviews are positive, so the model must be compared with a simple baseline.
* Reviews can contain personal information, so privacy must be respected.

## What next?

* Support several languages.
* Use more advanced text models that take word order into account.
* Detect topics automatically and track how they change over time.
* Build a simple web dashboard for non-technical users.
* Test it with real small businesses to learn what they actually need.

## Acknowledgments

* Inspired by the Elements of AI courses (University of Helsinki and Reaktor): the sections on naive Bayes, working with text (bag-of-words, tf-idf) and the nearest neighbor method.
* Review data: [Inside Airbnb](http://insideairbnb.com/), used under its stated license.
