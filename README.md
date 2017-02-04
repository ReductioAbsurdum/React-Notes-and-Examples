# React-Notes-and-Examples
####These are notes and examples for learning the Framework React

##LEARNING REACT JS:

###1(WHAT IS REACT.JS):
React is a javascript library used for UI, created at Facebook, and maintained open source. The benefits are using a virtual DOM, so when a change takes place in the DOM based on user input or any updates, the virtual DOM will efficiently re-render the DOM.
* Reading and writing to the DOM is taxing on efficiency, react reads and writes to the virtual DOM so it's more efficient

React is FAST! Javascript objects are faster than DOM objects. The React Virtual DOM is a javascript object which react reads to rather than reading from the actual DOM object. React only writes to the actual DOM whenever it needs to.
* When we call render in React, javascript is only making changes to the virtual DOM, whereas other frameworks will make direct changes to the actual DOM
* The virtual DOM is like a mediator between the Javascript logic and the actual DOM

React is writing HTML inside the javascript with JSX instead of on the HTML page
<hr>
  For anything vaguely written on this page for any levels, look up more info at source api docs: https://facebook.github.io/react/docs/react-api.html
<hr>

###Level 1 (Creating Elements and rendering React to the DOM):

EX: level1/index.html
ReactDOM.createElement()
  //two params:
* 1st is element to create, EX: React.createElement('div', null, 'Hello World');
* 2nd is where in the DOM you are placing this react element EX: document.getElementById('react-container');

EX: level1/index2.html
React.createElement()
  //3 params:
  * 1st is type, EX: span, div, p
  * 2nd is [props]
  * 3rd is children for this element, what goes inside the tags
    * You can list multiple React.createElement() in the 3rd parameter as shown in getting_started/index2.html
  * Typically you don't use this when using JSX

EX: level1/index3.html
Here we use JSX but need to transpile it, we were using Babel to convert <h1>h1</h1> to React.createElement('h1', null, 'hi');
  * Babel also transpiles your ES6 to javascript readable by the browser
  * Babel is sort of an all purpose ES6, React element, compiler
  * WARNING: Babel compiles at runtime and that's slow, so don't use in production
<hr>
###level 2 (Three ways to create components in React):

In React we use components. Components are bits/ pieces of an overall website. You can have an entire website be a component and have sub components within the component. Components are typically their own tag.
  Component building steps:
    1st: create tag in DOM you plan to render components to
    2nd: create component in Javascript/Babel
    3rd: render component to DOM
    4th: insert any properties inside component tags where you render to the DOM and put these properties inside your component between curly braces {}

EX: level2/index4.html
First off, it's good practice to write components in CamelCase with the first letter Caped as well. You'll treat your react component as a variable, call React.createClass ... or whatever you want to create, and render it to the DOM.
  * At first React.createClass(); was the only method available for creating a React component, but now you can also use ES6 Classes and stateless functional components
  * A quick lesson on using React.createClass() method for creating components, you don't need to wrap your return statement in parentheses, but it's a good idea to do so in order to avoid error by not starting your statement right after the return

EX: level2/index5.html
Creating a React component using an ES6 classes will always extend from the React.Component object (inheriting everything in the React.Component, including render())
  * you still call render() the same way inside your new component

Ex: level2/index6.html
Stateless functional components are just simple functions that return React component elements. You do NOT use render() inside a stateless functional component.

<hr>
###level 3 (Props, Custom methods, State, and Refs):

EX: level3/index7.html
Here we are going to be sending properties to our components which is similar to adding attributes to HTML elements.
  * first we add some (any arbitrarily) named attribute inside the component being rendered to the DOM and set it equal to something, anything!
  * then we reference our attribute (property) inside our component
Inside our example index page the attribute/ property is myText="Hello computer world", it gets written to the props object and we can call it inside our component.

EX: level3/index8.html
  Here we are going to reuse the same component, but rewrite the property going into each component... check it out!
    * remember to wrap your properties inside your component in curly braces {}
  This level/index is all about showing you can display dynamic content and reuse components

EX: level3/index9.html
In this example we are going to create methods inside our component and add a class attributes to our JSX HTML inside our component. When we add anything inside the virtual DOM, we need to use javascript syntax, EX: class="" is now className="" since we are inside Javascript when we are inside the virtualDOM
  * If you're styling anything in the virtual DOM make sure you assign a class to it, you can't directly style Div when it's created in the virtual DOM
  * for creating methods, you just mimic render(){} and separate them with commas unless you are using ES6 class syntax
  * any time you see an attribute inside the virtualDOM using {}, that means it's JSX
  * when calling your methods inside the virtual DOM, EX the attributes on the buttons, you don't need the parentheses after the method, as common in many other frameworks

EX: level3/index10.html
An important React term to understand is State, when a component's state changes the render method will run again and re-render the change in state. We can change the state by using a React method called setState() and set the state to something else. We initialize the state in our component with getInitialState(), part of the React.Component() class.
  * we use JSX in our checkbox input by specifying whether the box should be checked based off of the initialize state of checked, this.state.checked, that way everything in the component is in sync

EX: level3/index11.html
It's important to understand refs in React, it's basically a way to set up virtualDOM input elements with a ref="" and refer to the user input values.
  * A ref is a reference to a virtualDOM element's value. We get all the ref values through this.refs.NameOfRef.value
<hr>

###level 4:
