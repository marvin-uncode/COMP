# Fun Fair Project 

This is the lee county fun fair project. This project will display utilize procedures to the caculate the logistics of colored balls in the fun fair ball bucket game. This project will also utilize these procedues to determine a winner of the game.

* Counts the number of balls corresponding to color
* Counts the total value of balls in bucket based on their color
* Has a judge procedure that determines the winner based on the total points in buckets

### Quick start
**Make sure you have Windows OS version 8 or Linux OS**

> Clone/Download the solution then run `funfair_scheme.rkt`

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

The main task of these procedures is to help determine the winner of the fun fair ball game. Participates will have buckets with different colored balls that are worth an certain amounts of points based on their color. Whichever players has the most points will win the game as per the "judge."

___

#### Installing

The IDE, "Dr.Racket" will need to be installed beforehand in order to properly run the program.
___

#### API

The accomodating methods and classes below describes how funfair_scheme.rkt runs its procedures to effectively determines winners in the funfair games.
___

#lang racket
(require (planet dyoo/simply-scheme:2:2))

(define (ball-val x)
  (cond
    ((equal? "R" x) 10)
    ((equal? "G" x) 15)
    ((equal? "B" x) 20)
    ((equal? "W" x) 1)
  )
)

(define (count-balls x bucket)
  (cond ((empty? bucket) 0)
        (else
         (cond ((equal? (car bucket) x) (+ 1 (count-balls x (cdr bucket))))
               (else (count-balls x (cdr bucket)))
         )
         )
        )
  )

(define (color-counts bucket)
  (define a (count-balls "R" bucket))
  (define b (count-balls "G" bucket))
  (define c (count-balls "B" bucket))
  (define d (count-balls "W" bucket))
  (cons a (cons b (cons c (cons d'()))))
 )

(define (bucket-val bucket)
  (define a (count-balls "R" bucket))
  (define b (count-balls "G" bucket))
  (define c (count-balls "B" bucket))
  (define d (count-balls "W" bucket))
  (define red_value (* a 10))
  (define green_value (* b 15))
  (define blue_value (* c 20))
  (define white_value (* d 1))
  (+ red_value green_value blue_value white_value)
 )

(define (judge bucket_1 bucket_2)
  (define bucket1 (bucket-val bucket_1))
  (define bucket2 (bucket-val bucket_2))
  (cond((> bucket1 bucket2) "Bucket 1, Won .. !")
       ((< bucket1 bucket2) "Bucket 2, Won .. !")
       ((= bucket1 bucket2) "It's a Tie .. !"))
  )
___

#### Result of Sample Test Case

![alt text](https://github.com/marvinbell/COMP/blob/master/exampleoutput.JPG)
___

#### License
 [Auburn University](/LICENSE)

___

## Author
 [Marvin Royal](/LICENSE)
