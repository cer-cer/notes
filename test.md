```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
Note left of Bob: who are you.
Note over Alice: rencai
```

```sequence
Title: abc
A->B: nothing
Note over A: hello
B-->D: no
Note right of D: D is bad
D->> A: ab
Note over A, B: wrong way
```

```mermaid
graph TB;
	A-->B;
	A-->C;
	A-->E; 
	E-->F;
```

```mermaid
pie 
	title Pie Chart
	"Dogs" : 100
	"Cats" : 100
	"Ducks" : 50
```

```mermaid
classDiagram
class A{
	<<interface>>
}
class B{
	<<abc>>
}

A <|--B: implement

```



