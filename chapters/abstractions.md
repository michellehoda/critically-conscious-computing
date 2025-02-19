=
@keyIdeas
* Abstraction is a strategy for reducing the complexity of computer programs by hiding information and detail.
* Encapsulation is a strategy for reducing the complexity of computer programs by organizing code, often by making some information visible, and other information hidden.
* Functions and classes are abstraction and encapsulation mechanisms that give code a name so that it may be reused.
* APIs are collections of abstractions that make it easier to create software by reusing existing functionality.
* All abstractions hide detail, which risks erasing diversity, nuance, and context, and making it harder to identify when code being reused encodes bias, and harder to change the behavior of software.
* Teaching abstractions can focus on use, design, or critique, all three having their own challenges .
=

Throughout this book, we have characterized computers as relatively unintelligent machines that mindlessly execute low-level instructions. Justice, in this view, is woven through the particular instructions that software developers choose and the particular data that those instructions process. But throughout these discussions, we’ve been able to critique these algorithmic choices directly because the instructions that developers choose in our examples have been *transparent*: we see every line of code in a program and can analyze each line for their computational meaning and social implications.

Modern software, however, is anything but transparent. In fact, by design, software hides information. For example, when we launch a program on a smartphone -- an email client or web browser, let’s say -- we don’t have to think about the hundreds of thousands, or perhaps millions of lines of code that make it work or how they work. We don’t even have to think about the smaller computer program that an operating system runs to launch the program. We only have to think of the icon we want and use our finger, nose, or other capacitive device to press it. The rest of the details are hidden away, and we only deal with the *interface* to that functionality -- in this example, an icon that responds to our touch.

The same is true for when writing code. The developers that makes your favorite web browser, for example, has not read the millions of lines of code that make it work. And many of the lines aren't even available to them, as they come packaged and pre-compiled as libraries, frameworks, and application programming interfaces. Increasingly, programming is therefore defined by _reusing_ the decades of programming labor that has come before, and assembling it together with a small amount of new code.

The ability to reuse the work of others is what has enabled such incredible feats of computation, from the internet's billions of interconnected computers, to the ability to get an answer from a search engine in a fraction of a second. However, reuse also comes with tradeoffs, since most developers do not know how reused code works or what assumptions it makes. In this chapter, we examine a foundational idea behind these reuse tradeoffs -- abstraction -- and examine the many ways that this idea is manifested in programming languages (e.g., functions, objects, APIs, and more). We then consider the many social implications of abstraction, and how to develop youth critical consciousness of these implications.

|Chapter14_Figure01_Interface.png|Several people standing around a cube, staring at facades, but inside is complex machinery.|We can't see inside, for better and worse.|@jessie|<

# Abstraction

One of the central ideas behind reuse is that of ~abstraction~abstraction<kramer07>. This is the idea of identifying which details are most essential in representing something, and using those ideas to represent the idea, discarding other details, even at the expense of capturing some exceptions. Most of us are quite familiar with abstraction, because it's central to natural language. For example, we use the word _chair_ to represent physical objects that have three or more legs and a sitting surface. This particular definition of a chair isn't perfect -- for example, does a chair with two legs that self balances count as a chair? -- but the word and its fuzzy boundaries is still helpful, because we can just use a single word to represent a shared idea, rather than writing a long description or giving numerous examples of chairs. Words, therefore, are abstractions that make communication more efficient, at the expense of exceptions and nuance.{Sometimes, the erasure of nuance behind words leads to _stereotypes_, which leads words to connote some assumptions about the ideas it refers to. For example, _programmers_ might lead people to imagine White and Asian men. Some stereotypes are even given words of their own, such as _brogrammers_ (male programmers who engage in macho behaviors) and _cowboy coders_ (male programmers who write code recklessly and without regard to collaborators or organizational goals).}

Just as natural language uses abstraction through words to make communication more efficient, learnable, and convenient, software uses abstraction to make programming and other forms of computing more efficient, learnable, and convenient. For example:

* Computer engineers, who create computer components like CPUs, control boards, memory, and other hardware, do not have to understand the low-level physics of electricity or even a transistor, because those details have been hidden. Instead, they can just think of transistors as abstract binary switches that can be turned on and off. The _transistor_ abstraction hides the nuance of electricity and physics.

* Operating system developers, who creating programs that reliably execute the programs that a user wants to be run, do not have to understand the details of how computer hardware uses transistors, because those details have been abstracted away into ideas such as CPUs, memory, and storage, as we detailed in @operating. These computer architecture abstractions hide the nuance of the physicality of computer hardware.

* Software developers who write applications do not have to understand how an operating system works, because its details have been abstracted away behind concepts like programming languages, data structures, and algorithms. These programming abstractions hide the nuances of operating systems, computer hardware, and physics.

* Software users do not have to understand the details of how the programs are implemented in code, because these details have been abstracted away behind concepts like windows, buttons, taps, and clicks.

Just as with words, abstractions in computer science have tradeoffs: because software users don't have to understand how code words, when applications break, they might struggle to understand how to fix it. The same is true of software developers trying to troubleshoot an operating system, operating system developers trying to troubleshoot computer hardware, and even computer engineers trying to troubleshoot electrical engineering issues with computer hardware components.

The history of computer science is thus one of great efforts to invent ever more complex and powerful abilities, and then abstract away that complexity behind some simpler concept, idea, or interface. This is quite similar to the history of abstraction in other industries: for example, car drivers don't need to understand car engines until they break; most car mechanics don't have to understand the physics of combustion; and mechanical engineers of car engines don't have to understand the atomic physics or chemistry of combustion. At each of these levels, abstraction is what enables people to reuse complex systems and ideas with minimal understanding of the details.

