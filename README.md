# Data-Extraction-NLP
Step 1: Install Required Libraries
        Ensure that you have the necessary libraries installed.

Step 2: Prepare the Project Structure
Create a project folder and place the following files in it:

Input.xlsx: Contains the URLs and their corresponding ID.
Output Data Structure.xlsx: Defines the output structure.
Positive Dictionary.txt: A text file containing a list of positive words.
Negative Dictionary.txt: A text file containing a list of negative words.
Text Analysis.docx: Contains the definitions of the variables.

Definition of each of the variables given below
1.POSITIVE SCORE:
This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.

2.NEGATIVE SCORE
This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and 
then adding up all the values. We multiply the score with -1 so that the score is a positive number.

3.POLARITY SCORE
This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 
Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001)
Range is from -1 to +1

4.SUBJECTIVITY SCORE
This is the score that determines if a given text is objective or subjective. It is calculated by using the formula: 
Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001)
Range is from 0 to +1

5.AVG SENTENCE LENGTH
the number of words / the number of sentences

6.PERCENTAGE OF COMPLEX WORDS
the number of complex words / the number of words 

7.FOG INDEX
0.4 * (Average Sentence Length + Percentage of Complex words)

8.AVG NUMBER OF WORDS PER SENTENCE
the total number of words / the total number of sentences

9.COMPLEX WORD COUNT
Complex words are words in the text that contain more than two syllables.

10.WORD COUNT
We count the total cleaned words present in the text by 
I.removing the stop words (using stopwords class of nltk package).
II.removing any punctuations like ? ! , . from the word before counting.

11.SYLLABLE PER WORD
We count the number of Syllables in each word of the text by counting the vowels present in each word. 
We also handle some exceptions like words ending with "es","ed" by not counting them as a syllable.

12.PERSONAL PRONOUNS
To calculate Personal Pronouns mentioned in the text, we use regex to find the counts of 
the words - “I,” “we,” “my,” “ours,” and “us”. Special care is taken so that the country name US is not included in the list.

13.AVG WORD LENGTH
Average Word Length is calculated by the formula:
Sum of the total number of characters in each word/Total number of words

Stopwords:The stopwords folder contains txt files such as
          StopWords_Auditor.txt
    	  StopWords_Currencies.txt
    	  StopWords_DatesandNumbers.txt
    	  StopWords_Generic.txt
     	  StopWords_GenericLong.txt
    	  StopWords_Geographic.txt
    	  StopWords_Names.txt

Step 3: Extracting Article Texts from URLs
        Read the URLs from the Input.xlsx file, extracts the article title and text using 
        BeautifulSoup, and saves the extracted text in separate text files with the URL_ID as their names.

Step 4: Perform Textual Analysis and Compute Variables
        Takeon the textual analysis on each extracted article. It calculates the required variables 
        using NLTK, regular expressions, and custom functions. The calculated variables are then stored in a 
        new DataFrame and saved to the Output Data Structure.xlsx file.
