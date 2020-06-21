Disclaimer: This is not a substitute to the book. In fact, the book is far far better than this. You will be missing out a lot if you you will not read the book. This is just a reference for those who have read the book or for those who wants to get an overview about the contents of the book. 

If you find anything here that is hard to understand, refer to the book. Sections will be easy to find in the table of contents.

# Chapter 2 - Meaningful Names

### Use Intention-Revealing Names

Choosing good names takes time but saves more than it takes. So take care with your names and change them when you find better ones.

The name of a variable, function, or class, should answer all the big questions. Why it exists, what it does, and how it is used. If a name requires a comment, then the name does not reveal its intent.

```Int d; //elapsed time in days vs int elapsedTimeInDays```

### Avoid Disinformation

We should avoid words whose entrenched meanings vary from our intended meaning. 

Do not refer to a grouping of accounts as an ```accountList``` unless it’s actually a ```List```. The word list means something specific to programmers. 

Beware of using names that vary in small ways. Ex. ```XYZControllerForEfficientHandlingOfStrings``` and ```XYZControllerForEfficientStorageOfStrings```. The words have frightfully similar shapes. 

### Make Meaningful Distinctions

Noise words are another meaningless distinction. Imagine that you have a ```Product``` class. If you have another called ```ProductInfo``` or ```ProductData```, you have made the names different without making them mean anything different.

Noise words are redundant. The word ```variable``` should never appear in a variable name. The word ```table``` should never appear in a table name. How is ```NameString``` better than ```Name```? Would a Name ever be a floating-point number? Imaging finding one class named ```Customer``` and another named ```CustomerObject```. What should you understand as the distinction? 

### Use Pronounceable Names

If you can’t pronounce it, you can’t discuss it without sounding like an idiot. This matters because programming is a social activity. Ex.```genymdhms``` to ```generationTimestamp```.

### Use Searchable Names

Single letter names and numeric constants have a particular problem in that they are not easy to locate across a body of text. One might easily grep for ```AX_CLASSES_PER_STUDENT```, but the number ```7``` could be more troublesome.

Single-letter names can ONLY be used as a local variable inside short methods. The length of a name should correspond to the size of its scope.

### Avoid encodings

Encoded names are seldom pronounceable and are easy to mis-type.

### Hungarian Notation

Ex. ```PhoneNumber phoneString; //name not changed when type changed;```

### Member Prefixes

You also don’t need to prefix member variables with m_ anymore. Your classes and functions should be small enough that you don’t need them. 

### Interfaces and Implementations

There are sometimes a special case for encodings. For example, say you are building an ABSTRACT FACTORY for the creation of shapes. This factory will be an interface and will be implemented by a concrete class. What should you name them? ```IShapeFactory``` and ```ShapeFactory```? I prefer to leave interfaces unadorned. The preceding ```I```, so common in today’s legacy wads, is a distraction at best and too much information at worst. I don’t want my users to know that I’m handling them an interface. I just want them to know that it’s a ```Shapefactory```. So if I must encode either the interface or the implementation. I choose the implementation. Calling it ```ShapeFactoryImp```. 

### Class Names

Classes and objects should have noun or noun phrase names like ```Customer```, ```WikiPage```, ```Account```, and ```AddressParser```. Avoid words like ```Manager```, ```Processor```, ```Data```, or ```Info``` in the name of a class. A class name should not be a verb.

### Method Names

Method should have a verb or verb phrase names like ```postPayment```, ```deletePage```, or ```save```. Accessors mutators, and predicates should be named for their value and prefixed with ```get```, ```set```, and is according to the javabean standard.

When constructors are overloaded, use static factory methods with names that describe the arguments. For example,

```Complex fulcrumPoint = Complex.FromRealNumber(23.0);```

Is generally better than

```Complex fulcrumPoint = new Commplex(23.0);```

Consider enforcing their use by making the corresponding constructors private.

### Don’t Be Cute

If names are too clever, they will be memorable only to people who share the author’s sense of humor, and only as long as these people remember the joke. Choose clarity over entertainment value.

### Pick One Word per Concept

Pick one word for one abstract concept and stick with it. For instance, it’s confusing to have ```fetch```, ```retrieve```, and ```get``` as equivalent methods of different classes. 

Don’t Pun

Avoid using the same word for two purposes. Using the same term for two different ideas is essentially a pun.

If you follow the “one word per concept” rule, you could end up with many classes that have, for example, an ```add``` method. As long as the parameter lists and return values of various add methods are semantically equivalent, all is well. However one might decide to use the word ```add``` for “consistency” when he or she is not in fact adding in the same sense. Let’s say we have many classes where add will create a new value by adding or concatenating two existing values. Shall we call it ```add```? It might seem consistent but the semantics are different. So we should use a name like ```insert``` or ```append``` instead. To call the new method ```add``` would be a pun.

Our goal, as authors, is to make our code as easy as possible to understand. We want our code to be a quick skim, not an intense study. 

### Use Solution Domain Names

Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth. 

### Use Problem Domain Names