|Chapter14_Figure02_InputOutput.png|A woman sitting on a black box cross-legged with a laptop, and tendrils of data moving through the box, coming out as a signal on the other side.|How things go in and stuff comes out.|@jessie|>

# Abstractions in code

In computer science, abstraction was not always strictly necessary. For example, people who used the first mainframe computers were software users (executing programs), they were software developers (writing the programs to execute), they were computer operators (managing the computer’s resources), and they were computer engineers (removing insects from vacuum tubes that prevented the computer from functioning). The computers and programs they were writing were simple enough that one person, or perhaps a small group of people, could comprehend the entire system, and work at all of these different levels of detail. There was little benefit in hiding these details when individuals or small teams needed to manage and understand all of them.

Today’s software, however, is so complex that abstraction is essential. Consider the Microsoft Windows operating system, for example: it is composed of tens of millions of lines of code, maintained by tens of thousands of developers, all of whom only understand perhaps less than a hundred thousand lines of that code. Abstraction is what enables one developer at Microsoft to understand just a small part of the system in detail, and the rest of the system in the abstract. Computer science has invented several ways of using abstraction in code to make this possible.

## Functions

There are many features in programming languages that support abstraction, but perhaps the most central and ubiquitous is that of the ~function~function. You might recognize this word from mathematics, and that’s because it is a nearly identical concept. Consider, for example, the kinds of mathematical functions that appear in math education in algebra and plots. In these settings, we will see functions like this:

`
y = 5x + 2
`A function for a line with slope 5 and intercept 2.

You might recognize that as a function for a line with slope `5` and y-intercept `2`. In mathematics, students learn about functions in this spatial sense, imagining many possible values of `x`, the ways that those values are mapped onto a `y`-value via a function, and then how those `x` and `y` pairs might be visualized on a plot. In this way, functions are a mapping between inputs and outputs, where everyone input corresponds to some possible output. In the example above, when `x` is `5`, it maps to the `y` value of `5 x 5 + 2 = 27`; when it is `0`, it maps to `5 x 0 + 2 = 2`.

Computer science embraced mathematical functions as a way of representing computation, just with a different notation. For example, here is the same function above, but in Python:

`python
def y(x):
  return 5 * x + 2
`The same line as above.

Just as with the formula above, this function takes any value `x`python and returns it times `5`python, plus `2`python. Computing, however, expanded the notion of a function to also include *names*, to help give more meaningful, human readable descriptions of what input is being provided and what output is being computed. The function above allows a programmer to call a function by name; for example, the Python code `y(3)`python means "_call the function y with the value 3, execute it, and then obtain the value it returns_". In this case, this would mean finding the function named `y`python, setting a variable `x`python to the value provided, `3`python, getting the value of `x`python and multiplying it by `5`python, adding `2`python to the result, and then returning the value to whatever part of the program that called the function `y`python. This process is therefore unlike functions in math in many ways: we can give functions names that are more than just a single letter; we can use functions anywhere in a program where they are defined, and we can reuse functions throughout a program, to avoid having to write the same code multiple times. Functions are abstractions because they allow us to refer to some specific computation without having to worry about how that computation is implemented.

Functions in programs can have more than one input. We call each of these named inputs *arguments*{This word too was borrowed from mathematics, which borrowed it from astronomy<bello13>, where it referred to angles between Earth and other planets, and was meant to mean "that which elucidates something else."}. For example, consider this Python function, which has to arguments:

`python
def isEligibleToVote(age, citizenship):
    return age >= 18 and citizenship == "US"
`

These two arguments, `age`python and `citizenship`python, are used to compute a Boolean `True`python or `False`python value as to whether someone is eligible to vote. We would call it by writing the Python code `eligibleToVote(12, "Canada")`python, which would return the value `False`python. While this might look quite different from the mathematical function above, we could write it in a more mathematical syntax:

The inputs given to a function’s arguments can come from anywhere, but it’s important to note that it is the _values_ that are passed to functions, not the containers that store those values. For example, consider this program:

`python!
def isEligibleToVote(age, citizenship):
    return age >= 18 and citizenship == "US"
age = 20
citizenship = "Pakistan"
print(isEligibleToVote(age, citizenship))
`

In this program, when the function `eligibleToVote` is ~called~call, the values stored in variables `age` and `citizenship` are passed, not the variables themselves. This can be confusing, because in our example above, the variables in the function have the same names, `age` and `citizenship`. They are nevertheless entirely different containers: the variables in the program calling the function can be changed without affecting the behavior of the function. This is because functions define their own ~namespace~namespace, which is the concept of particular parts of a program (every line of indented code below a function declaration in Python, for example), have their own set of function and variable names, which cannot be accessed or modified outside the function. In Python, if variables are declared inside a function that happen to be the same as names outside the function, the names inside the function have precedence.

This program therefore produces the same result:

`python!
def isEligibleToVote(age, citizenship):
    return age >= 18 and citizenship == "US"
a = 20
c = "Pakistan"
print(isEligibleToVote(a, c))
`

One powerful aspect of functions is that they can be combined with other functions and logic to make even more complex functions that themselves abstract away complexity. For example, a progressive political campaign could use `eligibleToVote`python to automate the selection of who to call to encourage to vote:

`python
def selectOutreachList(people):
    outreachList = []
    for person in people:
        if (isEligibleToVote(person.age, person.citizenship) and 
            person.politics == "progressive"):
            outreachList.add(person)
    return outreachList
`

In this example, the person who wrote the `selectOutreachList`python function does not need to know how voting eligibility is determined; they can just reuse that function and focus on their own program logic. And anyone that uses `selectOutreachList` doesn't have to know the logic of who is selected and why, or voting eligibility; they can just call the function and get a list of people to call, text, or visit.

