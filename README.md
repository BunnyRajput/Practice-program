# Practice-program
Programs
def print_prime_factors(number):
  # Start with two, which is the first prime
  factor = 2
  # Keep going until the factor is larger than the number
  while factor <= number:
    # Check if factor is a divisor of number
    if number % factor == 0:
      # If it is, print it and divide the original number
      print(factor)
      number = number / factor
    else:
      # If it's not, increment the factor by one
      factor = factor+1
      ___
  return "Done"

print_prime_factors(100)
# Should print 2,2,5,5
# DO NOT DELETE THIS COMMENT


def is_power_of_two(n):
  # Check if the number can be divided by two without a remainder
  while n % 2 == 0:
    if(n==0):
      return False

    n = n / 2
  # If after dividing by two the number is 1, it's a power of two
  if n == 1:
    return True
  return False
  Additional Recursion Sources
  
  Given a list of filenames, we want to rename all the files with extension hpp to the extension h. To do this, we would like to generate a new list called newfilenames, consisting of the new filenames. Fill in the blanks in the code using any of the methods you’ve learned thus far, like a for loop or a list comprehension.
  filenames = ["program.c", "stdio.hpp", "sample.hpp", "a.out", "math.hpp", "hpp.out"]
# Generate newfilenames as a list containing the new filenames
# using as many lines of code as your chosen method requires.
newfilenames = [e.replace('.hpp','.h') for e in filenames]

print(newfilenames) 
# Should be ["program.c", "stdio.h", "sample.h", "a.out", "math.h", "hpp.out"]

Question 2
Let's create a function that turns text into pig latin: a simple text transformation that modifies each word moving the first character to the end and appending "ay" to the end. For example, python ends up as ythonpay.
def pig_latin(text):
  words = text.split()
  pigged_text = []

  for word in words:
    word = word[1:] + word[0] + 'ay'
    pigged_text.append(word)

  return ' '.join(pigged_text)

print(pig_latin("hello how are you"))
		
print(pig_latin("hello how are you")) # Should be "ellohay owhay reaay ouyay"
print(pig_latin("programming in python is fun")) # Should be "rogrammingpay niay ythonpay siay unfay"
Question 3
The permissions of a file in a Linux system are split into three sets of three permissions: read, write, and execute for the owner, group, and others. Each of the three values can be expressed as an octal number summing each permission, with 4 corresponding to read, 2 to write, and 1 to execute. Or it can be written with a string using the letters r, w, and x or - when the permission is not granted.
For example: 
640 is read/write for the owner, read for the group, and no permissions for the others; converted to a string, it would be: "rw-r-----"
755 is read/write/execute for the owner, and read/execute for group and others; converted to a string, it would be: "rwxr-xr-x"
Fill in the blanks to make the code convert a permission in octal format into a string format.
def octal_to_string(octal):
    permission = ["---", "--x", "-w-", "-wx", "r--", "r-x", "rw-", "rwx"]
    result = ""
    # Iterate over each of the digits in octal
    for ___ in [int(n) for n in str(octal)]:
        result += permission[___]
    return result
    
print(octal_to_string(755)) # Should be rwxr-xr-x
print(octal_to_string(644)) # Should be rw-r--r--
print(octal_to_string(750)) # Should be rwxr-x---
print(octal_to_string(600)) # Should be rw-------
Question 5
The group_list function accepts a group name and a list of members, and returns a string with the format: group_name: member1, member2, … For example, group_list("g", ["a","b","c"]) returns "g: a, b, c". Fill in the gaps in this function to do that.

1 / 1 point

def group_list(group, users):
 return "{} : {}".format(group,", ".join(users))
 
