# Morse-Convertor-in-Python
Given a string morsecode that contains a list of '.' and '-'. you are allowed to make one move and replace two consecutive '..' with '--'. return all possible morsecodes you can get after a single move you do to the string morsecode.

Constrains: 1<=morseCode<=500 and morsecode[i] is either '-' or '.'

APPROACH 1

1 create an empty list 'listMorse'.

2 iterate through string 'morseCode' starting from first character.

3 check if current character + next character are both '.'.

4 If they are, create new string replacing '..' with '--'.

5 If they are, append new string to list 'listMorse'.

6 return the list 'listMorse'.

Note: if there is no '..' substring, there is no append to the new list.

APPROACH 1 iterates the string for each character starting with the first and ending with the last - 1 . For every character, which is the index of the iteration, checks if the character(index) and the next one(index + 1) are equal to '..'. If they are, creates new string replacing '..' with '--', and appends this new string to the list created. After iteration, returns the list.

TEST CASES:

1 INPUT: morseCode = '....' OUTPUT: listMorse = ['--..','.--.','..--]

Reasoning: At the beginning I got '..' and I expect to append to the list replacing the first two character with '--' having a string '--..', next moving to index 1, I got also two characters '..', and expect to have appended to the list a string '.--.', finally I got another '..' and expect to have appended to the list a string '..--'. Final result is a list with three strings ['--..','.--.','..--].

2 INPUT: morseCode = '-.-..-...' OUTPUT: listMorse = ['-.----...', '-.-..---.', '-.-..-.--']

Reasoning: There are three groups of substring '..', so the new list will have three strings replacing '..' to '--'.

3 cover edge case: INPUT: morseCode = '-.-.' OUTPUT = listMorse = []

Reasoning:   there are no substring '..', so the output will be an empty list
4 big string case: INPUT: morseCode = '-.-.-------------------------------------------------..' OUTPUT: listMorse = ['-.-.---------------------------------------------------']

Reasoning: there is only two dots at the end of the string, so it is expected to have only one
           string on the new list replacing at the end with '--'
5 cover edge case: INPUT: morseCode = '' OUTPUT = listMorse = []

Reasoning:  there are no substring '..', so the output will be an empty list