Some aspects of functions are surprising in their beauty. For example, imagine in the example above that every person data structure came with a list of associated people stored in a field called `connections`, such as friends and family, and we wanted to build an outreach list based on a social network of connected people. How could we use a function to scan this network of connections for eligible people? Functions allow us to do something called ~recursion~recursion, where a function can even call _itself_ in order to compute something. For example:

`python
def buildOutreachListFor(person, selected, checked):
    # If we already checked, no need to check again
    if person in checked:
      return
    # Remember that we checked this person
    else:
      checked.add(person)
    # If they're eligible, add them to the list
    if isEligibleToVote(person.age, person.citizenship)
      selected.add(person)
    # Recursively check all of their connections
    for connection in person.connections:
      buildOutreachListFor(connection, selected, checked)

outreachList = []
buildOutreachList(amy, outreachList, [])
`

This function does three things:

* The first is the most important in a recursive function: it checks to see if the given `person`python has already been checked, using a list of people that keeps track of who is already been checked; if the person has already been checked, then it returns, stopping this particular execution of the function, and if they have not, then the person is added to the `checked`python list so that future calls remember that they have been checked. In recursion, this is what is called a *base case*: the condition in which a function should _not_ call itself. This check prevents the function from calling itself over and over without ever stopping.

* The second step is the same as before, just checking to see if the person is eligible, and if so, adding them to a list of people selected for outreach.

* The third step is the _recursive_ step: the function loops through every one of the person's connection, and calls _itself_, to do the same process for the connection. This is often the most confusing part of recursion, because it's hard to imagine a program that executes itself ever stopping. That's where the *base case* above comes in: whenever the function starts inspecting a person it has already inspected, it will stop. Otherwise, it will check every connection in the network, finding all eligible voters and adding them to the list `selected`python.

These examples make the benefits of functions clear: someone can write a function that has some complex, nuanced logic, expose only details about its inputs and outputs, and then other people can call the function without having to know much of anything about how it is implemented. Functions are therefore the abstraction mechanism underlying most of the magical things that computers have been taught to do. Without ever having to understand how they are implemented, functions allow us to:

`python
sendEmail(message)
classifyFace(selfie)
driveCar(currentImageOfRoad)
detectCancer(medicalImage)
`

## Classes

While functions are the most ubiquitous form of abstraction in programming, as the software we built in society became more complex, their power hide complexity was not great enough to deal with the scale of some programs. Consider Google Search, for example; it is likely built from hundreds of thousands of functions, written by thousands of different people, each responsible for ensuring that the functions they wrote are working correctly and interoperating with other functions correctly. Imagine a computer program, stored in a single document, with hundreds of thousands of functions, and how much of a disorganized mess that could become: how would a new employee learn how Google Search is built, other than by just reading all of the functions?

This problem led to the invention of ~object orientation~oo. As we discussed in the @languages chapter, this was the idea that code and data might be encapsulated into something called an object<holmevik94>, which is nothing more than a container for storing related code and data to keep it organized. For example, continuing our voting example above, imagine we defined an object that represent a voter:

`python
class Voter:
  def __init__(self, age, citizenship):
    self.age = age
    self.citizenship = citizenship
    self.vote = None

  def isEligibleToVote():
     return self.age >= 18 and self.citizenship == "US"

  def recordVote(candidate):
     self.vote = candidate
`A `Voter` class, which encapsulates data and functions related a voter.

In object-orientated terminology, the code above represents a ~class~class, which represents a kind of template for the data and functions an object will contain. This template has three functions, which in object oriented programming terminology, are called ~methods~method when they are part of a class: one to initialize an object of this type with some values (with the strange Python name of `\_\_init\_\_`python), one that is from our earlier example that determines voting eligibility, but using the values stored in the voter object (`isEligibleToVote`python), and another function that stores the candidate the voter voted for (`recordVote`python). The class also has three variables, which are called ~fields~field when they are part of a class: `age`python, `citizenship`python, and some text string stored in vote to record which candidate the voter voted for. By writing the class above, we’ve given a blueprint to the computer about what kinds of data and functionality each voter object has. And we could have included any methods and fields that we wanted; Python has no expectations about what methods or fields a class has, what they are named, or what they do.

But: we have not yet created a `Voter`python object. To do that, we have to create an object using the class. In Python, that is as simple as:

`python
amy = Voter(41, "US")
print(amy.isEligibleVoter())
`

That code tells Python to create a new `Voter`python object using the `Voter`python class as a template, and call its `\_\_init\_\_`python function to initialize it’s fields. The result would be what object-oriented programming languages call an instance of class Voter. This distinction is key: the blueprint for creating a voter is not the same as an ~instance~instance of class `Voter`python, just like the blueprint for creating a house is not the same as an actual house. If we wanted to create objects to represent millions of other voters, we would need to use the same syntax above to instantiate millions of additional `Voter`python objects; each instance would share the same methods, but have their own unique value stored in their fields. (The loops we discussed in @control might be helpful there, rather than writing a line of code for each voter). And yet, no matter how many instances of `Voter`python we create, there would still only be one `Voter`python class.

With these ideas of classes, methods, fields, instances, we have the power to organize larger programs. For example, returning to our Google Search example, we could make some classes that were responsible for analyzing user’s search terms, other classes that were responsible for indexing documents on the web, and other classes that were still responsible for retrieving documents based on a search query. By using classes to organize code and data, an individual Google engineer wouldn’t have to read a single file with hundreds of thousands of functions; instead, they might just learn how one or two classes are built, and just use the methods of other classes to implement new search functionality. 

