# WordCount
WordCount problem using mapreduce


Hadoop WordCount operation occurs in 3 stages –

Mapper Phase
Shuffle Phase
Reducer Phase
Hadoop WordCount Example- Mapper Phase Execution
The text from the input text file is tokenized into words to form a key value pair with all the words present in the input text file. The key is the word from the input file and value is ‘1’.

For instance if you consider the sentence “An elephant is an animal”. The mapper phase in the WordCount example will split the string into individual tokens i.e. words. In this case, the entire sentence will be split into 5 tokens (one for each word) with a value 1 as shown below –

Key-Value pairs from Hadoop Map Phase Execution-

(an,1)
(elephant,1)
(is,1)
(an,1)
(animal,1)


​Hadoop WordCount Example- Shuffle Phase Execution
After the map phase execution is completed successfully, shuffle phase is executed automatically wherein the key-value pairs generated in the map phase are taken as input and then sorted in alphabetical order. After the shuffle phase is executed from the WordCount example code, the output will look like this -

(an,1)  
(an,1) 
(animal,1)
(elephant,1)  
(is,1) 





​Hadoop WordCount Example- Reducer Phase Execution
In the reduce phase, all the keys are grouped together and the values for similar keys are added up to find the occurrences for a particular word. It is like an aggregation phase for the keys generated by the map phase. The reducer phase takes the output of shuffle phase as input and then reduces the key-value pairs to unique keys with values added up. In our example “An elephant is an animal.” is the only word that appears twice in the sentence. After the execution of the reduce phase of MapReduce WordCount example program, appears as a key only once but with a count of 2 as shown below -

(an,2)  
(animal,1)
(elephant,1)  
(is,1) 

​This is how the MapReduce word count program executes and outputs the number of occurrences of a word in any given input file. An important point to note during the execution of the WordCount example is that the mapper class in the WordCount program will execute completely on the entire input file and not just a single sentence. Suppose if the input file has 15 lines then the mapper class will split the words of all the 15 lines and form initial key value pairs for the entire dataset. The reducer execution will begin only after the mapper phase is executed successfully.

### use the below command for running jar files 
hadoop jar filename.jar classname 

### big.txt is the file used for input 



