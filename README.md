# Overview
This is a java implementation of a postfix calculator. Each character of the user's input is fed into a lexical analyzer which outputs tokens that are used for processing. A parser interprets these tokens and builds a parse tree with them. Once the parse tree is complete, the final output for the initial expression is calculated. 

# Usage
This program will wait for user input to start calculating. Every expression/equation must end with an '@' symbol in order for the program to start computing. 
```sh
>> 3 5 + @
>> 8.0
>>
```
The '@' symbol denotes END OF FILE. If the user does not end the expression with an '@' symbol, the console will go to a new line and wait for more input.
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
>>
```
Whitespace in expressions is ignored. This means that you can have varying amounts of whitespace (or none) in between characters. 
```sh
>> 4    5  3 ++      @
>> 12.0
>>
```
The exception are numbers and letters. 
```sh
>> 2 3 +
```
will not be interpreted the same as
```sh
>> 23 +
```
## Invalid Inputs
Any invalid input given to the program will have a pointer to the first error-causing character along with an error message printed to the console.
```sh
>> 3 +
Note enough operands:
3 +
  ^
```