print(group_list("Marketing", ["Mike", "Karen", "Jake", "Tasha"])) # Should be "Marketing: Mike, Karen, Jake, Tasha"
print(group_list("Engineering", ["Kim", "Jay", "Tom"])) # Should be "Engineering: Kim, Jay, Tom"
print(group_list("Users", "")) # Should be "Users:"
Question 6
The guest_list function reads in a list of tuples with the name, age, and profession of each party guest, and prints the sentence "Guest is X years old and works as __." for each one. For example, guest_list(('Ken', 30, "Chef"), ("Pat", 35, 'Lawyer'), ('Amanda', 25, "Engineer")) should print out: Ken is 30 years old and works as Chef. Pat is 35 years old and works as Lawyer. Amanda is 25 years old and works as Engineer. Fill in the gaps in this function to do that. 
def guest_list(l):

   for i in l:

       print("{0} is {1} old and works as {2}.".format(i[0],i[1],i[2]))

l=[('Ken', 30, "Chef"), ("Pat", 35, 'Lawyer'), ('Amanda', 25, "Engineer")]

guest_list(l)

guest_list([('Ken', 30, "Chef"), ("Pat", 35, 'Lawyer'), ('Amanda', 25, "Engineer")])

#Click Run to submit code
"""
Output should match:
Ken is 30 years old and works as Chef
Pat is 35 years old and works as Lawyer
Amanda is 25 years old and works as Engineer
"""

Additional Recursion Sources
In the past videos, we visited the basic concepts of recursive functions.

A recursive function must include a recursive case and base case. The recursive case calls the function again, with a different value. The base case returns a value without calling the same function.

A recursive function will usually have this structure:
def recursive_function(parameters):
    if base_case_condition(parameters):
        return base_case_value
    recursive_function(modified_parameters)
  

print(is_power_of_two(0)) # Should be False
print(is_power_of_two(1)) # Should be True
print(is_power_of_two(8)) # Should be True
print(is_power_of_two(9)) # Should be False


def sum_divisors(n):
  sum =0
  for i in range(1,n):
    if n%i ==0:
      sum = sum + i
  return sum
  

print(sum_divisors(0))
# 0
print(sum_divisors(3)) # Should sum of 1
# 1
print(sum_divisors(36)) # Should sum of 1+2+3+4+6+9+12+18
# 55
print(sum_divisors(102)) # Should be sum of 2+3+6+17+34+51
# 114


def multiplication_table(number=0):
	# Initialize the starting point of the multiplication table
	multiplier = 1
	# Only want to loop through 5
	while multiplier <= 5:
		result = multiplier*number
		# What is the additional condition to exit out of the loop?
		if result >25:
			break
		print(str(number) + "x" + str(multiplier) + "=" + str(result))
		# Increment the variable for the loop
		multiplier += 1

multiplication_table(3) 
# Should print: 3x1=3 3x2=6 3x3=9 3x4=12 3x5=15

multiplication_table(5) 
# Should print: 5x1=5 5x2=10 5x3=15 5x4=20 5x5=25

multiplication_table(8)	
# Should print: 8x1=8 8x2=16 8x3=24

Question 2
Fill in the blanks to make the factorial function return the factorial of n. Then, print the first 10 factorials (from 0 to 9) with the corresponding number. Remember that the factorial of a number is defined as the product of an integer and all integers before it. For example, the factorial of five (5!) is equal to 1*2*3*4*5=120. Also recall that the factorial of zero (0!) is equal to 1.
def factorial(n):
    result = 1
    for x in range(1,n):
        result = result *x
    return result

for n in range(0,10):
    print(n, factorial(n+1))


Question 3
Write a script that prints the first 10 cube numbers (x**3), starting with x=1 and ending with x=10.
for i in range(1,11):
  print(i*i*i)
  
  Write a script that prints the multiples of 7 between 0 and 100. Print one multiple per line and avoid printing any numbers that aren't multiples of 7. Remember that 0 is also a multiple of 7.
  for i in range(0,100):
    if i %7 ==0:
        print(i)
Question 5
The retry function tries to execute an operation that might fail, it retries the operation for a number of attempts.  Currently the code will keep executing the function even if it succeeds. Fill in the blank so the code stops trying after the operation succeeded.
def retry(operation, attempts):
  for n in range(attempts):
    if operation():
      print("Attempt " + str(n) + " succeeded")
      break
    else:
      print("Attempt " + str(n) + " failed")

retry(create_user, 3)
retry(stop_service, 5)
	
