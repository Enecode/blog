---
title: "How to Use List Comprehension in Python"
date: 2022-09-05T12:34:16+01:00
draft: false
cover:
    image: img/And_How_To_Use_List_Comprehension_in_Python.png
    alt: 'And How To Use List Comprehension in Python'
    caption: 'List comprhension'
    Size: {1.91:1}

    
---

You spend a lot of time coding, which can be exhausting. Python cares about your mental health, which is why it has tools like list comprehension to help you with your work.

List comprehension allows you to create a list with a single line of code. List are collections of data separated by commas and covered by square brackets. A list comprehension is surrounded by square brackets as well, but instead of data, expressions are entered, followed by for-loops and if clauses.

```python
List: [1, 2, 3, 4, "a", "b", True, False, 10.90]
```

```python
List Comprehensions: [expression for value in collection]

```

List comprehension allows us to manipulate items on a list. If you want to change a single list item, simply change the index and the value. 

When you want to access a specific item in a list, list comprehension can also help you extract information. it can also be used to filter items in a list.

## For-loops In A List comprehension
The `expression ` below generates the elements in a list, followed by a `for-loop` over collections data this will evaluate the `expression ` for every element in the collection.
```python
[expression for value in comprehension]
```

If you only want to include the `expression ` for certain pieces of data, you can add an if clause after the `for-loop`. The expression will be added to the list only if the if clause is `True`
```python
[expression for value in collection if <test>]
```

You can have more than one if clause as you can see from below and the expression is in the list only if the if clauses are `True`. 
```python
[expression for value in collection if <test1> and <test2>]
```

You can also loop over more than one collection in a list
```python
[expression for value1 in collection1 and value2 in collection2]
```

## List A Square Of Numbers
Let’s create an empty list called find square number and loop over 10 positive integers. And append the square of i to the list.

```python
squares = []
for i in range(1, 11):
    squares.append(i ** 2)
print(squares)
this will print 
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
You can use list comprehension to do the same in a single line of code and will arrive at the same result.

```python
squares = [i ** 2 for i in range(1, 10)]
print(squares)
this will print 
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
## Manipulating List Item With A List Comprehension
List comprehension is always based on the following logic: Assume you already have a list with many products. We'll refer to it as 

```python
products_list = [1, 2, 3, 4, 5]. 
```

You can access this list and do something with it by adding, multiplying, or looking up specific product numbers. After that, save the changes as a new list.
Let's multiply the product list by two. You need access to each list item to multiply them by 2. To accomplish this, You will use a for-loop to loop through the product list. You'll do something similar down below.

```python
create an empty list to store the new changes.
new_product_list = []
products_list = [1, 2, 3, 4, 5]
for an item in products_list:  # we will use the .append method to add each item multiplied by 2 in the new list.
    new_product_list.append(item * 2)
print(new_product_list)
the print out will be
[2, 4, 6, 8, 10]
```
When you want to create a new list from any iterable, it is a good practice to make use of list comprehension because it aids readability and that's the best practice. Let’s see how you replicate the above using list comprehension.

```python
products_list = [1, 2, 3, 4, 5]
new_product_list = [item * 2 for item in products_list]
print(new_product_list)
the print out will be
[2, 4, 6, 8, 10]
```
List comprehension reads from the left-hand side by multiplying items by 2 then the for-loop loop through the product list. 
We have printed the desired result without using the append methods and everything in a single line.

## Repeating Items In A List Comprehension 
Let’s say you want to repeat the product list by 2. You will do something like this below.
```python
products_list = [1, 2, 3, 4, 5, ]
product_list = products_list * 2
print(product_list)
This will print [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
```
As you can see the asterisk `(*)` is not for multiplication in this case. It is for repetition.

_**NOTE:**_In python `(**)` represents exponential and if you add two lists, it concatenates them_.

## How To Access A Specific Item In A List
You can also use list comprehension to access a specific item in a list. 

To demonstrate this, let’s create a list containing the student registration number, student name, subject, and score.

```python
students = [{'reg_number': 101, 'name': 'Kenny', 'subject': 'python programming Language', 'score': 78},
            {'reg_number': 212, 'name': 'Blessing', 'subject': 'java programming Language', 'score': 65},
            {'reg_number': 322, 'name': 'Ibrahim', 'subject': 'typeScript programming Language', 'score': 87},
            {'reg_number': 434, 'name': 'John', 'subject': 'javaScript programming Language', 'score': 90},
            {'reg_number': 545, 'name': 'Enema', 'subject': 'data analyst', 'score': 35}
            ]
print(students)
[{'reg_number': 101, 'name': 'Kenny', 'subject': 'python programming Language', 'score': 78}, {'reg_number': 212, 'name': 'Blessing', 'subject': 'java programming Language', 'score': 65}, {'reg_number': 322, 'name': 'Ibrahim', 'subject': 'typeScript programming Language', 'score': 87}, {'reg_number': 434, 'name': 'John', 'subject': 'javaScript programming Language', 'score': 90}, {'reg_number': 545, 'name': 'Enema', 'subject': 'data analyst', 'score': 35}]
```
You have been able to create a student dictionary list with the reg number, name, subject, and score as the keys followed by the corresponding value. You can read more on the dictionary list [here](https://dev.to/arvindmehairjan/what-are-the-differences-between-a-list-tuple-dictionary-set-in-python-2lm6).

## You Can Access All Student Names From The List

```python
student_name = [student['name'] for student in students]
print(student_name)
# ['Kenny', 'Blessing', 'Ibrahim', 'John', 'Enema']
this will print 
['Kenny', 'Blessing', 'Ibrahim', 'John', 'Enema']
```

What you did is loop through students to enable us to access the name key. You are not limited to the name alone, you can also use the same method to access the subject or score.

## How To Filter List Items 
You filter list items to find information about specific items or if they meet a specific condition. Maybe you are looking for the lowest student in a class or the highest student in a class.
What you need to do here is to add conditions that check for students who scored lower marks in a class. 

```python
student_name = [student['name'] for student in students if student['score'] <= 35]
print(student_name)
 this will print Enema
```
This will print Enema because that is the student with the lowest score.

Suppose you want to find a student whose name starts with the letter **“B”** among your students, you will do something like this below:

```python
names_letters = [name for name in students if name['name'].startswith('B')]
print(names_letters)
[{'reg_number': 212, 'name': 'Blessing', 'subject': 'java programming Language', 'score': 65}]
```
```python
this will print everything regarding the student whose name starts with the letter B.
[{'reg_number': 212, 'name': 'Blessing', 'subject': 'java programming Language', 'score': 65}]
```
You can also check for the names of students and their scores.
You can do something like this below.

```python
name_and_score = [{'name': student['name'], 'score': student['score']} for student in students]
print(name_and_score)
we have this as our output 
[{'name': 'Kenny', 'score': 78}, {'name': 'Blessing', 'score': 65}, {'name': 'Ibrahim', 'score': 87}, {'name': 'John', 'score': 90}, {'name': 'Enema', 'score': 35}]
```
## Checking For List Length
You can also check the length of a list using the len() method.

```python
Students_lenght = len(students)
no_of_users = len(students)
print(no_of_users)
this will print 5 because we have 5 students on our list
```

## Wrap up
In this article, I have been able to explain different ways list comprehension can be applied in python code. With list comprehension, you can build a complex list using a single line of code. Python loves you and wants to protect your sanity.