Some programming languages go beyond the basic ideas of classes, methods, fields, and instances above, adding more powerful features. For example, one common idea is the notion of ~inheritance~inheritance, which is the idea of writing new classes that "inherit" the functionality of other classes, but add new data and functionality. If we continue with the voter example above, for example, one might imagine special types of voters that not only have an age, citizenship, and vote, but also other privileges. For example, in the United States U.S Presidential Elections, some voters are also electoral college voters, which vote for presidential candidates based on the votes of the people they represent. We could create a *subclass* of Voter, which inherits all of the fields and methods of Voter, but adds additional data and functionality:

`python
class Elector(Voter):
  def __init__(self, age, citizenship, state):
    self.state = state
    self.electoralVote = None
    Voter.__init__(self, age, citizenship)

  def recordElectoralVote(candidate):
    self.electoralVote = candidate
`

This subclass `Elector`python has all of the fields and methods of `Voter`python that we defined above, but two additional fields -- `state`python and `electoralVote`python -- and one additional method -- `recordElectoralVote`python. We can treat an instance of `Elector`python like an instance `Voter`python when calling functions on it, calling `isEligibleToVote`python, but only instances of `Elector`python can use the additional functionality defined in the `Elector`python class. All of this extra effort to define subclasses through inheritance is just another way avoid rewriting code: by inheriting from `Voter`python rather than creating an entirely different class for `Elector`python, `Elector`python can reuse `Voter`python’s code.

Object orientation, as an approach to abstraction, leverages two related design principles that are quite common in computer science. The first is ~encapsulation~encapsulation<parnas85>, which is the idea of combining together conceptually-related details into some single structure, making it easier to find related code and keeping some degree of organization between large amounts of code. For example, bundling together all of the functionality related to representing voters, rather than just having a bunch of variables and functions loosely connected, is an example of encapsulation. A second strategy is ~information hiding~infohiding<parnas72>, which is the idea of purposefully hiding implementation details, to prevent people from reusing code in a way that would make it hard to change later. For example, if someone called `isEligibleVoter`python in our examples above, and the person who wrote that function decided to change its behavior, the program that calls the function wouldn't need to change.

## APIs

After functions and object-orientation became common, other abstraction mechanisms emerged to organize even larger collections of reusable code. We broadly refer to these now as ~application programming interfaces~api (APIs), though many other related names are used, such as _libraries_, _frameworks_, and _packages_. APIs are collections of functions and data structures written by one group of people for use by other groups of people to write programs<bloch06>. Rather than having to write functions oneself to do the many complex computations to build modern software, one can simply use APIs, which build upon decades of labor by software developers to implement algorithms for various tasks. One person can write a function to sort numbers, and millions can reuse it without ever knowing how it is built. In fact, none of the software that we have built today, including our devices, their operating systems, the numerous software applications we use, and the entirety of the internet, would be possible without APIs and the many abstraction mechanisms used to create them. Without them, each person writing a program would have to start from scratch, without the benefit of 60 years of programming labor to build upon.

Whereas learning programming languages involves learning the syntactic and semantic rules behind a language, learning an API is a fundamentally different learning task<thayer21>. Because APIs are collections of functions that purposefully hide their implementation from their users, learning an API requires understanding the different things. For example, consider facial recognition algorithms, an increasingly prevalent kind of computation that takes an image as input, and produces a name as output. Here is how one might call a hypothetical facial recognition API we'll call `facelib`python in Python:

`python
import facelib

classifyFace(loadImage("myFace.png"))
`

This simple hypothetical example uses the `import`python statement to load in all of the named functions and data structures in `facelib`python into this program when executed, including `classifyFace` and `loadImage`. This is encapsulation at scale: the single word `facelib`python could represent dozens, hundreds, or even thousands of functions, classes, and other encapsulated functionality and data structures.

But how does what understand how any of these functions work? For example, what is the structure of the image data that is passed in to `classifyFace`? What happens if the image contains multiple faces? What happens if the image does not contain faces at all? What if the image is not well lit? What if the image contains faces, but of mammals, but not humans? What if the person in the image is a Black Woman, which most facial recognition algorithms are demonstrably worse at classifying<buolamwini18>? Because the code of this API may not be available for inspection, or perhaps too complex to comprehend, using APIs requires different knowledge<thayer21>:

* *Domain knowledge*. This includes both knowledge about the domain in the world that the API is modeling, but also how it is modeling it. For example, for a face recognition API, what is an image? What does it mean for an image to "contain" things? What counts as a "face"? What words does the API use to represent ideas like images, faces, and names? Without understanding these ideas, and how the API represents them, learners often cannot find documentation about the API, understand the examples it gives, or make predictions about other aspects of its behavior.

* *Execution semantics*. This includes knowledge about how a function in an API behaves: what types of inputs it will tolerate, what types of errors it might produce, how it maps inputs to outputs, how long that might take, how accurate the results might be, and so on. In the case of face recognition, this might be semantics like classification only working accurately when there is one well lit White face directly facing the camera, and when the person whose face appears in a photo is in a private database that maps faces to names. Without understanding these properties of a function’s behavior, learners will struggle to write programs using the API that do precisely what they want, and struggle to debug programs because they can’t explain or predict the behavior of a function.

* *Usage patterns*. APIs are often written in ways that require functions to be used in particular ways. For example, to call one function, one must call other functions first, or to achieve a particular complex behavior, multiple functions in the API might need to be combined. Some behaviors might not even be possible with an API. For example, to recognize a face accurately with a face recognition API, it might be necessary to first preprocess an image to increase its brightness and contrast, and crop it so that the face is in the center of the image. Without knowing these patterns of use, learners may not be able to translate the behavior they want their program to have into a program that uses an API’s functions.

