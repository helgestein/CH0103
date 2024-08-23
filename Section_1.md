
Copyright (c) 2024 Prof.Dr.-Ing Helge Sören Stein, Technische Universität München
<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-nd/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nd.svg?ref=chooser-v1" alt=""></a></p>

Chemistry has been a data driven science from the early beginnings. The Periodic Table is a great example of how gathering, structuring, and visualization of data can help chemists in studying the change of matter.
In the last decades however the advancements of computer science have not fully proliferated to chemistry and the study programs though chemists need to deal with software, computing, and robotics in their everyday career.
This course seeks to change that by going a slightly different route than conventional “Here is how we teach you programming in python”. I do this because every science is in my opinion teaching you a way of thinking about the world. Physicists have a certain perspective and approach to solving challenges, Chemists have another. Computer scientists are also different in approaching a problem - so are Sociologists, Biologists and Philosophers.
In this course I want to show you a toolset on how to approach problems through algorithms and data structures because Chemistry is algorithmic and thinking about chemistry happens in complex (data) structures. Interestingly mathematics is not really about numbers either - it is the study of structures. I digress.

### How to get the most out of this course?

Think for yourself and don’t think in prompts you feed to a large language model. Im serious: **Do yourself the favor of not using any of the large language models early in your studies (I'd say 4-5 semester)**. You may be thinking: oh great another hater of AI. That is not the case. I hate to break it to you but you are at a stage of your career and knowledge that you are not yet even capable of understanding the sometimes sublte mistakes a LLM will generate. Not just that, you won't ever get a grip on understanding the thought structures that are needed to creatively think. Believe it or not but most innovations by scientists rely on the very foundations taught in the first introductionary lectures. You need to understand that at a university, and specifically in a undergraduate course like chemistry or physics, it is maybe 40% formal knowledge, 20% manual skills, and 40% structuring your thought process. We. teach. you. how. to. think. If you go everywhere with a car you might not forget to walk but to be excellent scientists you need to be able to run a marathon. Yes, doing all of this "the old fashioned way" is less convenient and defenetly more annoying but it will teach you so much more. They will anyway not help you as the graded tests are on paper and all analogue. We will do things slightly different from other courses as an experiment.

### Thinking in Data Structures

Everything in the universe is an object. Every object is part of a class and very often the specific instance of an object is what we actually care about. Ok this is a lot of words and might sound like a introduction aty philosophy class so let me turn this into a chemistry class.
You should have heard of elements. Likely some of your friends or family will have gifted you a periodic table and in the inorganic chemistry lecture hall there is a 10m long one. So what properties do elements have? They all have a name e.g. Nitrogen and an average atomic mass e.g. 55.8u. Now to build up molecules and condensed matter structures we would assemble specific instances of atoms which are elements. Is an element and atom? Yes and no. A atom is a specific thing that exists in the universe whilst an element is a concept.
This data structure is called an object and in the programming language that we want to learn (python) the syntax i.e. the way how we tell our programming language what we want is this:

```python
class Element:
	pass
```


This code in it self does very little and is mostly concerned with the syntax which tells “python” what we want. So let’s dissect these two lines of code. We start with the word `class` which is pythons way of saying “here I define an object” we then write `Element` because we name this object ”Element“. Please note that virtually all programming languages are case sensitive i.e. it makes a difference if you Wirte Element, element, eLeMeNt or eleMent. What follows then is a color which tells python that you are done naming your class. The next line of code has an indentation. Indentations tell python that the code that follows belongs to what has been named above. The word `pass` in the following line is essentially telling python to pass this section of the code without doing anything.
We can now create an instance of our element. Let’s say we want to create iron. To do so we need to create an instance of element by creating a variable. 


```python
a = Element()
```

The variable `a` is now an instance of Element. Why variable? Well, we can change a and that makes a "variable". Let’s give our (arguably very abstract variable) ```a``` name and a mass. Name and Mass are attributes of an element and the notation is `variableName.attribute`. We can for now treat attributes like variables. Let's do this for helium

```python
"""<--this is how you start a multiline comment
Helium:
 ┌────────────────┐
 │ 2       4.0026 │
 │      He        │
 │     Helium     │
 └────────────────┘
this is how you end it -->"""
a.name = “Helium” #setting the name btw a # starts a single line comment
a.mass = 4.0026 #setting the mass
```

We just now had to put the letters that make up the word Helium into parentheses because if we simply write a word like `Helium` without putting it in parentheses like ``“Helium”`` would lead python to the expectation that there is a Variable called Iron. Numbers are simply written as such and if we want to make a comment we write a hashtag and everything in that line after the hashtag is ignored. Note how the equal sign sets the thing on the left to the thing of the right.
With this we also have two very simple data types introduced. aa.name is a so called string i.e. a chained or stringed together list of characters. The other data type is called a float i.e. a number with a floating point (German: Fliesskomma). We could have also used the engineering notation

```python
a.mass = 400e-2 #setting the mass
```

which is equivalent of saying $$400*10^{-2}=4.00$$

If we would like to retrieve the information we stored in a.name we simply write:

```python
print(a.name) #this should return ”Helium”
```

Same goes naturally for the mass of a. Remember how I said that a string is a list of characters? What if I want to get the second letter of `a.name` ? We can access it by adding brackets at the end like this:

```python
print(a.name[0:2]) #this should return ”He”
```

The last bit of code should return "He" which happens to be also the symbol of the Element Helium. Noe the notation wit the brakets ``[0:2]`` ... what does this do? This notation tells python that we would like to access elements from a list. To acess the first element in a list we can simpy type ``[0]`` and to acess the second element we type ``[1]`` - this is because python and many other programming alnguages are zero-indexed i.e. the first element has index zero. Now you might be rightfully asking: then why are you writing ``[0:2]`` in the code above? Well, this is because the notation in python goes such that you ask for elements from a list with the starting element index to the first excluded element i.e. ``[start_index:end_index+1]``. This arguably strange notation makes sense if you start thinking about indexing from the back. If you want to get the last element from a list you can simply type ``[-1]``.

This was a lot of information so here are some things for you to try out:
- add a symbol attribute to your element by directly setting it with a string
- Now also try adding the symbol element using the first two characters of the name

### Mini Project No. 1: Custom Element Symbol v1
*We know that this will create very wrong symbols for some elements. As an example: consider the name "Iron" - the first two letters will be "Ir" which is the symbol of Iridium that would also (correctly) be "Ir". Since some symbols have little to do with the name of the element let's design our own unique elemental identifier. The shortest element name in the english language is "Tin" and in german it is "Iod". So we have three letters minimum. Let's do it like this: We generate a "custom symbol" by taking the first two letters of the name and adding to that the last two letters of the name. You can add characters and strings via the ``+`` sign. For Iron this would be ``"Ir"`` and ``"on"`` ... so not super creative. Think about how to access the second last element **and** the last element - there are multiple ways. Write your code in a reusable fashion i.e. setting the new symbol not with the literal "Ir" and "on" strings but using the bracket notation by using name.*

So now we have our own custom element but I want to let you in on a secret: most people are lazy and don't like repetitive work and I assume you are no different. What most people do like however is rewarding work. There are few things as blissful as solving a hard challenge with an elegantly (sometimes even simple) solution. We don't want to leave our element class to be as dumb as it was and we would like to add some more structure to it. This will also help in readability. Remember when I wrote "we create an instance of our class"? This process is called initialization. See below for a small graphical visualization of the process of initializing an instance from a class.

```
 ┌─────────┐    initialization     ┌────────────────────┐
 │  Class  │     (short: init)     │      Instance      │
 │(Concept)│──────────────────────▶│ (Specific Object)  │
 └─────────┘     a = Element()     └────────────────────┘   
  class Element:                             a           
         pass                                            
```

Here is a general rule of thumb: ***shorter code is more readable***. Imagine you have some code like this:

```python
class Element:
	pass

a = Element()
a.mass = 2.03
a.name = "Hydrogen"

b = Element()
b.mass = 4.12
b.name = "Helium"

c = Element()
c.mass = 6.02
c.Name = "Beryllium"
```

I think this code is pretty ugly, and also slightly wrong. First of all someone who looks at this code will have no Idea what structure Element has and might rightfully ask "Is this an Element from the Periodic table?", or "Is this an Element of a list?". Also the code is long and our instance c has an attribute ```c.Name``` whilst all others have a ```.name``` attribute (remember: cases matter and vAriable and varIABLE are two different variables). That is pretty bad code and this sloppiness is made possibile by writing "spaghetti code". 
Let's fix this.
Inside the class we can add a code block that starts with a specific name/notation called ```__init__``` which is called upon initialization. This code block is a function but a so called *magic function*. Lets first however discuss what a function is. Functions in most programming languages work like what you are used to from math i.e. they take an argument and return a value or they "do something" when they "function". Need an example? Consider a simple polynominal function like this:

$$f(x)= 3+2*x$$
this function take a parameter $x$ multiplies it by $2$ and adds 3 to it it then returns a value such that:
$$y = f(10)$$
will result in $f$ returning 23 and thus setting $y=23$. So how would this work in python? Like this:

```python 
def f(argumentNumberOne):
	value = 3+2*argumentNumberOne
	return value
```

the syntax word `def` tells python that we are going to define a function, here named `f`. if we add parentheses we can tell python that this function takes an argument called `argumentNumberOne` which is then multiplied by `2` and we add `3` to it to set a variable called `value` which is returned in the next line. Please not that the text that belongs to the function is indented. This has syntactic significance for python as it saves you from doing curly brackets like in many other languages and makes python ever so slightly more readable.
Ok let's see this in action:

```python 
x = 10
def f(argumentNumberOne):
	value = 3+2*argumentNumberOne
	return value
y = f(x)
print(y)
```

so this code will set `x` to `10` pass that value to our function, the function does its thing and then the function returns `23` and we set `y` to `23` and then we `print` it. If you run this code in a python console it will just spit the number `23` at you.
if we set `u = f(100)` and print `u` we have a simple example of reusing a function (which is their main purpose: reuse of code blocks)
### Mini Project No. 2: Scoping and your first error
Try setting `y=value` and **read** the error message and try to understand it. Imagine a function to work like a room in which you can pass in information wie a form (the arguments) and you recieve a form back (via the return). The people in that room can look at your information but you are not allowed to peek in.

### Mini Project No. 3: Non error-producing but still wrong code
Try setting value like `value = 3+2*x` ... this will spit out `23` as well doesn't it? Rerun this but now set `y=f(20)`. What is being printed?

### Mini Project No. 4: Making it modular
Write an improved version of `f` that takes in variables for the function `g(x)=a+m*x`. Once you have that set the arguments for a and m to standard values e.g. `m=2` and `a=3`  by setting them in right in the argument definition to their standard. Use the error codes produced to guide you. Don't scroll down as this will spoiler things.

Ok so much for our detour about functions. We wanted to make a better Element class. Remember: I told you that there is an initialization function that is "magic". Let's add that:

```python
class Element:
	def __init__(self,massArgument,nameArgument)
		self.mass = massArgument
		self.name = nameArgument
```

Now if we were to run our previous code:

```python
a = Element()
```

we will get an error saying something along the lines of:

```python
TypeError: Element.__init__() missing 2 required positional arguments: 'massArgument' and 'nameArgument'
```

so let's give element what it wants:

```python
a = Element(4.002,"Helium")
```

if we now ask what the name of our Element a is we get its name!

```python
print(a.name)
```

Ok we were on a mission to clean up the ugly codeblock from above.

```python
#ugly spaghetti coe with errors
class Element:
	pass

a = Element()
a.mass = 2.03
a.name = "Hydrogen"

b = Element()
b.mass = 4.12
b.name = "Helium"

c = Element()
c.mass = 6.02
c.Name = "Beryllium"
```

now becomes 🤗:

```python
#bliss
class Element:
	def __init__(self,massArgument,nameArgument)
		self.mass = massArgument
		self.name = nameArgument

a = Element(2.03,"Hydrogen")
b = Element(4.12,"Helium")
c = Element(6.02,"Beryllium")
```

Ok we are not yet perfect because if we were to run:

```python
d = Element('Wrongium',-3)
```

What is the Name and the mass of d?
What we need is type hinting which will create errors if we set things to the wrong value or type. It is quite simply done like this:

```python
#bliss
class Element:
	def __init__(self,massArgument: float,nameArgument: str)
		self.mass = massArgument
		self.name = nameArgument
```

Run the Wrongium element code again and see what happens. 
Let's say we don't remember how we ordered our arguments .. well we just call them by name!

```python
a = Element(nameArgument = "Hydrogen",massArgument = 2.03)
```

Ok cool now our element is kind of stupid. Very often we need to get the molar Weight or the density either by Mol or by kg.

### Mini Project No. 5: Making Element intelligent
Add another argument that takes in the density assuming it is in $g/cm^3$.  Then add a function to the Element class that takes no arguments besides `self` (because every function that wants to access information of the specific class instance it belongs to need to have `self` passed to it) and returns the molar density i.e. $mol/cm^3$. Then add another function that returns the mass if a molar amount is given.

> [!question]- Spoiler altert!
> Please note that here I also use the -> float notation which completes type hinting and ensures that if we pass our functions' result in another function that is type hinted we don't get an error. This is all optional but I want to show you 😇💫🌈 style code early on
> ```python
> class Element
> 	def __int__(self,massArg: float, nameArg: str, densityArg: float):
> 		self.mass = massArg
> 		self.name = nameArg
> 		self.density = densityArg
> 		
> 	def molar_density(self) -> float:
> 		molar_mass = self.mass_u #because 1u = g/mol
> 		return self.density / molar_mass
> 		
> 	def mass_for_mol(self, moles: float) -> float:
> 		molar_mass = self.mass_u
> 		return moles * molar_mass
> 	

Great now we have many tools up our sleeve but I need to show you some more data structures and looping before we can get into the nifty stuff.
A very convenient data structure is a list. List are an ordered way of storing information. He is for instance a list of the first 10 elements:

```python
elemental_names = [ "Hydrogen", "Helium", "Lithium", "Beryllium", "Boron", "Carbon", "Nitrogen", "Oxygen", "Fluorine", "Neon" ]
```

We can access the elemental names via the bracket notation as we did with strings that were "lists of characters". So this prints the first and the last element as well as the fifth element:

```python
print(elemental_names[0])
print(elemental_names[-1])
print(elemental_names[4])
```

We should be a little more verbose and can format this nicer like:

```python
index = 4
print("The " + str(index+1)+"th element is " + elemental_names[index])
```

here we need to pass `index+1` into a builtin function called `str`. This process is called "type casting" as strings cannot be added with numbers via the `+` sign. 

> [!question]- Side quest on typing
> what does the following code do and why? What do operators such as `+` and `*` really mean when I apply them to non-number objects strings and lists?
> ```python
> a = "Muenchen"
> print(a*10)

Ok now we also have information on the mass and density somewhere

```python
elemental_masses = [1.00,4.00,6.94,9.01,10.81,12.01,14.00,15.99,18.99,20.18]
elemental_densities = [0.8988e-4, 0.1785e-3, 0.534, 1.85, 2.34, 2.267, 0.12506e-2, 0.1429e-2, 0.1696e-2, 0.8999e-3]
```

Before we create a bunch of elemental objects let's get some slicing done first. Imagine lists and slices a bit like a spreadsheet calculator but better.
Let's say I don't know what element number is Boron. I can just do the following:

```python
elemental_names.index("Boron")
```

This will return me the index of Boron. Note this `.` notation! It is the same as what we would use to call a function from an object! I need to tell you a secret which I have withheld up until now: everything is an Object in python - even a list though it is its own data type it is also just another good ol' object. Oject have a cool conceptual property and that is: they can carry states or information about themselves that is dynamically updated if their internal state changes. Lets see this in action. Any list has a length. We can get it via a magic function called `.__len__()
`
```python
print(elemental_names.__len__()) #should be 10
```

Typically anything with a underscore is coming from "under the hood".
A often used property of lists is the pop function which "pops" an element from a list and returns it. We can "pop" Neon from our list like this (pretending we don't know its index):

```python
popped = elemental_names.pop(elemental_names.index("Boron"))
print(popped) #should be Boron
print(elemental_names) #all but Boron
print(elemental_names.__len__()) #should be 9 now
```

Now we will need Boron later and better append it at the end again. We do so like this:

```python
elemental_names.append(popped)
```

so if we run

```python
print(elemental_names) #all but Boron
print(elemental_names.__len__()) #should be 10 again
```

everything should be back to normal.

We can for instance make a list that contains the names, masses and densities - a list of lists or lol in short!

```python
lol = [elemental_names,elemental_masses,elemental_densities]
```

We can now access eleents of our list of lists like this:

```python
print(lol[2][5])
```

We could also make a list out of elements from lol that have mixed types:

```python
C = [lol[1][5],lol[0][5],lol[0][5]]
```

Little mini challenge: Can you still follow this Hütchenspiel? Print the elemental name that is stored in C!
It is often better to store data not in a ordered format like a list and call things by numbers but to name items in a collection of information. This data type is called a dictionary and it is created like this:

```python
CbutAsADict = dict(name=lol[0][5],density=lol[1][5],density=lol[2][5])
```

we can now very conveniently access the name via

```python
print(CbutAsADict['name'])
```

Our numeric indexes have now become strings and are now called `keys` behind which a `dict` stores `values`. 
Very often when we have some data we want to iterate through it in a loop. We can turn a list or a dictionary into an iterator object by calling the buildin function `iter(myList)` iter then works kind of like a friendly helper that has your list printed out in a book and will read every page to you when you ask it to. This iterator will then advance a page and know where it left off - it does wthis with a built in function called `next`.
For instance:

```python
namesIterator = iter(elemental_names)
massIterator = iter(elemental_masses)

firstName = next(namesIterator)
secondName = next(namesIterator)
thirdName = next(namesIterator)
# ...and so on

firstMass = next(massIterator)
secondMass = next(massIterator)
thirdMass = next(massIterator)
# ...and so on
```

This is all good but also very boring to write. If we need to iterate for larger repetitions (and that is anything larger than 1-2x IMHO!) we can use a for called for loop. A for loop will iterate over an iterator until it stops. When you reach the end it will actually throw an error:

```shell
In [10]: next(namesIterator)

---------------------------------------------------------------------------

StopIteration                             Traceback (most recent call last)

Cell In[10], line 1
```

To really understand how a for loop works let's spell out what it would be in code:

```python
namesIterator = iter(elemental_names)
currentValue = next(namesIterator) #1
print(currentValue)
currentValue = next(namesIterator) #2
print(currentValue)
currentValue = next(namesIterator) #3
print(currentValue)
currentValue = next(namesIterator) #4
print(currentValue)
currentValue = next(namesIterator) #5
print(currentValue)
currentValue = next(namesIterator) #6
print(currentValue)
currentValue = next(namesIterator) #7
print(currentValue)
currentValue = next(namesIterator) #8
print(currentValue)
currentValue = next(namesIterator) #9
print(currentValue)
currentValue = next(namesIterator) #10
print(currentValue)
```

Or as a for loop:

```python
namesIterator = iter(elemental_names)
for currentValue in namesIterator:
	print(currentValue)
```

Python does however come with batteries included and as you know: everything in python is an object such that lists actually have an iterator build in which can be accesses through `.__iter__()` thus directly writing:

```python
for currentValue in elemental_names:
	print(currentValue)
```

Works as well and this is precisely how I do it in 99.999% of all cases with a list.
Sometimes you want to iterate over two things at once. As long as both of these "things" have a `.__iter__()` function it will work. What we do in the case of multiple things that we'd like to iterate over: we "zip" them together like this:

```python
for name,mass in zip(elemental_names,elemental_masses):
	print("The element " + name + " has the mass " + str(mass) " u")
```

Cool huh? Now we are equipped for a small intermission project!
### Mini Project No. 6: Generating an element list
You have the Element Class right? With the three lists containing mass, density and Names you can now create a list that contains Element object instances that correspond to the first top 10 elements. Write a for loop that appends these instances to an empty list - which you can create with `myEmptyList = []`. Once you have that you can create a new list that contains all molar densities!

> [!question]- Spoiler altert!
> Please note that here I also use the -> float notation which completes type hinting and ensures that if we pass our functions' result in another function that is type hinted we don't get an error. This is all optional but I want to show you 😇💫🌈 style code early on
> ```python
> class Element
> 	def __int__(self,massArg: float, nameArg: str, densityArg: float):
> 		self.mass = massArg
> 		self.name = nameArg
> 		self.density = densityArg
> 		
> 	def molar_density(self) -> float:
> 		molar_mass = self.mass_u #because 1u = g/mol
> 		return self.density / molar_mass
> 		
> 	def mass_for_mol(self, moles: float) -> float:
> 		molar_mass = self.mass_u
> 		return moles * molar_mass
> #the following line is just so that the for loop line is not too long
> em,ed,en = elemental_masses,elemental_densities,elemental_names
> elemList = []
> for mass,dens,name in zip(em,ed,en):
> 	tempElement = Element(massArg=mass,nameArg=name,densityArg=density)
> 	elemList.append(tempElement)
> 	

We're still not done unfortunately.
A very useful thing is to be able to run some loop n-times. In python there is a special builtin function for that! It is called `range` and it takes a single argument, that is how many times you want to run a for loop (essentially). What it returns is a value that starts at `0` which is then increased every time that "next" function is called by the for loop. Again in the spaghetti code version:

```python
iterator = range(3)
i = next(iterator) # i is 0
print(i)
i = next(iterator) # i is 1
print(i)
i = next(iterator) # i is 2
print(i)
```

or as a for loop:
```python
for i in range(3):
	print(i)
```

Sometimes it convenient to loop over a list of something but also have a counter variable run at the same time. You could of course write bad code such as:

```python
i = 0
for mass in elemental_masses:
	print("The " + str(i) + "-th element has a mass of " + str(mass))
	i = i+1
```

or the much cleaner (and two lines shorter version):

```python
for i,mass in enumerate(elemental_masses):
	print("The " + str(i) + "-th element has a mass of " + str(mass))
```

what enumerate does is it returns a tuple i.e. two values (here a counter variable and the current element corresponding to that elements index position).
Tuples can be used in many ways, for instance if you have a list that contains mass, density, and name you can do the following:

```python
m1,d1,n1 = [5.04,2.3,'Blablonium']
m2,d2,n2 = [3.04,1.3,'Schablonium']

m1,m2 = m2,m1
```

this unpacks the values from the lists and then flips m1 and m2. This might sound useless not but it can come in very hands especially if you have a function that returns more than one value:

```python
def convertTemperature(kelvin: float):
	F = (kelvin − 273.15) × 9/5 + 32
	C = kelvin + 273.15
	return F,C

freedomTemp, euroTemp = convertTemperature(70)
```

Sometimes I have a function that returns some things that I don't need to there is a "waste" variable called `_` you can use it like this:

```python
_, euroTemp = convertTemperature(70)
```

This way you signal "here is something being returned but I throw it away" which is better then declaring an unused variable.
Not technically our function for converting the temperature from Kelvin in other units will accept negative Kelvin values which is not right. So we need cases! We do this by evaluating a logical expression which will return a Boolean i.e. either `True` or `False` - which btw. are syntax words in python.
Let's add some checking in our function!

```python
def convertTemperature(kelvin: float):
	if kelvin>0:
		F = (kelvin − 273.15) × 9/5 + 32
		C = kelvin + 273.15
		return F,C
	else:
		raise ValueError

freedomTemp, euroTemp = convertTemperature(70)
```

Now if you enter a kelvin value above 0 (which is evaluated using the biggger smaller sign) then the function dies it's thing. If you run `convertTemperature(-20)` it will throw an ValueError. You could also run any other code in the else block. Naturally you can generate super complex logical checks. If you know that your code will create certian errors and you wish to deal with them in a certain way you can use the try catch expression:

```python
try:
	freedomTemp, euroTemp = convertTemperature(-300)
except ValueError:
	print("The value provided for kelvin was erroneous")
	```

Overall there is a rule that says that python code should be as short as possibile because it helps with readability (there are exceptions to this rule)!
### Mini Project No. 7: Generating an element list
Create a list that contains the first elemental names that end in a n
> [!question]- Spoiler altert!
>
> ```python
> names = []
> for name in elemental_names:
> 	if name[-1] == "n":
> 		names.append(name)
> 	else: #not needed
> 		pass #not needed

The solution to this challenge would be at least 3 lines long. Two lines too long and not very readable. So I introduce to you: list comprehensions. This is a shorthand way of generating a list with a for loop. We do it first without the if clause:

```python
names = [name for name in elemental_names]
```

ok that is actually the exact same as elemental names but this is just to show you that it does the exact same as:

```python
names = []
for name in elemental_names:
	names.append(name)
```

we can now add the if-clause as well:

```python
names = [name for name in elemental_names if name[-1] == "n"]
```

This is (in my opinion) quite readable.

Now whilst python has a lot of functionalities it cannot do everything and we don't want to reinvent the wheel. For most numerical tasks there is a great python library called numpy. We need to import its functionality into our script. Importing is done by writing:

```python
import numpy
```

For instance we can calculate the cosine of $\pi$ using numpy:

```python
print(numpy.cos(numpy.pi))
```

Again you can see the `.-notation` indicating that numpy is also treated a lot like an object (even though it is a library and there are some subtle differences). We are lazy and always writing numpy is boring so we import numpy as an alias by saying:

```python
import numpy as np
```

which allows us to write:

```python
print(np.cos(np.pi))
```

we could also do:

```python
from numpy import *
```

which will import all of numpy - which is not recommended (but then we could write `print(cos(pi))`)
Numpy as a lot of useful functions. You want to generate all numbers between 0 and 42? Use `numpy.linspace`. You want to get a random integer between 0 and 1000? Use `numpy.random.randint`. Another great library is matplotlib which allows you to make plots. Matplotlib can do much more (color, drawing, etc.) so it is organized in sublibraries. You can import the relevant pyplot library like this (and please give it an alias):

```python
import matplotlib.pyplot as plt
#alternative:
from matplotlib import pyplot as plt
```

plotting is then pretty simple. Let's say we wish to plot the function from the very early beginning - something like $3+2*x$ we can do it like this:

```python
x = np.linspace(0,10,100) #creates 100 equally spaced numbers between 0 and 10
y = 3 + 2*x
plt.plot(x,y)
plt.show()#if this is not called nothing is shown
```

Numpy has a great feature called arrays that implement a lot of functionality that comes in handy with working with n-dimensional matrices.
Remeber our list of lists? We can turn that into an array and supercharge it!

```python
lol = [elemental_names,elemental_masses,elemental_densities]
lol = np.array(lol) #we typecast lol into an numpy array
```

now we can slice in multiple dimensions:

```python
print(lol[:,2]) #what is this?
print(lol[2,:]) #what is this?
```

numpy arrays do not just contain numbers!
We can also now take more complex calculations.
Let's assume we have three labs and we want to get some statistics about their temperature.

```python
lab1 = [23.1, 23.2, 23.0, 24.3, 21.1, 23.15, 23.01, 23.13] #1day=1value
lab2 = [23.0, 23.1, 29.1, 24.2, 21.0, 23.05, 22.99, 23.03]
lab3 = [23.2, 23.5, 21.1, 26.7, 20.4, 22.15, 24.01, 23.44]
```

We can put them into a dingle array:

```python
data = np.array([lab1,lab2,lab3])
```

### Mini Project No. 8: Simple statistics
Calculate the average temperature for every day and for every lab. For this you will need to go to the numpy documentation at https://numpy.org/doc/Plot and read it for the mean function. It will say axis there. Axis refers to either the per lab or the per day "axis" i.e. in which direction you calculate your statistics in your 3x8 array.  The temperature for every lab and the average temperature in a single plot. You can add a label to the x axis and y axis via `plt.xlabel("My xlabel")`.