Question 1
Fill in the blanks of this code to print out the numbers 1 through 7.
number = 1
while number<= 7:
	print(number, end=" ")
	number=number+1
Question 2
The show_letters function should print out each letter of a word on a separate line. Fill in the blanks to make that happen.
def show_letters(word):
	for letter in word:
		print(letter)

show_letters("Hello")
# Should print one line per letter
Complete the function digits(n) that returns how many digits the number has. For example: 25 has 2 digits and 144 has 3 digits. Tip: you can figure out the digits of a number by dividing it by 10 once per digit until there are no digits left.
def digits(n):
	count = 0
	if n == 0:
	  return 1
	while (n>0):
		count += 1
		n = n//10
	return count
	
print(digits(25))   # Should print 2
print(digits(144))  # Should print 3
print(digits(1000)) # Should print 4
Question 4
This function prints out a multiplication table (where each number is the result of multiplying the first number of its row by the number at the top of its column). Fill in the blanks so that calling multiplication_table(1, 3) will print out:
def multiplication_table(start, stop):
	for x in range(start, stop+1):
		for y in range(start,stop+1):
			print(str(x*y), end=" ")
		print()

multiplication_table(1, 3)
# Should print the multiplication table shown above
Question 5
The counter function counts down from start to stop when start is bigger than stop, and counts up from start to stop otherwise. Fill in the blanks to make this work correctly.
def counter(start, stop):
	x = start
	if start>stop:
		return_string = "Counting down: "
		while x >= stop:
			return_string += str(x)
			if x >stop:
				return_string += ","
			x = x-1
	else:
		return_string = "Counting up: "
		while x <= stop:
			return_string += str(x)
			if x<stop:
				return_string += ","
			x= x+1
	return return_string

print(counter(1, 10)) # Should be "Counting up: 1,2,3,4,5,6,7,8,9,10"
print(counter(2, 1)) # Should be "Counting down: 2,1"
print(counter(5, 5)) # Should be "Counting up: 5"
Question 6
The even_numbers function returns a space-separated string of all positive numbers that are divisible by 2, up to and including the maximum that's passed into the function. For example, even_numbers(6) returns “2 4 6”. Fill in the blank to make this work.
def even_numbers(maximum):
	return_string = ""
	for x in range(2, maximum+1,2):
		return_string += str(x) + " "
	return return_string.strip()

print(even_numbers(6))  # Should be 2 4 6
print(even_numbers(10)) # Should be 2 4 6 8 10
print(even_numbers(1))  # No numbers displayed
print(even_numbers(3))  # Should be 2
print(even_numbers(0))  # No numbers displayed
Question 7
The following code raises an error when executed. What's the reason for the error?
def decade_counter():
	while year < 50:
		year += 10
	return year
What is the value of x at the end of the following code?
for x in range(1, 10, 3):
    print(x)
 Question 9
What is the value of y at the end of the following code?
for x in range(10):
    for y in range(x):
        print(y)
How does this function need to be called to print yes, no, and maybe as possible options to vote for?
def votes(params):
	for vote in params:
	    print("Possible option:" + vote)
print(digits(0))    # Should print 1

Question 1
The is_palindrome function checks if a string is a palindrome. A palindrome is a string that can be equally read from left to right or right to left, omitting blank spaces, and ignoring capitalization. Examples of palindromes are words like kayak and radar, and phrases like "Never Odd or Even". Fill in the blanks in this function to return True if the passed string is a palindrome, False if not.
def is_palindrome(input_string):
	# We'll create two strings, to compare them
	new_string = ""
	reverse_string = ""
	input_string = input_string.lower()
	# Traverse through each letter of the input string
	for e in input_string:
		# Add any non-blank letters to the 
		# end of one string, and to the front
		# of the other string. 
		if e !=" ":
			new_string += new_string
			reverse_string +=reverse_string 
	# Compare the strings
	if new_string == reverse_string:
		return True
	return False

