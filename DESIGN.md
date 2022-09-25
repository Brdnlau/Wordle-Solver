# Design Document


## Purpose
*The purpose of this program is to implement a solver for the popular word guessing game, Wordle, that works in two different ways. A secret word can be specified and the program will try to guess it or it can iteratively suggest guesses to a user for a live game.*


## Structure
*The structure of this program will be as follows:*


#### 1. `score_letter`
This function loops over the vocabulary list and returns the number of words that contain a particular letter. 

An int is initialized as zero to keep track of the number. Two for loops will then be used to iterate through the vocabulary list and every word in that list, respectively. In the first for loop, an if statement will make sure that the word in the vocabulary array is
not null before continuing. The inner loop checks if the current letter in the word is the letter we are looking for, and if it is, add one to the counter and then break out of the inner loop. The counter int is then returned.


#### 2. `score_word`
This function calculates the score for an inputed word, using values for each letter from an inputed array. It then returns the calculated score.

An init is initialized as zero to keep track of the score. An empty string is then initialized to keep track of which letters have been scored. A for loop will be used to iterate through the given word, and an if statement checks if the current letter has already been 
scored. If not, the required value is called from the input array using the index calculated from subtracting the letter from 'a'. This value is then added to the score, and the letter is added to the string. The score is then returned.


#### 3. `filter_vocabulary_gray`
This function helps filter the vocabulary list knowing that a certain letter is not in a word. It will loop over the vocabulary list to free words with the letter.

An int is initialized as zero to keep track of how many words have been filtered out. Two for loops will then be used to iterate through the vocabulary list and every word in that list, respectively. In the first for loop, an if statement will make sure that the word in
the vocabulary array is not null before continuing. The inner loop checks if the current letter in the word is the letter we are looking for, and if it is, free that index in that vocabulary array and set its pointer to NULL. It then adds one to the counter and breaks out 
of the inner loop. The total words filtered out is then returned. 

#### 4. `filter_vocabulary_yellow`
This function helps filter the vocabulary list knowing that a certain letter is in a word, but not at a particular position. It will loop over the vocabulary list to free words without the letter or with the letter, but at the particular position.

An int is initialized as zero to keep track of how many words have been filtered out. A for loop will then be used to iterate through the vocabulary list. An if statement will make sure that the word in the vocabulary array is not null before continuing. A second one is
then used to check if the letter at the position specified is the letter specified. If it is, the index in that vocabulary array is freed and the pointer is set to NULL. An else if is then used with strchr to see if the letter is in the word at all, and if it is not,
then the index in the vocabulary array is freed and the pointer is set to NULL. The total words filtered out is then returned.


#### 5. `filter_vocabulary_green`
This function helps filter the vocabulary list knowing that a certain letter is in a word and at a particular position. It will loop over the vocabulary list to free words that does not have that letter at that position.


An int is initialized as zero to keep track of how many words have been filtered out. A for loop will then be used to iterate through the vocabulary list. An if statement will make sure that the word in the vocabulary array is not null before continuing. Another if 
statement is then used to check if the letter of the word at the position specified is the letter specified. If it is not, the index in the vocabulary array is freed and the pointer is set to NULL. The total words filtered out is then returned.
