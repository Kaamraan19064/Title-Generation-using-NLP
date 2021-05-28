# Title-Generation-using-NLP

## Problem Statement
Headline generation while preparing to write about any topic is very important as headings gain readers attention and based on that most of the users decide whether they want to read a particular article. If the writer fails to give a relevant headline to a good ar-
ticle the user may not even consider reading it. The
aim of the project is to develop a generalized archi-
tecture which generates heading for the given text,
which can be an article, a book’s paragraph, news
paper contents or any legal document. A model is
proposed which makes use of encoder – decoder
recurrent neural network architecture consisting of
LSTM.

## Dataset Used

We have tried to use data set from diverse domains
to make a generic architecture. We have used data
 set available on BBC news website which consists
 of 2225 documents from the BBC news website
 corresponding to stories in five topical areas. It also
 consists of 737 documents from the BBC Sport
 website corresponding to sports news articles in
 five topical areas.
 We have also scraped data from medium which
 consists of summary of the articles present on the
medium website together with its title. This dataset
 consists of 1700 rows where each row consists of
 the article summary and title.
 Department of justice press releases dataset is
 used which is scraped from data.gov site of USA
 using beautiful soup. It consists of 13,087 press
 releases but does not includes data which have been
 labelled as speeches.
 All news data set contains articles from publica-
 tions such as CNN, FOX News, New York Times,
 RSS etc. The data was scraped using beautiful soup
 from archive.org and was stored in SQLite, which
 was stored in csv of size 50,000.
 We have done pre-processing on the content as
 well as the headings. These include: converting
 everything to lowercase, removing HTML tags,
 contraction mapping, removing “”, removing any
 text inside the parenthesis, eliminating punctuation
 and special characters, removing stop words and short words.  In total our dataset when combined contains 1 lakh plus data points or rows where each row consists of the text or the content using which headings will be predicted and the actual heading of the given text or content.
 
 
 ## Architecture
 
 After applying the necessary preprocessing as described above we need to change the words into a form that can be passed to our model. We can do 2 things either assign a number corresponding to each word (make a word2idx dictionary) or use a vector representation i.e. Google word2vec to create a word embedding of a large corpus of data by producing a vector space of several hundred dimensions, in our case we have kept the dimensions to 300. Each unique word in the corpus is assigned a vector. It is a more meaningful representation as words that have similar or close context are assigned vector spaces that are close to each other in 198 space.
 The vector or the word embeddings so formed
 are passed into the encoder network i.e. has LSTM
 layers in it and provide an output feature vector that
 holds the necessary information to map the input to
 output. We are passing the hidden layer and output
 layer to the decoder which is similar architecture
 i.e. LSTM and gives the output that is closest to
 the actual input i.e. headlines in our case. As we
 have a lot of articles simultaneously being passed
 to the network we add LSTM for identifying the
 useful information and prevents the generation of
 ambiguous headlines. LSTM keeps the mapped
 representation of every article, therefore, enabling
 a hierarchical structure for the decoder.
 The decoder uses the obtained representations
 from all the models i.e. it is able to access the
 hidden layers of the article. The next step is to
 convert the vector to words, so the decoder takes
the words of the document summary and forms a
context vector.

## Result
We can see the result in docs folder.

https://github.com/Kaamraan19064/Title-Generation-using-NLP/tree/master/Docs


 
