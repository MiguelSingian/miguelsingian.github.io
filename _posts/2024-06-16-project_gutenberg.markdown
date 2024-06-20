---
layout: single
title:  "Completing Project Gutenberg's Unfinished Bookshelves"
date: 2024-06-16 22:39:00 +0800
categories: "works"
tags: "pyspark aws big_data sparkml nlp"
header:
    overlay_image: "assets/images/gutenberg-printing-press.webp"
---

[Project Gutenberg](https://gutenberg.org/) is the oldest and largest digital repository of public domain literature on the internet. Browsing the website is rather difficult, as there is only a search bar and a list of volunteer-generated "bookshelf" collections, from `Science Fiction` to `Psychology`. These bookshelves would be great for searching if they were not mostly incomplete--only 20% of books are in any bookshelf at all.

Thus, we used the following methodology to "complete" the bookshelves, using semi-supervised machine learning:

1. Ecode all whole texts by term frequency,
2. Create a logistic regression model for each bookshelf, training it on *positive samples* only (i.e. books that belong in that bookshelf), and *synthetic negative samples* so that the model learns the shape of the inlier class without excluding other real books that may belong.
3. Evaluation on accuracy to existing books in the bookshelf unseen by the model (80-20 train-test split), and testing on other books not included in the bookshelves. 

Here are some of our results:

**US Civil War**
![Civil War Result](/assets/images/gutenresults/Screenshot 2024-06-20 at 4.53.00 PM.png)

**United Kingdom**
![United Kingdom Result](/assets/images/gutenresults/Screenshot 2024-06-20 at 4.53.16 PM.png)

**Psychology**
![Psychology Result](/assets/images/gutenresults/Screenshot 2024-06-20 at 4.56.48 PM.png)

The models produced great results, finding books that were very relevant to the incomplete bookshelves.

This project was made possible with the power of Cloud Computing to process these large text files, using a 15 node EMR cluster on AWS.

The full notebook and report can be accessed [here](https://github.com/MiguelSingian/school-projects/blob/main/project_gutenberg.ipynb).