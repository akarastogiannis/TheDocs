# React Js Docs

## Rules to live by in React

1. JSX expressions must only have one parent element, usually a div element. Can't return multiple elements. So place all your elements in a single div or empty fragment element (<>).


## Expressions in JSX

### Passing Variables

`const name = 'Bob'`<br>
`<h2> Hi - { name } </h2>`

Output:<br>
"Hi Bob"

### Computation in JSX

`<h1>2 + 2 = { 2+2 }</h1>`

Output:<br>
"2 + 2 = 4"

### Ternary (Conditional) Operaters

`const a = true`<br>
`<h1> a is = {a ? 'True' : 'False' } </h1>`

Output:<br>
"a is True"
