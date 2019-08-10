# seniment-analysis
import nltk
nltk.download
from nltk.tokenize import word_tokenize

import logging
from textblob import TextBlob
import math
import json
import string

#yourResult=[]
file=open('C:/Users/amit/Downloads/senti/12356.txt', 'rt')
text=file.read()
file.close()
tokens = word_tokenize(text)
words = [word for word in tokens if word.isalpha()]
tokens = [w.lower() for w in tokens]

from nltk.stem.porter import PorterStemmer
porter = PorterStemmer()
stemmed = [porter.stem(word) for word in tokens]
table=str.maketrans('', '', string.punctuation)
stripped = [w.translate(table) for w in stemmed]
words = [word for word in stripped if word.isalpha()]
res = len(words)
print(str(res))

#from nltk.corpus import stopwords
#stop_words = set(stopwords.words('english'))
#words = [w for w in words if not w in stop_words]
        # data = infile.read()
         #data=data.replace (" \ "," ")
         #data=data.replace (" / "," ")
         #data=data.replace (" : "," ")
         
#        data = data.replace("-", "")
#        data=data.replace("[","")
#        data=data.replace("]","")
#        data=data.replace(" ","")
#        data=data.replace ("\t"," ")
#        data=data.replace ("\n"," ")
#        print(data)
#C:\Users\amit\AppData\Local\Programs\Python\Python37

with open('C:/Users/amit/Downloads/senti/.12356.txt', 'w') as f:
    f.write(json.dumps(words))
with open('C:/Users/amit/Downloads/senti/.12356.txt', 'r') as fp:
         content = fp.read()
         blob = TextBlob(content)
         blob.tags
         blob.noun_phrases 


for sentence in blob.sentences:
    print(sentence.sentiment.polarity)
