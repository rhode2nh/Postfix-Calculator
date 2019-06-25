# Overview
This is a java implementation of a postfix calculator. Each character of the user's input is fed into a lexical analyzer which outputs tokens that are used for processing. A parser interprets these tokens and builds a parse tree with them. Once the parse tree is complete, the final output for the initial expression is calculated. It will run indefinitely, waiting for new expressions until it is killed.

# Usage
This program will wait for user input to start calculating. Every expression/equation must end with an '@' symbol in order for the program to start computing.
```sh
>> 3 5 + @
>> 8.0
>>
```
The '@' symbol denotes END OF FILE. If the user does not end the expression with an '@' symbol, the console will go to a new line and wait for the rest of the expression until there is an '@' symbol.
```sh
>> 3 2 +
>>
```
This means that you can break an expression up into multiple lines as such:
```sh
>> 3
>> 2 +
>> @
>> 5
```
Whitespace in expressions is ignored. This means that you can have varying amounts of whitespace (or none) in between characters. 
```sh
>> 4    5  3 ++      @
>> 12.0
```
The exception are numbers and letters. 
```sh
>> 2 3 + @
```
will not be interpreted the same as
```sh
>> 23 + @
```
### Variables
You can set values to variables and use them in future expressions. 
```sh
>> test = 3 4 + @
>> 7.0
>> 1 test - @
>> 6.0 
```
Saved values can only be accessed for the given instance of the program.
## Invalid Inputs
Any invalid input given to the program will have a pointer to the first error-causing character along with an error message printed to the console.
```sh
>> 3 +
Not enough operands:
3 +
  ^
```
