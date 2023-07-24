## Logical Programming

Main features:

* **Terms**: Computing takes place over the domain of all terms defined over a universal alphabet.
* **MGU**: Most General UNifiers, values are assigned to variables by means of automatically generated substitutions
* **Backtracking**: the control is verified by a unified mechanism.

DECLARATIVE -> can be either True or False

Logic programs can be seen as executable specifications (focus on WHAT to compute instead of HOW to compute) -> Inefficient though

## Terms

A variable is a **term**, while a function (functor) with arity 0 (number of arguments) is a **constant** and is a term.

## Proposition

Sentences in logic are called **propositions**. 
We can use **negations** to write false propositions.

Literals can be combined through **logical connectivies**:

* Conjunction `A ∧ B`
* Disjunction `A ∨ B`
* Implication `A -> B`
* Equivalence `A <-> B`

## Resolution

Logical programming works withing **Horn's Clauses**.
Robinson's principle proceed by contradiction.

## Logical variables

Strings which starts with an upper letter.
Variable are SHARED: goals in a conjunctive query can share variables.




