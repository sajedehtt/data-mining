## Exercises for Section 2.3
### **Exercise 2.3.1** 
#### (a) The largest integer.
#### map:     For each tuple t, emit a key/value pair (1, t) 
#### Reduce:     key 1 represent a group, with values [t1, t2, …, tn]. Apply max to the list of all value, Emit the key/value pair (1,x), where x = max([t1, t2, …, tn])
 #### (b) The average of all the integers.
#### map:     For each tuple t, emit a key/value pair (1, t) 
#### Reduce:    Apply Averag to the list of all value Emit the key/value pair (1,x), where x =  Averag([t] t in  value)
#### (c) The same set of integers, but with each integer appearing only once.
### **Exercise 2.3.5**: 
#### map:   For a tuple (a,b) in R emit a key/value pair (b, (‘R’,a)) 
  #### For a tuple (c,d) in S, emit a key/value pair(c, (‘R’,d))
#### Reduce: for each (b, (‘R’,a)) and (c, (‘R’,d)) if key b< key c then  emit a key/value pair ((a,b),(c,d)) Otherwise, emit a key/value pair (t, NULL)

