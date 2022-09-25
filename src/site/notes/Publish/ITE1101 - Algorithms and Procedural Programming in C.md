---
{"dg-publish":true,"dg-permalink":"ite/1101","permalink":"/ite/1101/","dgHomeLink":true,"dgPassFrontmatter":false}
---

# ITE1101 - Algorithms and Procedural Programming in C
## Course Introduction 

<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">

<div class="markdown-embed-title">



</div>

## Introduction to ITE1101- Algorithms and Procedural Programming in C
* Couse : [[Publish/ITE1101 - Algorithms and Procedural Programming in C|ITE1101 - Algorithms and Procedural Programming in C]]
___
* Objectives : 
	* Learning the C language, and at the same time acquire some notions of algorithmic thinking 

Ecrire un programme C qui permet de tester si un entier est premier : 
```c
boolean premier (int n ){
	// i don't remember basic C syntax 
}
```
what we've got here is a problem that needs resolving. let's reflect on it using natural language : 
>[!info]- Prime Numbers 
> Prime numbers are numbers that are only dividable by 1 and themselves 

Expressing a problem in algorithmic form can  help us identify and resolve certain problems 
if we attack an easier problem say that of adding 2 numbers 
we might write the following algorithm : 

```algorithm 
Algorithme Somme 
variable 
	A,B,C : entier // déclaration des variables
Début 
	A <- 3 // etape d'initialisation
	B <- 4
	
	C <- A+B // affectation d'une valeur 
```

which yields the following C program : 
```c 
#include <stdio.>
void main(){
	int A, B, C; 
	A = 3  ; 
	B = 4  ;
	C = A+B;
	printf("%d+%d=%d",A,B,C); 
	// Read and write in C are done using formatted strings 
}
```
this program when compiled using an appropriate C language compiler will yield a  hexadecimal code that is understandable by the machine and the program becomes runnable. 
>[!note]- Compilers are not just translators....
>Compilers also serve an important role in detecting syntactic errors such as forgetting a `;`  or  typing `print` instead of `printf`
>Useful as they are for syntactic errors, compilers are not immune to semantic errors, in which case we need to review the algorithm 

let's go back to our prime integers 
an algorithm for that problem might look like 
```Algorithme
Algorithme Premier
	Variable
		N, i : entier
		premier : booléen 
	Debut 
		lire(N) 
		i <- 2
		premier <- Vrai 
		
		tant que (i <= n div 2) faire
			Si  (N mod i = 0) alors 
				premier <- Faux 
			fin Si
			i <- i + 1 
		fin tant que 
		Si (premier = Vrai) faire 
			Ecrire(N, " est premier")
		Sinon 
			Ecrire(N, " n'est pas premier")
			
	Fin 
```

the algorithm then translates to the following C code
==Warning, C LANG doesn't have Boolean ! please correct this==
```C 
// this is false, C doesn't have a boolean base type!!!!!!!!
#include <stdio.h>
//#include <math.h> //if needed
void main(){
	int N, i;
	bool flag = true; 
	
	scanf("%d", &N); // reads an int value into N from standard input
	i = 2; //  div / 0 is impossible and 1 is automatically correct 
	
	while (i <= nb/2){
		if ( nb % i == 0) {
			flag = false;
			break;
		}
		i++;		
	}
	if  (flag) {
		printf("%d est premier", N)
	}
	else {
		printf("%d n'est pas premier", N)
	}
}
```

### a C program has a fixed  structure:  
1. include the needed libraries 
2. declare and init global variables and Constants (which are outside the scope of all functions)
3. declare new types and structs
4. declare functions and procedures  and  `void main()` which is the entry point of a given program 
	1. declare local variables
	2. the function body which contains the logic to be executed 

### types
C is a strongly typed language : each variable must have a declared fixed type or the compiler to not throw a tantrum. base types integrated in the C language include : 

| **base type**  | **bytes in memory** |
| -------------- | ------------------- |
| int            | 4 o                 |
| unsignedInt    | 4 O                 |
| short          | 2 O                 |
| unsigned short | 2 O                 |
| long           | 4 O                 |
| unsignedlong   | 4 O                 |
| ---            |                     |
| float          | 4 o                 |
| double         | 8 o                 |
| longDouble     | 16 o                |
| ---            |                     |
| char           | 1 o                 |
| unsigned char  | 1 o                 |

### Operators 
#### Arithmetic Operators
| operator | description                             |
| -------- | --------------------------------------- |
| =        | affectation                             |
| +        | addition                                |
| -        | soustraction                            |
| *        | multiplication                          |
| /        | division entière                        |
| %        | reste de la division entiere            |
| += , -=, \*=      | ajoute  à la valeur actuelle et affecte |
|          |                                         |

#### Relational operators 
| operator     | description |
| ------------ | ----------- |
| <, >, <=, >= |             |
| == , !=      |             |
|              |             |

#### Logical operators 
| operator | description |
| -------- | ----------- |
| !        | not         |
| &&       | anad        |
| \|\|       | or          |

#### Incrementation operators 
| i++ | i = i + 1 |
| --- | --------- |
| i-- | i = i - 1 |
this operator is very confusing because of priority for example 
```C 
i = 4 ; 
B = i++; 
printf('%d', i ) ;// returns 5
printf('%d', B) ; // return 4 
// i++ is not prioritary compared to the affectation operator 
C = ++i;
printf('%d', i ) ;// returns 6
printf('%d', C) ; // return 6
```
___

#### Operator priority 
from higher to lowest
1. ()
2. ++n, --n (prefix operators)
3. \* / %
4. + - 
5. <, >, <= , >=
6. \=\=, != 
7. &&
8. !=
9. +=, -=, \*=, /=, %=
10. n++, n-- (suffix operators)
___
[[2022-09-18|yesterday]] | [[Journal/2022/2022-09-20|Tomorrow]] 

</div></div>

## Chapters 


___
        [[Publish/Chedi's Notes|Back Home]]    |    [[Publish/IT Engineering|IT Engineering]]     |   