When there is no “programmer-esse” for what you’re doing, use the name from the problem domain. At least the programmer who maintains your code can ask a domain expert what it means.

### Add Meaningful Context

Imagine that you have variables named ```firstName```, ```lastName```, ```street```, ```houseNumber```, ```city```, ```state```, and ```zipcode```. Taken together it’s pretty clear that they form an address. But what if you just saw the ```state``` variable being used alone in a method? Would you automatically infer that it was part of an address? You can add context by using prefixes: ```addrFirstName```, ```addrLastName```, ```addrState```, and ```soon```. At least readers will understand that these variables are part of a larger structure. Of course, a better solution is to create a class named ```Address```. Then, even the compiler knows that the variables belong to a bigger concept.

### Don’t Add Gratuitous Context

In an imaginary application called “Gas Station Deluxe,” it is a bad idea to prefix every class with GSD. Frankly, you are working against your tools. You type G and press the completion key and are rewarded with a mile-long list of every class in the system.

Likewise, say you invented a ```MailingAddress``` class in GSD’s accounting module and you named it ```GSDAccountAddress```. Later you need a mailing address for your customer contact application. Do you use ```GSDAccountAddress```? Does it sound like the right name? Ten of 17 characters are redundant or irrelevant. Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary. 

The names ```accountAddress``` and ```customerAddress``` are fine names for instances of the class ```Address``` but could be poor names for classes. ```Address``` is a fine name for a class. 

### Final Words

The hardest thing about choosing good names is that it requires good descriptive skills and
a shared cultural background. This is a teaching issue rather than a technical, business, or management issue. As a result many people in this field don’t learn to do it very well. People are also afraid of renaming things for fear that some other developers will object. We do not share that fear and find that we are actually grateful when names change (for the better). You will probably end up surprising someone when you rename, just like you might with any other code improvement. Don’t let it stop you in your tracks. Follow some of these rules and see whether you don’t improve the readability of your code. If you are maintaining someone else’s code, use refactoring tools to help resolve these problems. It will pay off in the short term and continue to pay in the long run.


# Chapter 3 - Functions

### Small!

The first rule of functions is that they should be small. The second rule of functions is that they should be smaller than that. 

### Blocks and indenting

Functions should not be large enough to hold nested structures. Therefore, the indent level of a function should not be greater than one or two. This makes the functions easier to read and understand.

### Do one thing

Functions should do ne thing. They should do it well. They should do it only.

The problem with this statement is that it is hard to know what “one thing” is. If a function does only steps that are one level below the stated name of the function, then the function is doing one thing. After all, the reason we write functions is to decompose a larger concept into a set of steps at the next level of abstraction.

Another way to know that a function is doing more than “one thing” is if you can extract another function from it with a name that is not merely a restatement of its implementation.

### Reading Code from Top to Bottom: The Stepdown Rule

We want to be able to read the program as though it were a set of TO paragraphs, each of which is describing the current level of abstraction and referencing subsequent TO paragraphs at the next level down. 

### Use Descriptive Names

Don’t be afraid to make a name long. A long descriptive name is better than a short enigmatic name. A long descriptive name is better than a long descriptive comment. 

Don’t be afraid to spend time choosing a name. Indeed, you should try several different names and read the code with each in place.

Be consistent in your names. Use the same phrase, nouns, and verbs in the function names you choose for your modules. 

### Function Arguments

The ideal number of arguments for a function is zero (niladic). Next comes one (monadic), followed closely by two (dyadic). Three arguments (triadic) should be avoided where possible. More than three (polyadic) requires very special justification and then shouldn’t be used anyway.

Arguments are hard. They take a lot of conceptual power. Arguments are even harder from a testing point of view. Imagine the difficulty of the difficulty of writing all the test cases to ensure that all the various combinations of arguments work properly. 

Output arguments are harder to understand than input arguments. When we read a function, we are used to the idea of information going into the function through arguments and out through the return value. We don’t usually expect information to be going out through the arguments. So output arguments often cause us to do a double-take.

It will be worth it to read all the contents of this section in the book. So please do so.

### Have no side effects

Side effects are lies. Your function promises to do one thing, but it also does other hidden things. 

### Output Arguments

In general output arguments should be avoided. If your function must change the state
of something, have it change the state of its owning object.

### Command Query Separation

Functions should either do something or answer something, but not both. Either your function should change the state of an object, or it should return some information about that object. Doing both often leads to confusion.

### Prefer Exceptions to Returning Error Codes

Returning error codes from command functions is a subtle violation of command query separation. It promotes commands being used as expressions in the predicates of if statements. 

### Extract Try/Catch Blocks

```Try/catch``` blocks are ugly in their own right. They confuse the structure of the code and mix error processing with normal processing. So it is better to extract the bodies of the try and catch blocks out into functions of their own.

### Error Handling Is One Thing

Functions should do one thing. Error handling is one thing. Thus, a function that handles errors should do nothing else.

### Structured Programming

Every function and every block within a function should have one entry and one exit. Following these rules means that there should only be one return statement in a function, no break or continue statements in a loop, and never, ever, any goto statements.


