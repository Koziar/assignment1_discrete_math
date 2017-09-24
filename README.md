# Assignment #1 - Programming with predicates - Discrete Mathematics

## db
```
student(lukasz).
student(william).

class(discreet_mathematics).
class(large_system_development).
class(system_integration).

room(1).
room(2).
room(3).

date(20092017).
date(21092017).
date(26092017).
date(27092017).
date(28092017).
```
## facts
```
takes(lukasz,discreet_mathematics).
takes(william,discreet_mathematics).
takes(lukasz,large_system_development).
takes(william,system_integration).

on(system_integration,20092017).
on(large_system_development,21092017).
on(discreet_mathematics,26092017).
on(system_integration,27092017).
on(large_system_development,28092017).

in(discreet_mathematics,1).
in(large_system_development,2).
in(system_integration,3).
```
## rules
```
mates(X,Y) :-
    student(X),
    takes(X,discreet_mathematics),
    student(Y),
    takes(Y,discreet_mathematics).

goodProgrammer(X) :-
    takes(X,discreet_mathematics).
goodProgrammer(X) :-
    takes(X,large_system_development).

isInterestingClass(X,Y,Z) :-
    student(X),
    student(Y),
    class(Z),
    takes(X,Z),
    takes(Y,Z).   

```