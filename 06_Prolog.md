## Logical Programming

Main features:

* **Terms**: Computing takes place over the domain of all terms defined over a universal alphabet.
* **MGU**: Most General UNifiers, values are assigned to variables by means of automatically generated substitutions
* **Backtracking**: the control is verified by a unified mechanism.

DECLARATIVE -> can be either True or False

Logic programs can be seen as executable specifications (focus on WHAT to compute instead of HOW to compute) -> Inefficient though

### Terms

A variable is a **term**, while a function (functor) with arity 0 (number of arguments) is a **constant** and is a term.

### Proposition

Sentences in logic are called **propositions**. 
We can use **negations** to write false propositions.

Literals can be combined through **logical connectivies**:

* Conjunction `A ∧ B`
* Disjunction `A ∨ B`
* Implication `A -> B`
* Equivalence `A <-> B`

### Resolution

Logical programming works withing **Horn's Clauses**.
Robinson's principle proceed by contradiction.

### Logical variables

Strings which starts with an upper letter.
Variable are SHARED: goals in a conjunctive query can share variables.

### TuProlog Playground

`https://pika-lab.gitlab.io/tuprolog/2p-kt-web/`

## Exercises

1. Maria reads logic programming book by author Peter Lucas

```prolog
read(maria, book(author('Peter', 'Lucas'), lp))
```

2. Anyone likes shopping if she is a girl

```prolog
like(shopping, X) :- girl(X)
```

3. Who likes shopping?

```prolog
girl('Roberta')

?- like(shopping, X)
>>> 'Roberta'
```

4. Kirke hates any city if it is big and crowdy

```prolog
city(bologna)
big(bologna)
crowdy(bologna)

hate(X, kirke) :- city(X), big(X), crowdy(X)
hate(bologna, kirke)
>>> True
```

5. Define predicate descendants with recursion

```prolog
descendants(X, Y) :- father(Y, X)
descendant(X, Y) :- father(Z, X), descendant(Z, Y)
```

### Basic Inference

People wish to live in peace, Men, women and children are people. I am a woman and I hope to live in peace.

```prolog
wish_to_live_in_peace(X) :- people(X)

people(X) -: man(X)
people(X) -: woman(X)
people(X) -: child(X) 

woman(me)

?-wish_to_live_in_peace(me) ==> true
```

### Lists in Prolog

Lists are data structure characterized by a sequence of an arbitrary number of terms separated by commas and enclosed within square brackets.

`[a, b]`

### Cut predicate

To increase efficiency, we can stop the execution with mutually exclusive conditions:

```prolog
minimum(X, Y, X) :- x < Y !.
minimum(X, Y, Y) :- X >= Y !.
```

if `x < Y == True`, there is no need to continue the execution and we can stop to increase efficiency.

### Negation as failure

```prolog
mother(X, Y) :- \+ male(X), child(Y, X) - Incorrect
mother(X, Y) :- child(Y, X), \+ male(x) - Correct
```

We cannot prove that X is male but we can prove that X is the parent of Y.

## Explainable and Ethical AI with Logical Programming

Computation is a vehicle for the study of morality by injecting ethics in AI systems through explainability.

### Why logic for agents?

Logic Programming is declarative (yet not an agent programming language).

### Abduction

We can use abduction to list all the plausible scenarios to be generated under certain conditions, enabling **hypothetical reasoning**.
The agent is able to evaluate the scenarios and choose based on the preferences.

At the same time, **counterfactual reasoning** suggests thoughts about what might have been, what might have happened if any event had been different in the past.