print(is_palindrome("Never Odd or Even")) # Should be True
print(is_palindrome("abc")) # Should be False
print(is_palindrome("kayak")) # Should be True
Question 2
Using the format method, fill in the gaps in the convert_distance function so that it returns the phrase "X miles equals Y km", with Y having only 1 decimal place. For example, convert_distance(12) should return "12 miles equals 19.2 km".
def convert_distance(miles):
	km = miles * 1.6 
	result = "{} miles equals {:.1f} km".format(miles, km)
	return result

print(convert_distance(12)) # Should be: 12 miles equals 19.2 km
print(convert_distance(5.5)) # Should be: 5.5 miles equals 8.8 km
print(convert_distance(11)) # Should be: 11 miles equals 17.6 km


Question 3
If we have a string variable named Weather = "Rainfall", which of the following will print the substring or all characters before the "f"?
Question 4
Fill in the gaps in the nametag function so that it uses the format method to return first_name and the first initial of last_name followed by a period. For example, nametag("Jane", "Smith") should return "Jane S."
def nametag(first_name, last_name):
	return("{}, {:.1s}".format(first_name,last_name))

print(nametag("Jane", "Smith")) 
# Should display "Jane S." 
print(nametag("Francesco", "Rinaldi")) 
# Should display "Francesco R." 
print(nametag("Jean-Luc", "Grand-Pierre")) 
# Should display "Jean-Luc G." 

Question 5
The replace_ending function replaces the old string in a sentence with the new string, but only if the sentence ends with the old string. If there is more than one occurrence of the old string in the sentence, only the one at the end is replaced, not all of them. For example, replace_ending("abcabc", "abc", "xyz") should return abcxyz, not xyzxyz or xyzabc. The string comparison is case-sensitive, so replace_ending("abcabc", "ABC", "xyz") should return abcabc (no changes made). 
def replace_ending(sentence, old, new):
	# Check if the old string is at the end of the sentence 
	if sentence.endswith(old):
		# Using i as the slicing index, combine the part
		# of the sentence up to the matched string at the 
		# end with the new string
		
		i = sentence.rfind(old)
		new_sentence = sentence[:i]+new
		return new_sentence

	# Return the original sentence if there is no match 
	return sentence
	
print(replace_ending("It's raining cats and cats", "cats", "dogs")) 
# Should display "It's raining cats and dogs"
print(replace_ending("She sells seashells by the seashore", "seashells", "donuts")) 
# Should display "She sells seashells by the seashore"
print(replace_ending("The weather is nice in May", "may", "april")) 
# Should display "The weather is nice in May"
print(replace_ending("The weather is nice in May", "May", "April")) 
# Should display "The weather is nice in April"
Complete the code to iterate through the keys and values of the cool_beasts dictionary. Remember that the items method returns a tuple of key, value for each element in the dictionary.
cool_beasts = {"octopuses":"tentacles", "dolphins":"fins", "rhinos":"horns"}
for beast , feature in cool_beasts.items():
    print("{} have {}".format(beast,feature))

Iterating Over Dictionaries
You can iterate over dictionaries using a for loop, just like with strings, lists, and tuples. This will iterate over the sequence of keys in the dictionary. If you want to access the corresponding values associated with the keys, you could use the keys as indexes. Or you can use the items method on the dictionary, like dictionary.items(). This method returns a tuple for each element in the dictionary, where the first element in the tuple is the key and the second is the value.

If you only wanted to access the keys in a dictionary, you could use the keys() method on the dictionary: dictionary.keys(). If you only wanted the values, you could use the values() method: dictionary.values()
badges
Add a comment

0

In Python, a dictionary can only hold a single value for a given key. To workaround this, our single value can be a list containing multiple values. Here we have a dictionary called "wardrobe" with items of clothing and their colors. Fill in the blanks to print a line for each item of clothing with each color, for example: "red shirt", "blue shirt", and so on.

This gives the accurate required answer
wardrobe = {"shirt":["red","blue","white"], "jeans":["blue","black"]}

for clothes,colors in wardrobe.items():

 for color in colors:
    
    print("{} {}".format(color,clothes))
    
 
Dictionary Methods Cheat Sheet
Dictionary Methods Cheat Sheet
Definition

