<h1>Chapter 01 - Getting Started</h1>

<br>

- [Getting Started](#getting-started)
  - [What You'll Find in This Guide](#seeting-up-your-development-environment)
    - [Requirements](#requirements)
    - [Initializing Your App](#initializing-your-app)
    - [Application Structure](#application-structure)
  - [Hello World in React](#hello-world-in-react)
  - [Understanding JSX in React](#understanding-jsx-in-react)
    - [JSX Basics](#jsx-basics)
    - [Why Use JSX?](#why-use-jsx?)
    - [JSX Limitations](#jsx-limitations)
  - [Components & Props](#prerequisites)
    - [Components](#components)
    - [Props](#props)


<br>

Now that you've had a glimpse of what lies ahead, let's embark on the journey to becoming a proficient React developer. In this section, we'll guide you through the initial steps, ensuring you have a solid foundation before delving into the more advanced concepts.

## What to Expect in This Section:

•	Setting Up Your Development Environment: We'll begin by guiding you through the process of setting up your development environment.

•	Hello World in React: Get hands-on with your first React application! We'll guide you through the process of creating a simple "Hello World" application, introducing you to the basic syntax and structure of a React component.

•	Understanding JSX: Dive into JSX, the syntax extension used by React. Learn how it simplifies the process of writing React components and how it ultimately translates to JavaScript.

•	Components and Props: Explore the fundamental concepts of components and props in React. Understand the building blocks of React applications and how to pass data between components.

As you progress through these sections, remember that each topic builds upon the previous one, providing you with a structured and comprehensive learning experience. Feel free to explore the code examples, try out the exercises, and don't hesitate to reach out if you have any questions.
Let's get started with the basics and pave the way for your exciting journey into React development! Happy coding! 🚀

<br>

## 1.1: Setting Up Your Development Environment
In the realm of React usage, myriad approaches exist, but for the sake of efficiency and simplicity, we'll opt for the command-line interface (CLI) tool known as create-react-app. This tool expedites the React application development process by automating the installation of essential packages and generating the requisite files, thus handling the intricate tooling.

To witness React in action on your local machine, follow these steps. Create a new file named 'example.html' using your preferred code editor. Open the file, paste the provided HTML snippet, and launch it in your browser.



```js
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Hello World</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <!-- Don't use this in production: -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
    
      function MyApp() {
        return <h1>Hello, world!</h1>;
      }

      const container = document.getElementById('root');
      const root = ReactDOM.createRoot(container);
      root.render(<MyApp />);

    </script>
    <!--
      Note: this page is a great way to try React but it's not suitable for production.
      It slowly compiles JSX with Babel in the browser and uses a large development build of React.

      Read this page for starting a new React project with JSX:
      https://react.dev/learn/start-a-new-react-project

      Read this page for adding React with JSX to an existing project:
      https://react.dev/learn/add-react-to-an-existing-project
    -->
  </body>
</html>

```
Example From: https://react.dev/learn/installation

<br>

While it's feasible to integrate React into a website manually by copying \<script\> elements into an HTML file, create-react-app serves as a widely adopted starting point for React applications. By choosing this method, you'll spend more time on actual app development and less time grappling with setup intricacies.

<br>

<h3>Requirements</h3>
Before diving into create-react-app, ensure you have Node.js installed. It's recommended to use the long-term support (LTS) version, which includes npm (Node Package Manager) and npx (Node Package Runner).

<br>

For Windows users, additional software is necessary to emulate Unix/macOS terminal functionality for the terminal commands mentioned in this guide. Gitbash or Windows Subsystem for Linux (WSL) are both suitable choices.
<br>

Keep in mind that React and ReactDOM produce apps compatible with a relatively modern set of browsers — specifically, IE9 and newer with the aid of some polyfills. For an optimal experience, use a modern browser such as Firefox, Microsoft Edge, Safari, or Chrome while working through these tutorials.

<br>


<h3>Initializing your app</h3>

To kick start your application using create-react-app, provide a single argument — the desired name for your app. This name serves a dual purpose: create-react-app utilizes it to craft a new directory and subsequently generates the necessary files within. Before executing the following commands in your terminal, ensure you navigate to the preferred location for your app on your hard drive:

```Bash

npx create-react-app hello-world

```

Throughout this process, create-react-app will relay various messages in your terminal – a completely normal occurrence. The operation might take a few minutes, but it not only establishes a 'hello-world' directory but also undertakes several pivotal actions within it:

•	Package Installation: Installs essential npm packages crucial to the app's functionality.

•	Script Generation: Writes scripts facilitating the initiation and serving of the application.

•	File and Directory Structure: Constructs a coherent file and directory structure, outlining the fundamental app architecture.

•	Git Initialization: If you have git installed, initializes the directory as a git repository.create-react-app will display a number of messages in your terminal while it works; this is normal! This might take a few minutes, so now might be a good time to go make a cup of tea.

Once the process concludes, navigate to the 'hello-world' directory and execute npm start in your terminal. The scripts installed by create-react-app will activate a local server at localhost:3000, opening the app in a new browser tab. Your browser will showcase the initial view of your application.

<img src="./images/default-create-react-app.png">


<br>

<h3>Application Structure</h3>
create-react-app furnishes a comprehensive foundation for React application development, with an initial file structure resembling:


```js
hello-world
├── README.md
├── node_modules
├── package.json
├── package-lock.json
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    ├── reportWebVitals.js
    └── setupTests.js
```

The 'src' directory becomes the primary workspace, housing the source code for your application.

The 'public' directory contains files essential for your browser during development, particularly 'index.html.' React injects your code into this file for browser execution. While editing, exercise caution with other markup, as it plays a role in create-react-app's functionality. Ensure you modify the text inside the \<title\> element to reflect your application's title for accessibility.

Upon building and deploying a production version, the 'public' directory, including 'index.html,' will be published. Deployment specifics aren't covered in this book.

The 'package.json' file stores project information used by Node.js/npm for organization. Although not exclusive to React applications, create-react-app conveniently populates it. For the completion of this book, understanding this file isn't necessary. 

<br>

## Hello World in React
Now that your React application is up and running, let's kick things off with the quintessential "Hello World" example. In React, this involves creating a simple component that displays the classic greeting.

<br>

Step 1: Open the 'src' Directory

Navigate to the 'src' directory of your React project. This is where the source code for your application resides.

<br>

Step 2: Create a New Component

Inside the 'src' directory, create a new file named HelloWorld.js. This file will house our "Hello World" component.

<br>

Step 3: Write the Component Code

Open HelloWorld.js in your code editor and add the following code:

<br>


```js
// HelloWorld.js
import React from 'react';

const HelloWorld = () => {
  return (
    <div>
      <h1>Hello World!</h1>
      <p>This is your first React component.</p>
    </div>
  );
};

export default HelloWorld;
```

This component is a functional component written as a JavaScript arrow function. It returns JSX (JavaScript XML) representing the structure of our component. In this case, a \<div> containing an \<h1> heading and a \<p> paragraph.

<br>

Step 4: Using the Component in App.js

Now, let's use our newly created HelloWorld component in the main App.js file.
Open App.js in the 'src' directory and replace its content with the following code:

```js
// App.js
import React from 'react';
import HelloWorld from './HelloWorld';

function App() {
  return (
    <div className="App">
      <HelloWorld />
    </div>
  );
}

export default App;
```

Here, we import the HelloWorld component and use it within the App component, rendering it inside a \<div>.

<br>

Step 5: View the Result
Save both files, and if your development server is still running (you can check your terminal), the changes should automatically reflect in your browser. If not, run npm start in the terminal from your project directory.

Visit http://localhost:3000 in your browser, and you should see your React application displaying the "Hello World" message.

Congratulations! You've just created and integrated your first React component. Feel free to experiment further with the component's content and styling as you continue your React journey.


<br>

## 1.2 Understanding JSX in React

JSX, or JavaScript XML, is a syntax extension for JavaScript that looks similar to XML or HTML but allows you to write React elements in a concise and expressive manner. It is a fundamental part of React and provides a syntax that makes it easier to describe the structure of UI components.

<br>

<h3>JSX Basics</h3>

1.	Syntax: JSX looks similar to HTML, allowing you to define elements with a tag-like syntax. However, it's important to note that JSX is not HTML; it's a syntax extension for JavaScript.

```js

  const element = <h1>Hello, JSX!</h1>;

  ```

  <br>

2.	Expressions in JSX: You can embed JavaScript expressions within curly braces {} in JSX. This allows you to dynamically include values or execute JavaScript code.

```js
const name = "John";
const greeting = <p>Hello, {name}!</p>;
```

<br>

3.	HTML Attributes:JSX uses camelCase naming conventions for attributes, similar to JavaScript, instead of HTML's traditional kebab-case.
```js

 const element = <input type="text" placeholder="Enter your name" />;
 ```

<br>

4.	JSX Represents Objects:
JSX is just a terser way to write React.createElement() which returns a javascript object, JSX gets transpiled into JavaScript objects, which React then uses to create and update the DOM efficiently.

```js

 const element = <h1>Hello, JSX!</h1>;
   // Transpiles to: const element = React.createElement('h1', null, 'Hello, JSX!');
```

<br>


<h3>Why Use JSX?</h3>

1.	Readability: JSX makes the code more readable and visually similar to the UI it represents. It closely resembles the final output, making it easier to understand the component structure.

2.	Expressiveness: JSX allows you to express complex UI structures in a concise and expressive manner. This is particularly beneficial when dealing with nested components and dynamic content.

3.	Integration of JavaScript:JSX seamlessly integrates with JavaScript expressions, enabling dynamic content and the use of variables and functions directly within the markup.

4.	Compile-Time Checks: JSX provides compile-time checks for correctness. This helps catch errors early in the development process, reducing the chances of runtime issues.

<br>

<h3>JSX Limitations:</h3>

1.	Learning Curve: While JSX is powerful and expressive, there may be a learning curve for developers who are new to the syntax. Understanding how JSX translates to JavaScript is key.

2.	Build Setup: JSX requires a build step to transpile it into JavaScript that browsers can understand. This additional step may be perceived as an extra setup requirement.


<br>

## 1.3 Components & Props

<h3>Components</h3>

In React, components are the building blocks of user interfaces. They are self-contained, reusable pieces of code that encapsulate a specific functionality or a part of the user interface. React applications are typically composed of multiple components that work together to create the overall user experience.

There are two main types of components in React:

1.	 Functional Components: Functional components are simpler and more concise. They are defined as JavaScript functions and take in props (short for properties) as input and return React elements to describe what should be rendered.

```js
const WelcomeMessage = (props) => {
    return <h1>Hello, {props.name}!</h1>;
  };
  ```

<br>

2.	Class Components: Class components are more feature-rich and can have their own internal state. They are defined using ES6 classes and extend the React.Component class. Class components are useful when you need to manage state or use lifecycle methods.

```js
class WelcomeMessage extends Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

<br>

Components can be composed together, allowing for the creation of complex user interfaces. They enable a modular and maintainable code structure, making it easier to understand and manage the application's logic.

Key concepts related to React components:

•	Props: Short for properties, props are used to pass data from a parent component to a child component. They are immutable and help in maintaining a unidirectional flow of data.

•	State: State represents the internal data of a component. Unlike props, the state can be changed by the component itself. Class components can have state, while functional components use hooks (e.g., useState) to manage state.

•	Lifecycle Methods: Class components have lifecycle methods that are called at different stages of a component's existence, such as mounting, updating, and unmounting. These methods provide hooks for executing code at specific points in the component's lifecycle.

•	Rendering: Components are responsible for rendering UI elements. They use JSX (JavaScript XML) to describe the structure and appearance of the user interface.

•	Reusability: Components promote reusability by encapsulating specific functionalities. This makes it easier to maintain and extend the application.

<br>

<h3>Props</h3>
In React, "props" is short for "properties," and it refers to a special keyword representing the input data that a React component can receive. Props are used to pass data from a parent component to a child component in a unidirectional flow. They make components dynamic by allowing them to receive different sets of data, and props are immutable within the component receiving them.

<br>

Here's a breakdown of how props work in React:
1.	Passing Props:  When a component is used within another component, it can be passed data through attributes, which become the props of the child component.

```js
// Parent component
const App = () => {
  return <ChildComponent name="John" />;
};

// Child component
const ChildComponent = (props) => {
  return <p>Hello, {props.name}!</p>;
};
```


2.	Accessing Props: Inside the child component, the props are accessed as an object. In this case, `props.name` holds the value passed from the parent.

```js
const ChildComponent = (props) => {
    return <p>Hello, {props.name}!</p>;
  };
```

<br>

3.	Dynamic Data: Props allow components to be dynamic. By changing the values passed as props, the same component structure can display different data.

```js
const App = () => {
    return (
      <>
        <ChildComponent name="John" />
        <ChildComponent name="Jane" />
      </>
    );
  };
```

<br>

4.	Default Props: Components can define default values for props using `defaultProps`. If a prop is not provided by the parent, the default value will be used.

```js
 const ChildComponent = (props) => {
    return <p>Hello, {props.name}!</p>;
  };
  
  ChildComponent.defaultProps = {
    name: 'Guest',
  };
```

<br>

Props play a crucial role in React's declarative approach to building UIs. They enable the composition of components, making it easier to manage and reuse code. Additionally, props contribute to the concept of a single source of truth for data, as each component receives its data explicitly through props rather than relying on shared state.

