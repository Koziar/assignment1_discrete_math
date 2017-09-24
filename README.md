# Assignment #1 - Programming with predicates - Discrete Mathematics
### Lukasz Koziarski & William Bech

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
    takes(X,Class),
    student(Y),
    takes(Y,Class).

goodProgrammer(X) :-
    takes(X,discreet_mathematics).
goodProgrammer(X) :-
    takes(X,large_system_development).

isInterestingClass(Class) :-
    class(Class),
    takes(X,Class),
    takes(Y,Class).

atSchool(X,Date) :-
    student(X),
    date(Date),
    takes(X,Class),
    on(Class,Date).

isOccupied(Room,Date) :-
    on(Class,Date),
    in(Class,Room).
```
## questions
```
?- mates(lukasz,william).
 /* Prolog will reply:
    yes */

?- mates(bill,william).
 /* Prolog will reply:
    no */

?- goodProgrammer(lukasz).
 /* Prolog will reply:
    yes */

?- goodProgrammer(william).
 /* Prolog will reply:
    yes */

?- isInterestingClass(What).
 /* Prolog will reply:
    What=discreet_mathematics
    yes */

?- isInterestingClass(system_integration).
 /* Prolog will reply:
    no */

?- atSchool(william,27092017).
 /* Prolog will reply:
    yes */

?- atSchool(adam,26092017).
 /* Prolog will reply:
    no */

?- isOccupied(3,26092017).
 /* Prolog will reply:
    no */
```