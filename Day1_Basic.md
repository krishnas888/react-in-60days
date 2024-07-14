Whta is React?

React is javascript library for building user interface. It was developed by facebook and is used to create reusable UI components. React allows developers to build web applications that can update and render efficiently in reponse to data charges.

In React, you can build individual user interface (UI) components. The concept of components is central to React.

what is HTML,JS,CSS?
    HyperText Markup Language (HTML)
    JavaScript (JS) work together. HTML, 
    Cascading Style Sheets (CSS),

Dom:
Document Object Model (DOM).
    The DOM views an HTML document as a tree of nodes. Each node represents an HTML element.

    const p1 = document.getElementById('p1');
    Here document represents the root node of the DOM tree. The getElementById searches the DOM tree and returns the p element whose id attribute matches with the specified string. Hence, we have the first p element object assigned to the variable p1. In the next line, we update its content:

    p1.textContent = 'Welcome to Web';
    Likewise, we update the content of the next p element as well:

    const p2 = document.getElementById('p2');
    p2.textContent = '1991';

    So each time, the script traverses the DOM tree to find the specific node and updates the respective p element. After updating, the browser performs a reflow and repaints the updated parts, as explained in the last section. For every DOM update, the process repeats. For large-size applications with a huge DOM tree and more DOM updates, this can have a negative impact on performance.

Core Concepts of React

1. Components:
    React is built around components. A component is a reusable piece of code that represents a part of the user interface. Components can be simple (like a button) or complex (like a form or an entire page).

    A component is a JavaScript class or function that can accept inputs and output a React element that describes how a section of the UI should appear. All the components you build together can make a complex UI.


2.JSX (JavaScript XML):
    JSX is a syntax extension for JavaScript that looks similar to HTML. It allows you to write HTML structures in the same file as JavaScript code, making it easier to understand and maintain.

3.Virtual DOM:
    React uses a virtual DOM to improve performance. The virtual DOM is a lightweight representation of the actual DOM. When the state of an object changes, React updates the virtual DOM first, and then it syncs these changes with the actual DOM in an efficient manner.

    It creates two copies of the DOM in memory. When we change the DOM, it changes one copy of the DOM. Then, it compares that copy with the other copy to determine what has changed. This process is called diffing.

    React then batches these changes and applies them to the real DOM in one shot. This way, it minimizes the reflow and repaint. This is how React improves performance.

    Let’s look at the difference between the UI render processes in plain JavaScript and React next.

    As we have seen in the previous section, we created the initial UI using HTML, and the browser displayed it. Then, the JavaScript got executed, and the browser repainted the screen with the updated UI.

4.State and Props:
    State is a built-in React object used to contain data or information about the component. Props (short for properties) are used to pass data from one component to another, making components dynamic and reusable.

5.Lifecycle Methods:
    React components have a lifecycle, and you can hook into different stages of this lifecycle using lifecycle methods. These methods are used for things like fetching data, setting up subscriptions, and cleaning up resources.

Why React?

1.Reusable Components:

    React promotes the creation of reusable components, which can save a lot of time and effort in development.

2.Virtual DOM:

    The virtual DOM improves performance by minimizing the number of manipulations to the real DOM.

3.Unidirectional Data Flow:

    React's data flow is one-way, making it easier to understand and debug applications.

4.Community and Ecosystem:

    React has a large community and a rich ecosystem of libraries and tools, which can help speed up development.

Practical Exercise
1.Install Node.js and npm
2.Create a New React Application 
    npx create-react-app my-first-react-app
    npx - node package 
    create-react-app --> create a new project
    my-first-react-app --> name of the project
3.Navigate into your project directory
    cd my-first-react-app
4.Start the Development Server
    npm start


Expalining about basic core consept by using code 

Components ex:

//create file for every reusable component with extention Mycomponent.js  

import React from 'react';

function Mycomponent({
    return{
        <div>
        <h1> This is component </h1>
        </div>
    };
}

exprot default MyComponent;


now we need to improt to into the APP FILE called app.js

import React from 'react';
import Mycomponent from './Mycomponent';

function App(){
    return{
       <div>
       <MyComponent />
        </div>
    };
}

JSX Example:

const element  = <h1> hello this is jsx example </h1>

jsx get transpiled to js by toolls like Babel

const element = React.createElement('h1',null, 'hello, world');

note:
React.createElement is a method in React that creates a new React element. It's the core function behind JSX (JavaScript XML) syntax and is used internally by React to create elements from the JSX you write.

The React.createElement function takes three arguments:

1. type: The type of the element (a string for HTML elements or a React component).
2. props: An object containing the properties (attributes) for the element.
3. children: The children of the element (which can be text, other elements, or an array of elements).

Here's a breakdown of the arguments:

1. type: The type can be a string (for standard HTML elements like 'div', 'h1', 'span', etc.) or a React component class/function.
2. props: An object containing key-value pairs for properties and attributes. If there are no properties, this can be null.
3. children: The children are the nested elements or text. This can be a single element, multiple elements, or text content.

Example
Let's see an example of React.createElement in action:

const element = React.createElement(
  'div', 
  { className: 'container' }, 
  React.createElement('h1', null, 'Hello, world!'),
  React.createElement('p', null, 'This is a React element created without JSX.')
);

This creates the following HTML structure:

const element = (
  <div className="container">
    <h1>Hello, world!</h1>
    <p>This is a React element created with JSX.</p>
  </div>
);

Virtual DOM Example:

const example = document.getElementById('root');
element.innerHtml ="hello";
element.style.color = 'red';

State and props

State Example:

improt React, {useState} from 'react';

function Counter(){
    const[count, setCount] = useState(0);

    return{
        <div>
        <p>Timer{count}</p>
        <button
        onClick ={()=>setCount(Count + 1)}>
        Check me </button>
        </div>
    };
}
export default Counter;

//Props
function Greeting(props){
    return <h1>hello, {props.name}</h1>;
}

now use in app level

function App(){
    return{
        <div>
            <Greeting name ="timon" />
            <Greeting name ="pumba" />
        </div>
    };
}
export default App;

Lifecycle Method Example:

import React, {component} from 'react';

class MyComponent extend Component{
    //runs after the component is mounted
        componentDidMount(){
            console.log("component is mounted")
        }
    //runs after the component is update
        componentDidUpdate(){
            console.log("component is update")
        }
    //runs before the component is Unmount
        componentWillUnmount(){
            console.log("component is Unmount")
        }

        reder(){
            return <h1>hello, this is react lifecycle method</h1>
        }

}
export default Mycomponent;
    

