---
toc: true
comments: false
layout: post
title: Python Quiz 
type: hacks
courses: { compsci: {week: 1} }
---

```python
import getpass, sys

def question_with_response(prompt):
    print("Question: " + prompt)
    msg = input()
    return msg
def question_and_answer(prompt):
    print(prompt)
    msg1 = input()
    return msg1

questions = 3
correct = 0

print('Hello, ' + getpass.getuser() + " running " + sys.executable)
print("You will be asked " + str(questions) + " questions.")
question_and_answer = input("Are you ready to take a test?")

rsp = question_with_response("In Python, the ______ function is used to display output to the console or terminal. ")
if rsp == "print":
    print(rsp + " is correct!")
    correct += 1
else:
    print(rsp + " is incorrect!")

rsp = question_with_response("In Python, the term _____ refers to the process of creating or declaring a variable, function, class, or other named entities in the program.")
if rsp == "def" or "defiend":
    print(rsp + " is correct!")
    correct += 1
else:
    print(rsp + " is incorrect!")

rsp = question_with_response("In Python, _____ is a built-in function that is used to take user input from the console or terminal.")
if rsp == "input":
    print(rsp + " is correct!")
    correct += 1
else:
    print(rsp + " is incorrect!")

print(getpass.getuser() + " you scored " + str(correct) +"/" + str(questions))
```