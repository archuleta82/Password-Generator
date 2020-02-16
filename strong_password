# Author: Steven Archuleta
# Date: 31 Dec 2019
# To generate random passwords for accounts.

import random
letters = "abcdefghijklmnopqrstuvwxyz"
specials = "*&$%#@!-"
password = ""

def makePassword():
  wordpass = []
  for i in range(random.randint(6,12)):
    selector = (random.randint(0,25) + random.randint(0,25))
    selector = round(selector)
    wordpass.append(selector)
    
  letters = "abcdefghijklmnopqrstuvwxyz"
  specials = "*&$%-#@!:"
  password = ""
  
  for w in wordpass:
    if w < 25:
      if w < len(specials):
        w = specials[random.randint(0,len(specials)-1)]
      else:
        w = w - random.randint(0,4)
    else:
      index = 50 - w
      #print("Index: " +str(index))
      w = letters[index]
      if random.randint(0,100) % 3 == 0:
        w = w.capitalize()
    password += str(w)

  if len(password) > 10:
    password = password[:10]

  return str(password)

def nicePrint(a,b,c,d,password):
  print("\nPassword: " + password +"\nNumber count: " + str(a) + "\nlowercase: " + str(b) + "\nUppercase: " + str(c) + "\nSpecials: " + str(d))

def checkPassword(a):
  numberCount = 0
  letterLower = 0
  letterUpper = 0
  special = 0
  if a[-1]== '-' or a[0] == '-':
    return False
  for i in a:
    if i in specials:
      special += 1
    elif i.lower() in letters:
      if i.isupper() == True:
        letterUpper += 1
      else:
        letterLower += 1
    else:
      numberCount += 1
  if numberCount < 1 or letterLower < 1 or letterUpper < 1 or special < 1:
    return False
  else:
    # nicePrint(numberCount,letterLower,letterUpper,special,a)
    return True

def strongPassword():
  password1 = makePassword()
  result = ""
  if checkPassword(password1) == True:
    result = password1
    return result
  else:
    return strongPassword()
    
for i in range(1,6):
print("Choice number {}: ".format(i) + strongPassword())
