## Exercises for Section 2.3
### **Exercise 2.3.1** . Design map-reduce algorithms to take a very large file of integers and produce as output:
#### (a) The largest integer.
 **map**:     For each tuple t, emit a key/value pair (1, t).
 **Reduce**:     key 1 represent a group, with values [t1, t2, …, tn]. Apply max to the list of all value. Emit the key/value pair (1,x), where x = max([t1, t2, …, tn])
 #### (b) The average of all the integers.
 **map**:     For each tuple t, emit a key/value pair (1, t). 
 **Reduce**:    Apply Averag to the list of all value. Emit the key/value pair (1,x), where x =  Averag([t] t in  value)
#### (c) The same set of integers, but with each integer appearing only once.
 **map**:     For each tuple t, emit a key/value pair (t, t).  **Reduce**: for each t that represent a group values 1 or mor than 1 member, Emit the key/value pair (t,t).
 #### (d) The count of the number of distinct integers in the input.
 at first we apply map and reduce in (b) to have The same set of integers, but with each integer appearing only once. then **map**:For each tuple t, emit a key/value pair (a, 1) so we have key/value (a,{1,1,...,1}). **Reduce**: emit a key/value pair(a,x)
 where x= sum[1,1,1...,1].
### Exercise 2.3.2. :Our formulation of matrix-vector multiplication assumed that the matrix M was square. Generalize the algorithm to the case where M is an r-by-c matrix for some number of rows r and columns c.:
the mapreduce is as same as the case that matrix is square. indeed, when we divide the matrix into vertical stripes or divide it into squre matrix is not important the last vertical diden"t have the same size or some spilite isn't a squre.

 **Exercise 2.3.2**. In the form of relational algebra implemented in SQL, relations are not sets, but bags; that is, tuples are allowed to appear more than once. There are extended deﬁnitions of union, intersection, and difference for bags, which we shall deﬁne below. Write map-reduce algorithms for computing the following operations on bags R and S:
### (a) Bag Union, deﬁned to be the bag of tuples in which tuple t appears the sum of the numbers of times it appears in R and S.
**Map**:For each tuple t in R or S, emit a key/value pair (t, 1). **Reduce**: For each key value (t,[1,1,..,1]),emit a key/value pair (t,(t,t,...t))where number of t is equal number of 1.
### (b) Bag Intersection, deﬁned to be the bag of tuples in which tuple t appears the minimum of the numbers of times it appears in R and S.
**Map**:For each tuple t in R , emit a key/value pair (t, 1),For each tuple t in  S, emit a key/value pair (t, 2)
**reduce**: For each key value (t,[1,1,..,1,2,2,...2]),emit a key/value pair (t,(t,t,...t)) where number of t is equal number of min{sum1, (sum2)/2}.
### (c) Bag Difference, deﬁned to be the bag of tuples in which the number of times a tuple t appears is equal to the number of times it appears in R minus the number of times it appears in S. A tuple that appears more times in S than in R does not appear in the difference.
### **Exercise 2.3.5**.The relational-algebra operation R(A,B) *_ [B<C] S(C,D) produces all tuples (a,b,c,d) such that tuple (a,b) is in relation R, tuple (c,d) is in S, and b < c. Give a map-reduce implementation of this operation, assuming R and S are sets.
 **map**:   For a tuple (a,b) in R emit a key/value pair (b, (‘R’,a)) 
   For a tuple (c,d) in S, emit a key/value pair(c, (‘R’,d)).
 **Reduce**: for each (b, (‘R’,a)) and (c, (‘R’,d)) if key b< key c then  emit a key/value pair ((a,b),(c,d)) Otherwise, emit a key/value pair (t, NULL)

