# Exercises Manning
## Chapter 6:
### **6.8.)**
The number of documents (*N*) is always finite and the document frequency (*df<sub>t</sub>*) is always a natural number (for any term that exists in the collection), so the result of log(N/df<sub>t</sub>) is always finite.

### **6.9.)**
The idf of a term that occurs in every document is log(1) = 0, so the word is ignored for weighing factors. The same happens with words put in the stopword list.

### **6.10.)**
- tf-idf<sub>car,doc1</sub> = 1.65*27 = 44.55
- tf-idf<sub>car,doc2</sub> = 1.65*4 = 6.6
- tf-idf<sub>car,doc3</sub> = 1.65*24 = 39.6
- tf-idf<sub>auto,doc1</sub> = 2.08*3 = 6.24
- tf-idf<sub>auto,doc2</sub> = 2.08*33 = 68.64
- tf-idf<sub>auto,doc3</sub> = 2.08*0 = 0
- tf-idf<sub>insurance,doc1</sub> = 1.62*0 = 0
- tf-idf<sub>insurance,doc2</sub> = 1.62*33 = 53.46
- tf-idf<sub>insurance,doc3</sub> = 1.62*29 = 46.98
- tf-idf<sub>best,doc1</sub> = 1.5*14 = 21
- tf-idf<sub>best,doc2</sub> = 1.5*0 = 0
- tf-idf<sub>best,doc3</sub> = 1.5*17 = 25.5

### **6.15.)**
Unnormalised:
- doc1 = [44.55, 6.24, 0, 21]
- doc2 = [6.6, 68.64, 53.46, 0]
- doc3 = [39.6, 0, 46.98, 25.5]

Normalised:
- doc1 = [0.897, 0.126, 0, 0.423]
- doc2 = [0.076, 0.787, 0.613, 0]
- doc3 = [0.595, 0, 0.706, 0.383]

### **6.16.)**
They all equal 1, since we are normalising the Euclidean distance, making the length of the vector equal to 1.

### **6.17.)**
**i)** The query vector is q1 = [1, 0, 1, 0].
score<sub>(q1,doc1)</sub> = 0.897 + 0 = 0.897
score<sub>(q1,doc2)</sub> = 0.076 + 0.613 = 0.689
score<sub>(q1,doc3)</sub> = 0.595 + 0.706 = 1.301
The ranking would be doc3 > doc1 > doc2.

**i)** The query vector is q2 = [1.65, 2.08, 1.62, 1.5] / ||q2|| = [0.478, 0.602, 0.469, 0.434].
score<sub>(q2,doc1)</sub> = (0.478*0.897) + (0.6024\*0.126) + (0.434\*0.423) = 0.688
score<sub>(q2,doc2)</sub> = (0.478*0.076) + (0.6024\*0.787) + (0.469\*0.613) = 0.798
score<sub>(q2,doc3)</sub> = (0.478*0.595) + (0.469\*0.706) + (0.434\*0.383) = 0.782
The ranking would be doc2 > doc3 > doc1.


## Chapter 8:
### 8.1.)
Precision = 8 / 18 = 0.444
Recall = 8 / 20 = 0.4

### 8.4.)
At a recall level of 0, the interpolated precision is the highest that it can be for a higher recall level, so it can be between 0 and 1.

### 8.8.)
a) MAP<sub>1</sub> = AP<sub>1</sub> = (1 + 2/3 + 1/3 + 2/5)/4 = 3/5 = 0.6
MAP<sub>2</sub> = AP<sub>2</sub> = (1/2 + 2/5 + 1/2 + 4/7)/4 = 69/140 = 0.493
1 has a higher MAP.

b) It makes sense intuitively, since the relevant results in 1 are in the first places of the list. To get a good MAP, the first positions should have more relevant documents.

c) R-P<sub>1</sub> = 2/4 = 0.5
R-P<sub>2</sub> = 1/4 = 0.25
1 has a higher R-P, as well as MAP.

### 8.9.)
a) 6/20 = 0.3

b) 2*0.3\*(6/8) / (0.3+(6/8)) = 0.45/1.05 = 0.429

c) 100%

d) Max(3/9, 4/11, 5/15, 6/20) = 4/11 = 0.364

e) MAP = AP = (1 + 1 + 1/3 + 4/11 + 1/3 + 3/10)/6 = 0.555

f) MAP = AP = (1 + 1 + 1/3 + 4/11 + 1/3 + 3/10 + 7/21 + 8/22) = 0.503

g) MAP = AP = (1 + 1 + 1/3 + 4/11 + 1/3 + 3/10 + 7/9999 + 8/10000) = 0.416

h) 0.555 - 0.416 = 0.139