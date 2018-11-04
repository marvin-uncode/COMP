# Ringing Phones

This is the phone project. In this project, there are multiple rooms with ringing phones in them. We will find many alternate paths to
the rooms that have ringing phones in them.

* Prints paths to specified rooms
* Prints paths to rooms where a starting room was not given
* Prints paths to rooms where a starting and ending room was not given

### Quick start
**Make sure you have Windows OS version 8 or Linux OS**

> Clone/Download the solution then run `roomsandphones.pl`

```

# Download all files from canvas

# For Windows

```

# Table of Contents
* [Problem](#Problem)
* [Installing](#installing)
* [API](#API)
* [License](#license)
* [Author](#author)

#### Problem

The main task of this program is to help determine all possible paths to which a phone may be ringing with the one story building. Sometimes there were be a starting room and ending room given, other times a starting room may not be given, and some other times a starting room and neither a ending room will be given.
___

#### Installing

The compiler, GNU Prolog, and the IDE ,SWI Prolog, will need to be installed beforehand in order to properly run the program.
___

#### API

The accomodating rules and procedures below describe how the rooms are defined and how paths to rooms with ringing phone are found.
___
edge(1,2).
edge(1,7).
edge(7,8).
edge(7,9).
edge(7,10).
edge(7,11).
edge(7,12).
edge(7,13).
edge(7,14).
edge(8,2).
edge(8,3).
edge(8,4).
edge(9,4).
edge(9,5).
edge(9,6).
edge(5,6).
edge(14,15).
edge(15,16).


connected(X,Y) :- edge(X,Y) ; edge(Y,X).

path_to_phone(A,B,My_Path) :-
       travel(A,B,[A],Q), 
       reverse(Q,My_Path).

travel(A,B,P,[B|P]) :- 
       connected(A,B).
travel(A,B,Visited,My_Path) :-
       connected(A,C),           
       C \== B,
       \+member(C,Visited),
       travel(C,B,[C|Visited],My_Path).  
___

#### Result of Sample Test Case

![alt text](https://github.com/marvinbell/COMP/blob/master/scheme_sample.JPG)
___

#### License
 [Auburn University](/LICENSE)

___

## Author
 [Marvin Royal](/LICENSE)
