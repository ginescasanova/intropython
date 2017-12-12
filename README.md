# intropython
Scripts del curso  Introduction to Computer Science de Udacity

# Clase 5: Procedures

# Ejercicio 1:
# Define a procedure, sum3, that takes three
# inputs, and returns the sum of the three
# input numbers.
# To help you out, the code for sum(a,b) is below.
# Ejemplos:
#print sum3(1,2,3) #>>> 6
#print sum3(93,53,70)#>>> 216
# Respuesta:
def sum3(a, b, c):
    return a + b + c

x=1
y=2
z=3

print sum3(x, y, z)

# Ejercicio 15: 

# Define a procedure, find_second, that takes
# two strings as its inputs: a search string
# and a target string. It should return a
# number that is the position of the second
# occurrence of the target string in the
# search string.
#Respuesta:
def find_second (a, b): 
    first = a.find (b)
    return a.find (b, first+1)
    
danton = "De l'audace, encore de l'audace, toujours de l'audace"

print find_second(danton, 'audace')

#>>> 25

# Ejercicio 17:
# Define a procedure, bigger, that takes in
# two numbers as inputs, and returns the
# greater of the two inputs.

def bigger(a, b):
    if a > b:
        return a
    return b

print bigger(6, 7)
print bigger(8, 7)

# otra posibilidad seria:

def bigger(a,b):
    if a > b:
        return a
    else:
        return b

print bigger(6, 7)
print bigger(8, 7)

# Ejercicio 18:
# Define a procedure, is_friend, that
# takes a string as its input, and
# returns a Boolean indicating if
# the input string is the name of
# a friend. Assume I am friends with
# everyone whose name starts with D
# and no one else. You do not need to
# check for the lower case 'd'

# Respuesta: 
def is_friend (name):
    if name[0] == 'D':
        return True
    else: 
        return False
    
print is_friend('Diane')
print is_friend('Fred')

# otra forma de hacerlo: como queremos recuperar un valor booleano (True/False) es suficiente con que el procedimiento describa una ecuación comparativa... así que no es estructamente necesario usar un if-statement:

def is_friend(name):
    return name[0] == "D"

print is_friend('Diane')
print is_friend('Fred')

# Ejercicio 19:

# Define a procedure, is_friend, that takes
# a string as its input, and returns a
# Boolean indicating if the input string
# is the name of a friend. Assume
# I am friends with everyone whose name
# starts with either 'D' or 'N', but no one
# else. You do not need to check for
# lower case 'd' or 'n'

def is_friend (name):
    if name[0] == 'D':
        return True
    if name[0] == "N": 
        return True
    else: 
        return False
    
print is_friend('Diane')
print is_friend('Ned')
print is_friend('Moe')

def is_friend (name):
    if name[0] == 'D':
        return True
    else: 
        if name[0] == "N": 
            return True
        else: 
            return False
    
print is_friend('Diane')
print is_friend('Ned')
print is_friend('Moe')

# Ejercicio 21 (no lo resolví):
# Define a procedure, biggest, that takes three
# numbers as inputs and returns the largest of
# those three numbers.

def biggest(a,b,c):
    if a > b:
        if a > c:
            return a
        else:   
            return c
    else:
        if b > c:
            return b
        else:
            return c

print biggest(3, 6, 9)
#>>> 9
print biggest(6, 9, 3)
#>>> 9
print biggest(9, 3, 6)
#>>> 9
print biggest(3, 3, 9)
#>>> 9
print biggest(9, 3, 9)
#>>> 9

# O se puede repetir dos veces un proceso menor: bigger. 
# De esa manera, se despeja primer el mayor entre a y b, 
# y ese resultado se compara con c, despejando el mayor
# de los tres:

def bigger (a,b):
    if a > b:
        return a
    else:
        return b

def biggest(a,b,c):
    return bigger (bigger(a,b),c)
        
print biggest(3, 6, 9)
#>>> 9
print biggest(6, 9, 3)
#>>> 9
print biggest(9, 3, 6)
#>>> 9
print biggest(3, 3, 9)
#>>> 9
print biggest(9, 3, 9)
#>>> 9
