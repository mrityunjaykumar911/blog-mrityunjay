---
title: "Handling Large text data in production"
date: 2018-03-21T00:27:54+05:30
draft: false
---

Question:

I have a 5GB a single JSON file which consists of million of queries (questions) with its answers.

Can anyone please tell me,

1) How to handle such kind of large datasets?

2) Objective is to find out the top 5 similar query along with the answers which is similar to the provided a new test query.


Answer:

I can suggest one option which I implemented.

1. Pyspark for data processing
If you want to make this simple, you can use pyspark to load the dataset and perform operations accordingly.
Because of the fact as soon as you datasize will grow, it will eat more memory and a simple collective operation will cost you a lot.
If I am not wrong, you might perform NLP techniques to analyze the structure underneath the question dataset.

2. After processing, you can store your pre-computed results in Graph database which will in-turn help you in faster document matching and retrieval.

Hope it helps.

1. pyspark : https://spark.apache.org/.../python-programming-guide.html
2. Graph database : https://dgraph.io/ or https://neo4j.com/
