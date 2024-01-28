# Python Learning Notes [2024-01-028]

Coding an Adventure Game in Python
Meetup via The Tech Academy

## Five Elements of a Computer Program

1. Entrance (first instruction)
2. Control/Branching (decision points within a program)
3. Variables (pieces of data that a computer program uses which can change)
   1. Keep track of data that can change while the computer is running
   2. Adapt to real-world conditions
4. Subprograms (programs within programs)
   1. Set of instructions in program that is used over & over, given a name, & set to the side so main program can ask for them to run & they will
5. Exit (the end)
   1. Exit point to tell the program you are running it is over
   2. Tell it to stop doing all the extra work

## Notes

+ Things/data you need the subprogram/function/instruction to do to do the work go in parentheses usually
+ Name of the player sometimes changes (display name), so it is a variable
+ print(var) in Python will print the value of the variable (not the variable name)
+ Entrance point: first instruction to be executed
+ *Context/scope determines if the variable knows its value*
+ Program moves through instructions one line at a time (consecutive)
+ Variable to hold the result of a decision
+ Choice value storage
+ If & decision statements need data to do their job - check for whether or not something is true
+ Computer programs are forced to make a decision, so they need criteria to make sure they know what decision to make
+ if() -> program looks inside parentheses to see if something is true
+ == for comparison; = for assignment of value to vairables
  + Assignment of variable means put the data in the variable
  + Comparison of variables means compare values on right or left & determine their relation
+ Can be cut & dry decision, or can be ambiguity (because depends on many variables?)
+ *Programming language is collection of words & symbols*
+ if(): next line then indent because Python is whitespace sensitive
+ Multiple choices, different options
+ A computer program is a complex system that you are able to modify
+ *Test a change that you make before introducing another change*
  + Test functionality to ensure it can be used
  + Test little bits of code at a time to more easily see if it works or breaks the program
  + It's better to find errors sooner rather than later
+ *Most of the time when you write something with any degree of complexity, it won't work the first time*
  + Cool part about the industry since it is easier to test than masonry/architecting/building, etc
+ Code editors try to help you!
+ Python is "whitespace sensitive", instead of other languages that rely on symbols like brackets to indicate it is part of the function
+ The choice is clear when there are fewer decisions; more decisions mean more condition checks & computational power
+ 3 branches of code if 3 if statements
+ Code is a branch if there is a possibility that it might never be run
  + Can be simple or complex
+ *Put your focus on what you are building*
+ Subprogram to complete functionality every time it is called
+ Levels inside program & functions

## Code Example

`
choice = "3"

if(choice == "1"):
  print("You chose to attack the troll. He defeats you.")

if(choice == "2"):
  print("You chose to befriend the troll. He betrays you.")

if(choice == "3"):
  print("You chose to trick the troll. You escape him.")
`

## More Notes

+ Precision in asking questions
+ Have to call a function for it to be run
+ Subprograms have to be called
  + They are descriptions of potential behavior, but have to be asked to run
+ Subprograms are called by different names (subroutines, functions, methods, etc)
+ A subprogram is a set of instructions that will be executed only when requested by another part of the program
+ It is a mini program that only runs when another part of the program asks for it to be run aka calls it
+ It is smarter to copy/paste names of variables so you don't make a typo
+ Capture the choice in a variable & call a function with the variable being passed as a parameter
+ Input handling: how to make sure the input is proper for the function & won't throw an error
+ Python's entrance line of code:
`if __name__ == "__main__":`
