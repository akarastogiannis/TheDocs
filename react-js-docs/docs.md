# React Js Docs

## Rules to live by in React

1. JSX expressions must only have one parent element, usually a div element. Can't return multiple elements. So place all your elements in a single div or empty fragment element (<>).


## Expressions in JSX

### Passing Variables

```
const name = 'Bob'
<h2> Hi - { name } </h2>
```

Output:<br>
> Hi Bob

### Computation in JSX
```
<h1>2 + 2 = { 2+2 }</h1>
```
Output:<br>
> 2 + 2 = 4

### Ternary (Conditional) Operaters
```
const a = true
<h1> a is = {a ? 'True' : 'False' }
```
Output:<br>
> a is True

## Components in JSX

### Rules

1. All JS Components begin with a capital letter.
2. End in .js for JS Files.
3. Every React Component does not need to import React anymore.

### Creating a Function Component

```
import React from 'react'

const Header = () => {
	return (
		<header>
			<h1>Header</h1>
		</header>
	)
}

export default Header
```

### Accessing a Component

```
import Header from './components/Header'

function App() {

	return (
		<div className="Container">
			<Header />
		</div>
	);
}

export default App;
```
<br>

> #### The key takeaways being: <br>
>
> `import Header from './components/Header'`<br>
> 
> `<Header />`

### Creating a Class Component

```
import React from 'react'

class App extends React.Component {
	render() {
		return <h1> Hello from a class lol </h1>
	}
}

export default App
```
## Component Props

### Passed Props

In App.js

```
import Header from './components/Header'

const App = () => {
	return (
		<div className='Container'>
			<Header title="hello" />
		</div>
	)
}

export default App
```

In Header.js

```
const Header = (props) => {
	return (
		<header>
			<h1> {props.title} </h1>
		</header>
	)
}

export default Header
```

### Specific Passed Props

```
import Header from './components/Header'

const App = () => {
	return (
		<div className='Container'>
			<Header title="hello" />
		</div>
	)
}

export default App
```

In Header.js

```
const Header = ( { title } ) => {
	return (
		<header>
			<h1> {title} </h1>
		</header>
	)
}

export default Header
```


### Default Props

In App.js

```
import Header from './components/Header'

const App = () => {
	return (
		<div className='Container'>
			<Header />
		</div>
	)
}

export default App
```

In Header.js

```
const Header = (props) => {
	return (
		<header>
			<h1> {props.title} </h1>
		</header>
	)
}

Header.defaultProps = {
	title: 'Hello',
}

export default Header
```
