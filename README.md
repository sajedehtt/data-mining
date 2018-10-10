## Exercises for Section 2.3
### **Exercise 2.3.1** 
#### i:
#### map:     For each tuple t, emit a key/value pair (t, t) 
#### Reduce:    Apply max to the list of all key
Emit the key/value pair (x,x), where x = max ([t] t in key value)

 #### ii:
#### map:     For each tuple t, emit a key/value pair (t, t) 
#### Reduce:    Apply Averag to the list of all key
Emit the key/value pair (x,x), where x =  Averag([t] t in key value)
### **Exercise 2.3.5**: 
#### map:   For a tuple (a,b) in R emit a key/value pair (b, (‘R’,a)) 
  #### For a tuple (c,d) in S, emit a key/value pair(c, (‘R’,d))
#### Reduce: for each (b, (‘R’,a)) and (c, (‘R’,d)) if key b< key c then  emit a key/value pair ((a,b),(c,d)) Otherwise, emit a key/value pair (t, NULL)
