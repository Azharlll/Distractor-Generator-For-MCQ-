# Distractor-Generator-For-MCQ-
Md Azhar
MCQ Distractor Generator Model ( By Md Azharuddin Ansari)

Library used:
    1. Numpy
    2. Pandas
    3. Gensim ( NLP Library)
    4. NLTK (NLP Library)

Steps :

   1.Removing Punctuations
   2.Substituing special characters and words
   3.Tokenization

I have used a very simple, precise technique to generate distractors.
We know the distractors have some semantic semalirity withe the actual answer to distract the students.
So, keeping this in mind , we need to generator the sentence which seems to be partially semantic similar with
actual answer.

I used Doc2vec model from Gensim . ( Doc2vec is an NLP tool for representing documents (sentence) as a vector and is a generalizing of the word2vec method.)
It is used to represent the sentences with vector having the similar semantic sentences similar vector.
So, Doc2vec emphasise on semantic meaning of documents.

Model training:

I started training the Doc2vec model using the train.csv dataset.
I passed the whole training datset to the Doc2vec model, which represents the data into vector form with similar data having similar vector.
Now, we can generatedistractor by passing the input as ( actual answer) and our trained Doc2vec model will give the most similar 3 sentences (topn =3)
i.e 3 distractor.

Generating Distractor:
 
To pass the input ( actual answer) , we need to first vectorise it using same vectorizer object while used in training.
Then, our model will return 3 vectors as ouput, which will be the vectors of our distractor.
So, I converted back the distractor vector back to text form. And thus finally, we get the ouput in our desired form.

The accuracy of Model seems to be very high. It's a very sweet, simple and precise way to generate distractor.


Cosine Similarity between each distractor and actual answer:

I have used cosine similarity to get the similarity score between the actual answer and predicted distractors.
which return a list of three % score for each distractor as we have three distractors for each answer.
 

Note: 

The final result is updated in Results.csv file.
Also the test.csv is updated with distractors and cosine scores columns.


 

 
