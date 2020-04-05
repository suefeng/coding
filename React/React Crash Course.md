# React Crash Course

Objectives

- Master React Fundamentals
- Render Data
- Handle Events
- Debug Your React Apps

* Definition: A JavaScript library for building user interfaces developed by Facebook in 2011, for building user interfaces
* Components: a piece of the UI
* React builds many single, isolated components that when combined builds complex user interfaces

|        | App     |       |       |
| ------ | ------- | ----- | ----- |
| NavBar | Profile | Trend | Feed  |
|        |         |       | Tweet |
|        |         |       | Like  |

``` javascript
class Tweet {
	state = {};
	render() { -> React Element -> maps DOM Element
	}
}
```

* Render has virtual DOM that syncs to real DOM
* No longer need to manipulate the DOM or create event handlers to elements. Just work with components and React auto-updates the DOM to match that state.
* React reacts to state changes and makes view in sync with it
* React is a view library and Angular is a framework
* React has different libraries and you choose which ones to use in your project.

``` bash
$ npm i -g create-react-app
$ npx create-react-app react-app
```

Installs development server, web pack, Babel, and other tools

## npm commands

`$ npm start` -> starts the development server
`$ npm run build` -> bundles app into static files for production
`$ npm test` -> starts test runner
`$ npm run eject` -> removes this tool and copies build dependencies, configs files and scripts into the app directory. Can’t undo!

## React pages

* `App.js` has `class App extends Component` and `render()`
  `render()` contains HTML code like code, JSX (JavaScript XML)
  Babel then takes the JSX syntax and converts it to JS
  Babeljs.io/repl can see live conversion between JSX and JS
* `App.test.js` is for testing
* `Index.js` is the entry point for the app
* `registerServiceWorker.js `serves assets in local cache to PRD environment

## Creating a React page

`import React from ‘react’` React -> object, ‘react’ -> module
`const element = <h1>Hello World</h1>;`
`ReactDOM.render(element, document.getElementById(‘root’));`

## Components

Create a components directory in src and create a `counter.jsx`
All components will go there and need to be referenced in `index.js`

## Embedding Components

`render()` returns JSX and needs a wrapper, can be `<div>` or `<React.Fragment>`
`state={}` contains the data
Curly braces in jsx contains expressions
Example:
`<span>{this.state.count}</span>`

## Setting Attributes

`class` = `className`  in JSX
`style = {this.styles}`  or  `style={{ fontSize: 30}}`
`<img src={this.imgURL} alt=“”>`

## Rendering Classes Dynamically

Create a method and conditions to change `className` values dynamically and assign in `className={this.getClasses()}`

## Rendering Lists

React `render()` does not do loops for list items in the same way as Angular. You need to map an array.

```
state = {
	“tags”: [
		{"tag":“tag1”, "id":"1"},
		{"tag":“tag2”, "id":"2"},
		{"tag":“tag3”, "id":"3"},
		{"tag":“tag4”, "id":"4"}
	]
};
```

```
<ul>
	{this.state.tags.map(tag=><li key={tag.id}>{tag}</li>)}
</ul>
```

## Conditional Rendering

Use helper methods to add conditional statements to enable conditions within `render()`
You can also add conditional statements to render
`{condition === 0 && “Please create a new tag!”}`

## Event Handling

There are regular JS events but the naming is camelCase
`onClick={this.handleIncrement}`
Create `handleIncrement` to have what you want on click

## Binding Event Handlers

`this` is not able to be accessed in `handleIncrement` You can create a `constructor()` to bind `this` to a method

```
constructor() {
	super();
	this.handleIncrement = this.handleIncrement.bind(this);
}
```

 Or you can make `handleIncrement` an arrow function
`handleIncrement = () => {}`

## Updating the State

You have to use `setState` and pass an object to change `state`.
`this.setState({ count: this.state.count + 1 });`

## What Happens When State Changes

`setState` tells React that `state` will change
React then schedules a call to `render()` method asynchronously
React compares virtual and real DOM to see what’s modified

## Passing Event Arguments

Arrow functions in `onClick` events can’t have arguments passed inside like regular functions. This is because events can only pass a function reference. One way is create another method and within it call the method and add an argument inside it

``` javascript
handleIncrement = () => {}
doHandleIncrement = () => {
	this.handleIncrement({});
};
onClick = {this.doHandleIncrement}
```

On a better way

``` javascript
onClick = { () => this.handleIncrement(product)}
```

That way you don’t need `doHandleIncrement()` at all.