Unfortunately, most APIs offer poor documentation of all of this knowledge, leaving many learners to have to find resources online, guess, or even read all of an APIs source code, creating challenges to learning and software engineering. And because most modern programming involves the extensive use of APIs to create interesting, useful software, much of the experience of creating software is searching for information online, reading documentation and tutorials, or taking classes that teach particular APIs to learn the knowledge above. This means that anyone that creates software -- professional software developers, hobbyists, students learning CS in classes -- will necessarily be engaging in informal learning about API abstractions, usually without well-designed instructional materials to support them. Thus, while removing details through abstraction can make complex things _easier_ to use, it does not make them _easy_ to use.

|Chapter14_Figure03_Guarded.png|Several people sitting on and around a safe labeled "Google", unable to get in.|The secrets might warp the world.|@jessie|<

# Social tradeoffs of abstraction

While abstraction is necessary for creating modern software of ever greater complexity, it poses inescapable tradeoffs when software is deployed into society. Consider, for example, the mechanisms of injustice we discussed in the @justice chapter.

One of the ways that algorithms amplify injustice is *centralizing* decision making. Functions, classes, and APIs are all tools for centralizing decisions. For example, consider the `eligibleToVote`python function and method above. If everyone in the world wrote programs about voter eligibility that used that function to decide eligibility, it would bestow great power to the people who control the logic of that function. And, in fact, that’s exactly what many U.S. states do: they have computer programs that encode the law and decide whose votes are eligible to count in an election based on logic. Who writes those programs? Should every city, county, and state write their own programs to automate this logic? Should they be trusted to write it correctly? What rights should the public have to inspect the logic of a function? What power does the public have to _change_ the logic of a function? In most countries, the public has _no_ rights to any of these things and no law to regulate how code is used to centralize power.

This brings us to *privatization* of decision making. Much of the voting in the U.S. now happens on electronic voting machines that are designed, implemented, and maintained by private companies, who hold intellectual property rights over their source code. Who are the software developers writing the code that assesses voter eligibility and counts votes? Can eligible voters inspect the company’s code to verify that they are determining eligibility correctly according to law? Is there any way to guarantee that the code on the physical machine being used to count votes is the same code that is made available during an audit? The whole point of encapsulating that logic in a function written by the private company is to free others from having to understand it. Therefore, encapsulation by private companies is a transfer of power from the transparent, public, human processes, to opaque, private, algorithmic processes. Without regulations that set particular requirements on making the implementation of functions available for inspection, we are forced to trust private companies to accurately implement the law. Again, in most countries, there are no laws granting the public, or even governments, any rights to inspect the source code of private companies, even in matters at the heart of democracy.

At the same time, implementing voting eligibility as a function is a form of *automation*. Automation that is encapsulated means that not only are the decisions made by a computer program centralized and potentially secret, but they are also no longer done by a person. Who should we trust to make judgments about someone’s age and citizenship? Our non-digital processes generally involve reviewing paper documents such as driver’s licenses, passports, and birth certificates, all of which are carefully maintained as paper records and processed by people, who are capable of identifying and notifying errors, and making interpretations in ambiguous cases. For example, the first author changed her first name on her birth certificate, and made a mistake on the form, but the friendly clerk noted the error, called the first author, and ensured it was correct. Had an algorithm processed the change, it could have resulted in the first author losing proof of citizenship and therefore voting eligibility. Abstraction is therefore a vessel for hiding the social consequences of automation behind innocuous names like `isEligibleToVote`python.

In the worst case, functions might implement explicitly unjust, discriminatory ideas, and because of abstraction, encapsulation, and information hiding, do that without anyone ever knowing. Imagine, for example, a function call like this:

`python
eligibleToVote(person)
`

While that might not look problematic at all, that function's implementation might be:

`python
def eligibleToVote(person):
    return person.race == "White" and person.disability is None
`

This explicitly racist, ableist logic is encapsulated away in a function that potentially no one would ever see, aside from the software developer who wrote it.

