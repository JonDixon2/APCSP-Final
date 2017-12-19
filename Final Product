from bs4 import BeautifulSoup
from bs4.element import Comment
import urllib2
import re

#WHILE RUNNING THIS CODE, ALLOW FOR 60+ SECONDS TO PASS FOR THE FINAL RESULT TO LOAD DUE TO THE CODE COMPARING THE WORDS TO A LIST OF 273k +
#THE LINK TO THE TEST SENTENCE I USED IS https://docs.google.com/document/d/117n_jjHYqdLvJY5GF5jBiTRGn3sjX-DY8o0dqfzoaq8/edit?usp=sharing

def create_list_of_submitted_words(string):

    word_list = re.sub("[^\w]", " ", string.lower()).split()
    return word_list

def full_list_of_english_words():
    url = "https://raw.githubusercontent.com/dwyl/english-words/master/words.txt"

    content = urllib2.urlopen(url).read()

    soup = BeautifulSoup(content, "html.parser")

    english_words = soup.get_text()

    english_word_list = english_words.lower().split()

    return english_word_list

def check_for_spelling():

    string = raw_input("> ").lower()
    new_phrase = " "
    incorrectly_spelled_words = " "
    user_input = create_list_of_submitted_words(string)
    english_words = full_list_of_english_words()

    for i in range(0, len(user_input)):
        if user_input[i] in english_words:
                new_phrase = new_phrase + " " + user_input[i]
        else:
            incorrectly_spelled_words = incorrectly_spelled_words + " " + user_input[i]

    return string + " " + ":" + " " + "was your original input." + "  " + "The word(s)" +  " " + ":" + " " + incorrectly_spelled_words + " " + ":" + " " + "doesn't / do not appear to be spelled correctly."

print check_for_spelling()
