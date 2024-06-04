Features:
- Total Words
- Total Punctuations
- Specific Punctuation Counts
- Total Capital Letters
- Most Common Words

Requirements:
- string module
- collections module

Example:
Same text. It contains punctuations such as commas, periods, and even exclamation marks! I have also included CAPITAL LETTERS.
Running the script with this as the input file would output:

Total words: 59
Total punctuations: 14
Specific punctuation counts: {'.': 3, ',': 1, '-': 0, "'": 0, '*': 0, ':': 1}
Total capital letters: 6
Most common word: is

def analyze_text(file_path):
  with open(file_path , 'r') as file:
    text = file.read()
    word = text.split()
    count = Counter(word)
    punctuation = set(string.punctuation)
    total_words = len(word)

This opens the file, reads it, splits up all the text into it's own section to count the number of words, punctuations, etc. I did this because I used len to count the number of words, or puncutations in the string.

    total_punctuations = sum(1 for char in text if char in string.punctuation)
    specific_punctuations = ['.', ',', '-' , "'", '*', ':']
    specific_count = {p: text.count(p) for p in specific_punctuations}
    capitals = sum(1 for char in text if char.isupper())
    common = count.most_common(1)[0][0]

This block of code calculates the total number of punctuations, counts how many there are of each specific punctuation, counts all the capital letters, and finds the most common words in the string.

  capitals = sum(1 for char in text if char.isupper())
means each character is counted as 1 if the char.isupper is true.


  common = count.most_common(1)[0][0]
this is the code used to find out the word that is said the most amount of times.

common = count.most_common(1):
this part is what actually finds the most common word in the string

[0][0]:
this part just makes it so that it only states the most common word, and doesn't add the amount of times it's said. in the zen of python file, if i were to remove these two zero's it would still say the same common word, but add the number of times that word was said.

**example of this  **

with:
most common word: is

without:
most common word: is, 10








Sources: 
https://www.geeksforgeeks.org/string-punctuation-in-python/
https://stackoverflow.com/questions/49941646/python-counter-function-to-count-words-in-documents-with-more-then-one-occurre
https://www.w3schools.com/python/python_strings.asp#:~:text=However%2C%20Python%20does%20not%20have,access%20elements%20of%20the%20string.
https://www.dataquest.io/blog/read-file-python/
https://stackoverflow.com/questions/3594514/how-to-find-most-common-elements-of-a-list