Perhaps the biggest challenge with encapsulation is that it is so powerful and necessary for creating software that we often cannot avoid it. Imagine, for example, that the public decided that the voting machines created by [Dominion|https://www.dominionvoting.com] could not be trusted. Because they are built upon so many layers of encapsulated functions, the only recourse to creating a public voting system platform would be to recreate it in its entirety -- the hardware, the software, and the maintenance workflows. It is far easier for a local government to delegate this work to a private company -- relying on its encapsulation of voting logic -- than it is for a government to recreate its own voting platforms. Dominion knows this, and uses this leverage to maintain control over its monopoly on electronic voting. And yet, most governments impose no requirements on the private organizations to which they delegate democratic processes.

While we have explicitly examined abstraction in the context of voting, and used hypothetical examples throughout, none of this is hypothetical. Racist logic like the example above is encoded in recidivism predictions, loan eligibility applications, Google search, and countless other computer programs<oneil16, noble18,benjamin19>, often without any ability for the public to audit their logic, or even awareness such programs exist. But this is not inevitable: abstraction doesn't _need_ to be used in these ways, as much as it is necessary for creating ever more sophisticated software. But this would requiring that abstraction, just like all other aspects of computer science, are inevitably vessels for political ideas, and often political in and of themselves. 

|Chapter14_Figure04_Insides.png|Several students standing around a black box on a table trying to find a way inside.|Students have to take black boxes apart to understand them.|@jessie|

# Teaching abstraction

While teaching computer science used to be strictly about learning programming languages, algorithms, and data structures, the abundance of reusable code in the world, and the inevitable reliance of the world on reusing it to create software, means that understanding computing is also about understanding abstraction and how it facilitates reuse. Within this, there are countless things that students might learn: what functions and APIs are, how they are created, how to select and use them, and how to reason critically about their behavior in technical terms. That is a lot to learn, especially in addition to everything else we've discussed thus far in the book. and not something that can be quickly or easily taught. 

However, as the last section illustrated, understanding abstraction technically isn’t the only way to understand them: students might also learn how to think about abstraction from critical, social, and political perspectives as well, examining them from the perspective of power and oppression. One of a teacher’s central roles is in deciding which of these many distinct skills and concepts are worth teaching, depending on who their students are, what standards they might want to teach, and what values they have, and reconciling their priorities, their students priorities, and the priorities imposed by state standards and parental politics.

In this section, we'll examine some of the more strictly technical approaches to teach abstraction, and then  with an unit sketch that focuses on critical perspectives on functions.

## Teaching abstraction use

At the simplest level, teachers can teach the use of functions, either ones that are built into a programming language or as part of an API. When teaching programming languages, this is often unavoidable. Even the simplest programs in some languages involve function and API use. For example, this Python program is just a single function call:

`python
print("Hello, the print function printed me.")
`

If one started teaching Python with this program, students would immediately have to know the syntax of function calls: a function names followed by parentheses, with a list of comma separated expressions to pass to the function for execution. And to know what a function call is, they have to know what functions are, at least to some extent, to reason about what the program is doing. At least with Python, then, doing anything interesting, such as printing output to a screen, requires functions.

Similarly, in languages like [Scratch|https://scratch.mit.edu], one of the simplest programs that causes interesting output is to write is:

|Chapter14_Scratch.jpg|A Scratch program that says "when [green flag]" is clicked, say "Hello World!"|The simplest Scratch program, which makes a character speech bubble display text when the program is run.|[Wikimedia|https://commons.wikimedia.org/wiki/File:Scratch_Hello_World.png]|<

This example uses `say`scratch function. It's not really presented as a function -- the drag and drop nature of its editor portrays it as a kind of natural language sentence or web form -- but it is still a function call, with a name (`say`scratch) and one argument (the string `Hello World!`scratch). Therefore, even languages intended to reduce the burden of language learning necessitates teaching at least a small amount about functions.

Methods for teaching function, object, and API use can be as simple as giving students practice conforming to the syntax of function calls, trying different inputs to understand their effects in a function call, and using functions in combination with other programming language constructs to achieve more complex behaviors. These methods can help develop knowledge of programming language syntax and semantics, while providing some shallow knowledge of what functions are and how they can be used<lee14>.

To develop more robust knowledge of an API, however, teachers need to cover the specific domain concepts, execution semantics, and design patterns of an API in more detail<thayer21>. For example, teaching data science skills in a science classroom might require using the popular [Pandas API|https://pandas.pydata.org/docs/reference/index.html] for data analysis. This API has a range of complex data structures and functions. Students have to know Python before they can feasibly use Pandas, but knowing Python is insufficient. Students also have to learn the general concept of [tabular data|https://en.wikipedia.org/wiki/Table_(information)], and how Pandas represents data tables with a data structure called [DataFrames|https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html], and that DataFrames have many functions that can automatically analyze, filter, and restructure data to support statistical analysis. The most common ways of learning all of these details are to read documentation -- either official documentation, or community generated documentation on sites like [StackOverflow|https://stackoverflow.com/questions/tagged/pandas]. But such documentation, while intended for learning, is often not written using best practices of instructional design, and so it can pose significant difficulties to even professional software developers<robillard11>. Students, therefore, can have even greater difficulties, as they are building upon more brittle understandings of programming languages. This often results in students being confused, and copying code that they do not understand, introducing defects that are difficult to debug without further learning. Therefore, teachers will be more successful by providing tailored direct instruction and practice on API concepts that accounts for their specific students’ prior knowledge.

Another challenge with teaching APIs, especially in project-based learning, is that no API can support every imaginable thing a student might want to make. Professional software developers might take weeks assessing the feasibility of an API for a particular program behavior, only to find that something is not possible, or is only partially possible<ko11>. Asking students to do such feasibility assessment work is risky, as they may go down similar fruitless paths. The expressive power of an API to make many things possible is also a great risk to teaching, as students may find themselves needing to learn ideas that no one in the class, including the teacher, knows anything about. 

None of this is meant to deter teaching about functions and APIs. Rather, it's to highlight that for students to thrive in reusing code, teachers need to carefully curate and constrain what types of difficulties students might encounter. Using platforms like Scratch that intentionally constrain potential challenges is one approach; teachers might also use more general platforms but set clear expectations with students that some things might not be easy or even possible, and that learning new concepts, language features, and APIs is an authentic part of programming.

## Teaching abstraction design

Whereas teaching function and API _use_ involves one set of challenges, designing _new_ abstractions, such as functions or classes, is a different skill entirely.

One well established method for teaching function design comes from the book _How to Design Programs_<felleisen18>. This book starts from a "pure" view of functions, where, given some inputs, a function performs some analysis or operations on the inputs to determine the output. (Impure functions might have other side effects, as in the examples in the previous section of printing something output in Python or changing a character’s costume in Scratch). The book recommends teaching this design recipe:

1. Identify what information must be represented and how it is represented in a programming language.
2. Write the function header, determining the inputs and their data types, and writing a description of what the function should compute.
3. Work through examples of what the function should compute with specific values.
4. Outline an algorithm that mirrors the examples of what the function should compute.
5. Fill in the outline, using the function’s purpose and the data types defined.
6. Test the function, to ensure that it computes what is intended for all possible inputs, and iterate on all of the previous steps as necessary.

Teaching this high level process is a form of scaffolding that can help students structure their problem solving process. Students often struggle to self-regulate during such structured problem solving, often deviating from the sequence, or struggling to independently perform a particular aspect of the process<ko19>. Teachers can play the role of coaching and support during these steps, offering direct instruction to address gaps in prior knowledge, and reinforcing problem solving steps, which can develop their programming self-efficacy and increase their independence<loksa16>. Such facilitation can feel like helping students sculpt a sculpture, one step at a time, converging toward their final vision.

## Unit sketch: Black box admissions

Whereas the previous two sections describe methods for developing programming skill using functions, there are many reasons why programming might not be the goal. Students in a social studies class might be studying capitalism, and one might teach them about how functions can be an instrument of profit. Students in a civics class might examine how functions are an instrument of power. Students in a science class might examine how functions are used to analyze data to make scientific judgments. Moreover, teaching abstractions as apolitical has consequences: rather than connecting students with the rich history of code that others have written over the past decades, abstractions and their goal of encapsulate and hide details, can create a a kind of "wall" between students the ideas contained in them<malazita19>. This tradeoff, especially in the context of integrating CS into other disciplines, may actually _harm_ literacy, as it eliminates opportunities to critically examine the assumptions and models embedded in abstractions. All of these purposes demand a different literacy toward functions, one that examines their role in society, rather than harnessing them as tools for creativity.

In this unit sketch, we demonstrate one method for teaching this critical examination. The unit uses a function of particular interest to many secondary students, especially high school students: the functions used to determine college admissions. This lesson examines an approximation of Texas’s college admissions process, which by state law uses a ["top 10%" rule|https://en.wikipedia.org/wiki/Texas_House_Bill_588] to automatically admit students who are in the top 10% of their class by GPA, Texas residents, and graduating from a public or private school in Texas, or a school in Texas operated by the Department of Defense. All other students undergo a holistic review of other factors. The key twist in this lesson is that students begin only being able to _use_ the function, and not see it’s implementation. The lesson then makes the logic transparent, and moves into more critical perspectives on unintended consequences of this function, and how it might be made more equitable.

The learning objectives are as follows:

1. Students will be able to call a function with varying inputs.
2. Students will be able to reverse engineer the possible behavior of a function.
3. Students will be able to critically examine the tradeoffs of keeping a function private.
4. Students will understand the relationship between transparency and perceptions of fairness.
5. The first lesson begins by setting the stage about college, and introducing the admissions function.

=
### Session 1: College admissions

* Describe college, including what is, how it varies, and the tradeoffs in going to it.

* Explain that in many countries in the world, anyone can go to college for free, but that in the United States, everyone pays, and must apply and be admitted.

* Explain that this requires the creation of a function, in which colleges are given several inputs -- transcripts, essays, SAT scores, and more -- and they compute one of three outputs: admit or deny. (One might also explain wait lists).

* Explain functions as a mapping from input to output.

* Given an example of a function that reflects the admissions decisions in Europe, such as the function below, which returns `True`python if a student is a citizen:

`python
def admit(citizen):
  return citizen 
`

* Test the two possible inputs and show the outputs.


* Give an example of a function that reflects an admissions lottery, such as the function below, which flips a coin, admitting half of the students who apply, independent of who they are:

`python!
import random
def admit():
  return random.random() < 0.5
print(admit())
print(admit())
print(admit())
`

* Run the function several times to show its behavior.

* Solicit alternative admissions logic from the students, and live code those, showing the definition of several possible admissions functions.
=

This first session establishes the domain of admissions and the concept of functions, given students a sense of how inputs are mapped to outputs. Students should leave this session wondering about college, but also wondering about how college admissions decisions are made, and whether they are as simple as the functions demonstrated.

The second session introduces a new admissions function, but without revealing its logic.

=
### Session 2: Hidden policy

* Remind students of the admissions function examples. Show this function signature, without showing the function’s implementation:

`python
# stateResident is a Boolean value that is True if a student is a resident in state
# GPA is a floating point number between 0 and 5.0 and represents a student’s grade point average
# GPAPercentile is between 0.0 and 1.0 and represents the percentile ranking of the student’s GPA at their school
# SAT is an integer between 400−1600
# essayScore is an integer between 1 and 10, 10 is better
# Returns a Boolean, True if the student is admitted.
def admit(stateResident, GPA, GPAPercentile, SAT, essayScore)
`

* Ask the students to provide example values for you to try. Ensure the examples cover a range of possible inputs.

* Pose the question: is it fair? What would they want to know to make that judgment? Capture the questions they have about the function in a shared space.

* Organize students into small groups. Task them with tinkering with the function, trying different inputs and observing the resulting outputs, and trying to build a model of how they think it works.

* Have each group share the rules that they think govern the function’s behavior.

* Pose the question to the class again: is it fair?

* Reveal the logic of the algorithm:

`python
if stateResident:
  if GPAPercentile >= 0.9:
    return True
  else:
    return (GPA > 3.0 and SAT > 1,200 and essayScore >= 8) or 
           random.random() > 0.5
else:
   return GPA > 3.7 and SAT > 1,400 and essayScore >= 9
`  

* After giving students a chance to see what logic they got right, reflecting on why it was so hard to understand its behavior without seeing it’s logic.
=

This second session introduces the idea that functions are not necessarily transparent: admissions processes algorithms are rarely transparent, and so they often cannot be examined for fairness. They also reveal how even simple and small programs can have surprisingly complex behaviors that are hard to reverse engineer. Students should leave the session understanding that functions are an idea that exists both in the world, and in computer science, and that they are ways of encoding the logic of decisions.

The third session engages students in critically reflecting on the fairness of the algorithm.

=
### Session 3: Admissions function fairness

* Bring up the algorithm again, and explain that it’s an approximation of the admissions function used by Texas public universities, which has a "top 10%" rule.

* Divide the class into philosophical chairs groups and prompt: is it fair? What is fair about it and what is not? Capture responses in a shared space.

* *Formative assessment*. Divide the class into small groups and ask them to revise the function’s logic, grouping teams by the position they take on the function’s fairness. Prompt them to discuss how they would change its behavior to make it more fair, and have them reflect those changes in revisions to the algorithm. Ensure they test their functions to ensure that it implements the behavior they intend. All functions should take the same inputs and provide the same possible outputs, just using revised logic. Negotiate when the revisions are due and how they’ll be presented and evaluated.
    ** This is _responsive_ in that students center their own values and notions of fairness.
    ** This is _participatory_ in that students are shaping what they are making and how it will be shared with their peers.
    ** This is _educative_ in that the process of constructing logic will compel hard decisions about fairness, revealing the limitations of using logic to make subjective decisions.
=

Students should leave the third session with a new perspective as a function author, envisioning new notions of admissions fairness and translating them into code. They should also experience a sense of the difficulty of expressing subjective, nuanced ideas around fairness as logical rules.

In the next session, students evaluate each others’ revised algorithms, again trying to reverse engineer, but at the scale of many different opaque admissions policies.

=
### Session 4: Hidden policies

* Have students open their revised programs.

* Present a series of student cases, and have each group use their function to compute the admissions decision, holding up their hand if they admit the person. After each student example, have each group defend their algorithm’s decision.

* Bring the class back together as a group for a series of discussion questions:
    ** Are any of the versions more fair than others?
    ** What kinds of inputs are missing from the function?
    ** What does fairness in college admissions mean?
    ** Should colleges be required to make their decisions transparent?
    ** Should admissions decisions be made by algorithms, by people, or both?
    ** Should there even be college admissions?

* *Summative assessment*. Prompt the students to use the discussion to write an essay articulating their own position on how admissions should work, to what extent rules and cutoffs should be involved, and to what extent these rules should be encoded as functions that others cannot inspect. Discuss what qualities might make a good essay, co-constructing a rubric for evaluating the essays.
    ** This is _responsive_ in that students are asked to articulate their own values and response to others’.
    ** This is _participatory_ in that students shape the criteria that are used to evaluate their writing.
    ** This is _educative_ in that in developing an argument for their values, they may surface tensions that cause them to question their positions.
=

Sessions should leave this session with a greater critical consciousness about college admissions policies, different notions of admissions fairness, the role of algorithms in encoding and automating these policies, and likely some position personal about fairness. They should also have a stronger sense of how functions encapsulate logic, which is a way of hiding information. This might be beneficial for someone implementing software, but can be a way of maintaining secrecy and holding power over people who are subjected to a function’s output.

Whereas the methods presented earlier explicitly focus on developing skills in using and designing functions, this method prioritizes critical consciousness over skills. This is a tradeoff in learning objectives: students who focus on designing functions will be more capable of writing programs to solve particular computational problems, but may not see the social problems they might create with their designs, whereas students who focus on critically examining the implications of functions might see their consequences more clearly, but be less well positioned to design them. A curriculum that balances these two over time might resolve these tradeoffs.

# Conclusion: the power and peril of opacity

Ask any computer scientist about the most powerful ideas in CS and they are quite likely to mention abstraction -- it is not only at the heart of what makes programs work, but of what enables us to make programs work together, building upon the ever larger history of code in the world to create ever greater things with computing. In fact, some computer scientists will not only characterize abstraction as powerful, but _beautiful_, that a single simple idea like a function can be so infinitely powerful.

That power and beauty, of course, has a price: a loss of transparency. There are contexts in which hiding the implementation of something is quite beneficial -- computing wouldn't be so broadly applicable or useful to humanity if we all had to understand the nuances of how it worked. But sometimes we have to understand how it works: politicians need to understand it to make informed decisions about technology policy; doctors need to understand it to know when to trust software to aid them in diagnosing an illness or managing care; and anyone who has ever tried to troubleshoot a problem with computers knows how important it can be to peer into these black boxes to repair them. The question, then, is how to prioritize these different kinds of knowledge: is it more important that every child know how to write code that _calls_ functions, knows how to write code that _defines_ functions, or knows how to critically examine what programs are hiding behind abstractions? The first two skills might position youth for high paying jobs, but at the expense of their ability to advocate for more just applications of abstraction to our digital world.

@standardsHeader
@standardsBlurb

@cstaHeader
@cstaIC
@csta2IC20
@csta3AIC24
@csta3AIC26
@csta3AIC28
@csta3BIC27
@csta3BIC28
@cstaCS
@csta3ACS01
@cstaAP
@csta2AP10
@csta2AP13
@csta2AP14
@csta2AP16
@csta2AP17
@csta3AAP17
@csta3AAP18
@csta3AAP20
@csta3AAP23
@csta3BAP11
@csta3BAP13
@csta3BAP14
@csta3BAP16
@cstaCS
@csta3ACS01

@toleranceHeader
@toleranceIdentity
@tolerance1
@toleranceJustice
@tolerance11
@tolerance12
@tolerance13
@tolerance14
@toleranceAction
@tolerance17

@teacherHeader
@teacher1
@teacher1a
@teacher1e
@teacher1f
@teacher2
@teacher2a
@teacher2b
@teacher2c
@teacher3
@teacher3b
@teacher3e
@teacher4
@teacher4c
@teacher4e
@teacher4f
@teacher4g
@teacher5
@teacher5a
@teacher5b
@teacher5c
@teacher5d
@teacher5e
@teacher5f