x = {key1:value1, key2:value2} 

Operations

len(dictionary) - Returns the number of items in the dictionary
for key in dictionary - Iterates over each key in the dictionary
for key, value in dictionary.items() - Iterates over each key,value pair in the dictionary
if key in dictionary - Checks whether the key is in the dictionary
dictionary[key] - Accesses the item with key key of the dictionary
dictionary[key] = value - Sets the value associated with key
del dictionary[key] - Removes the item with key key from the dictionary
Methods

dict.get(key, default) - Returns the element corresponding to key, or default if it's not present
dict.keys() - Returns a sequence containing the keys in the dictionary
dict.values() - Returns a sequence containing the values in the dictionary
dict.update(other_dictionary) - Updates the dictionary with the items coming from the other dictionary. Existing entries will be replaced; new entries will be added.
dict.clear() - Removes all the items of the dictionary
The email_list function receives a dictionary, which contains domain names as keys, and a list of users as values. Fill in the blanks to generate a list that contains complete email addresses (e.g. diana.prince@gmail.com).
def email_list(domains):
	emails = []
	for domain, users in domains.items():
		for user in users:
			emails.append(user+'@'+domain)
	return(emails)

print(email_list({"gmail.com": ["clark.kent", "diana.prince", "peter.parker"], "yahoo.com": ["barbara.gordon", "jean.grey"], "hotmail.com": ["bruce.wayne"]}))

Question 2
The groups_per_user function receives a dictionary, which contains group names with the list of users. Users can belong to multiple groups. Fill in the blanks to return a dictionary with the users as keys and a list of their groups as values. 
def groups_per_user(group_dictionary):
    user_groups = {}
    groups = []
    # Go through group_dictionary
    for group,users in group_dictionary.items():
        # Now go through the users in the group
        for user in users:
        # Now add the group to the list of
          # groups for this user, creating the entry
          # in the dictionary if necessary
          groups.append(group)
          user_groups[user] = group

    return(user_groups)

print(groups_per_user({"local": ["admin", "userA"],
        "public":  ["admin", "userB"],
        "administrator": ["admin"] }))
Question 3
The dict.update method updates one dictionary with the items coming from the other dictionary, so that existing entries are replaced and new entries are added. What is the content of the dictionary “wardrobe“ at the end of the following code?

Question 1
The email_list function receives a dictionary, which contains domain names as keys, and a list of users as values. Fill in the blanks to generate a list that contains complete email addresses (e.g. diana.prince@gmail.com).
def email_list(domains):
	emails = []
	for domain, users in domains.items():
		for user in users:
			emails.append(user+'@'+domain)
	return(emails)

print(email_list({"gmail.com": ["clark.kent", "diana.prince", "peter.parker"], "yahoo.com": ["barbara.gordon", "jean.grey"], "hotmail.com": ["bruce.wayne"]}))
.
Question 2
The groups_per_user function receives a dictionary, which contains group names with the list of users. Users can belong to multiple groups. Fill in the blanks to return a dictionary with the users as keys and a list of their groups as values. 
def groups_per_user(group_dictionary):
    user_groups = {}
    groups = []
    # Go through group_dictionary
    for group,users in group_dictionary.items():
        # Now go through the users in the group
        for user in users:
        # Now add the group to the list of
          # groups for this user, creating the entry
          # in the dictionary if necessary
          groups.append(group)
          user_groups[user] = group

    return(user_groups)

print(groups_per_user({"local": ["admin", "userA"],
        "public":  ["admin", "userB"],
        "administrator": ["admin"] }))
	Question 5
The add_prices function returns the total price of all of the groceries in the  dictionary. Fill in the blanks to complete this function.
def add_prices(basket):
	total = 0
	for items in basket.values():
		total += items
	return round(total, 2)
	 

groceries = {"bananas": 1.56, "apples": 2.50, "oranges": 0.99, "bread": 4.59, 
	"coffee": 6.99, "milk": 3.39, "eggs": 2.98, "cheese": 5.44}

print(add_prices(groceries)) # Should print 28.44


