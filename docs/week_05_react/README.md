# 1. Introduction to React

## 1.1 What is React?

React.js is a popular JavaScript library that allows developers to build user interfaces for web applications. It was created by Facebook and is now maintained by a community of developers.

React.js is often used for building complex and dynamic user interfaces because it makes it easier to manage the state of the application and update the UI based on changes in that state.

One of the key features of React.js is the use of reusable components, which are like building blocks that can be combined and reused across different parts of the application. This makes it easier to maintain and scale the codebase.

React.js uses a declarative syntax, meaning that developers can describe the desired outcome of a task or process, and React.js takes care of the underlying implementation details.

Overall, React.js simplifies the development of complex user interfaces, making it a popular choice for web application developers.

## 1.2 React vs Vue

React.js and Vue.js are both popular JavaScript frameworks used for building dynamic user interfaces for web applications. While they have some similarities, there are also some key differences between them.

React.js is known for its flexibility and powerful features like reusable components and the ability to handle complex state management. It has a larger ecosystem and is backed by Facebook, which means it has a lot of resources available to developers. However, this flexibility can also make it more difficult for beginners to learn.

On the other hand, Vue.js is known for its simplicity and ease of use. It has a smaller learning curve than React.js and is great for building smaller to medium-sized applications. Vue.js also has a smaller footprint, making it faster to load and more performant.

Overall, the choice between React.js and Vue.js depends on the specific needs of the project and the expertise of the development team. Both frameworks have their own strengths and weaknesses, and the best choice will depend on factors such as the size and complexity of the project, the team's skillset, and the performance requirements of the application.

## 1.3 How does React work?

React works by using a component-based approach to building user interfaces for web applications. In a React application, the UI is broken down into small, reusable components, each responsible for rendering a specific part of the user interface.

When a user interacts with the application, such as clicking a button or filling out a form, React updates the component responsible for that part of the UI, instead of reloading the entire page. This makes the application more efficient and responsive.

React also uses a virtual DOM (Document Object Model), which is a lightweight representation of the actual DOM. When a component needs to be updated, React first updates the virtual DOM, and then calculates the difference between the old and new virtual DOMs. It then updates only the parts of the actual DOM that have changed, instead of re-rendering the entire page.

In addition, React allows developers to manage the state of the application more easily by using a unidirectional data flow. This means that data flows in one direction, from parent components to child components, and changes to the state of the application are managed through the use of callbacks and props.

Overall, React works by using a component-based architecture, a virtual DOM, and a unidirectional data flow to make building dynamic user interfaces for web applications more efficient and responsive.

## 1.4 History of React

React.js was created by Facebook in 2011 as an internal tool to help manage the company's rapidly growing codebase. Facebook had been struggling with managing the complexity of its user interface and wanted to find a better way to build and maintain its web applications.

The initial version of React.js was released to the public in May 2013, and it quickly gained popularity among developers. One of the key features that made React.js stand out was its use of a virtual DOM, which made it more efficient than other JavaScript frameworks at the time.

Over time, React.js has continued to evolve and improve, with the introduction of new features and improvements to performance and usability. The React team has also developed a large ecosystem of tools and libraries, making it easier for developers to build complex applications with React.js.

In addition, React.js has become popular not just within Facebook, but also in the wider developer community. Many large companies, including Airbnb, Netflix, and Dropbox, have adopted React.js for building their web applications.

Today, React.js is one of the most popular JavaScript libraries for building user interfaces, and it continues to be actively developed and maintained by the React team and the broader open-source community.

# 2. Getting Started

For production React please do not use React with CDN.

## 2.1 React with CDN

To use React with a CDN, you can include the necessary scripts in your HTML file. Here's an example of how to do this using the latest version of React (as of September 2021):

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My React App</title>
  <!-- Include the React and ReactDOM libraries from the CDN -->
  <script src="https://unpkg.com/react@17.0.2/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.development.js"></script>
</head>
<body>
  <div id="root"></div>
  <!-- Include your React code using a script tag -->
  <script>
    function MyComponent() {
      return React.createElement('h1', null, 'Hello, world!');
    }
    ReactDOM.render(React.createElement(MyComponent), document.getElementById('root'));
  </script>
</body>
</html>
```

In this example, we're including the React and ReactDOM libraries from the CDN using script tags. We're also defining a simple React component called MyComponent, which returns an h1 element with the text "Hello, world!".

Finally, we're using ReactDOM.render() to render our component inside the div with the ID "root".

Note that in a real-world application, you would typically use a build tool like Webpack or create-react-app to manage your dependencies and build your React code, rather than relying on a CDN.

### 2.1.1 createElement()

React.createElement() is a method in React that creates a new React element with the specified type, properties, and children.

The React.createElement() method takes three arguments:

> type (required): The type of the element you want to create. This can be a string (e.g. 'div', 'span', etc.) or a reference to a React component (e.g. MyComponent).

> props (optional): An object that contains the properties you want to set on the element. These properties will be passed as props to the component when it is rendered.

> children (optional): Any child elements that you want to include inside the element you're creating. These can be other React elements created with React.createElement(), or they can be plain strings.

Here's an example of how to use React.createElement() to create a simple React element:

```
const element = React.createElement('h1', { className: 'my-header' }, 'Hello, world!');
```

Note that in modern React code, you would typically use JSX syntax to create elements instead of React.createElement(). JSX provides a more concise and readable syntax for creating React elements, and it is automatically transpiled to React.createElement() calls by Babel.

## 2.2 React and Babel with CDN

To use React with Babel and a CDN, you can include the necessary scripts in your HTML file. Here's an example of how to do this using the latest version of React (as of September 2021) and Babel:

```
<!DOCTYPE html>
<html>
  <head>
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>

    <div id="root"></div>

    <script type="text/babel">
      function Hello() {
        return <h1>Hello World!</h1>;
      }

      const container = document.getElementById('root');
      const root = ReactDOM.createRoot(container);
      root.render(<Hello />)
    </script>

  </body>
</html>
```

In this example, we're including the React and ReactDOM libraries from the CDN using script tags, and we're also including the Babel standalone library.

We're then using a script tag with type="text/babel" to write JSX code. Note that the type="text/babel" attribute tells the browser to treat the script as JSX code that needs to be transpiled with Babel.

Finally, we're using a separate script tag to transpile the JSX code with Babel. This script finds all script tags with type="text/babel", transpiles each one using Babel, and then executes the resulting JavaScript code.

### 2.2.1 JSX

JSX (JavaScript XML) is a syntax extension to JavaScript that allows you to write HTML-like code in your JavaScript files. It is a way to write declarative views for React applications.

In other words, JSX is a syntax that allows you to write HTML-like code in your JavaScript files. With JSX, you can define what a component should look like by writing HTML-like code directly in your JavaScript file, rather than building up the component's structure with JavaScript function calls.

Here's an example of how to use JSX to define a simple React component:

```
function MyComponent() {
  return (
    <div className="my-component">
      <h1>Hello, world!</h1>
      <p>This is my component.</p>
    </div>
  );
}
```

In this example, we're defining a new function called MyComponent that returns a JSX expression. The expression defines a div element with the class name 'my-component', and two child elements: an h1 element with the text 'Hello, world!', and a p element with the text 'This is my component.'.

Note that to use JSX in your React code, you'll need to set up a build process that transpiles your JSX code into plain JavaScript using a tool like Babel.

## 2.3 Set up a React Environment Locally

To set up a React environment locally, you will need to:

1. Install Node.js and npm: React is built on top of Node.js and npm is the Node.js package manager. You can download and install Node.js from the official Node.js website.

2. Install a code editor: You can use any code editor of your choice. Some popular code editors for React development are Visual Studio Code, Sublime Text, and Atom.

3. Create a new React app: Once you have installed Node.js and a code editor, you can create a new React app using the create-react-app tool. Open a terminal or command prompt and run the following command:

```
npx create-react-app my-app
```

4. Replace my-app with the name of your app.

5. Run the app: Once your app is created, you can navigate to the app directory and run the following command to start the development server:

```
cd my-app
npm start
```

This will start the development server and open your app in a browser at http://localhost:3000.

That's it! You now have a local React environment set up and ready to start building your app. You can make changes to your code and the development server will automatically reload your app to reflect the changes.

### 2.3.1 The create-react-app file structure

When you create a new React app using create-react-app, it generates a basic file structure for your project. Here's an explanation of the file structure:

```
my-app/
  node_modules/
  public/
    index.html
    favicon.ico
  src/
    App.js
    App.css
    index.js
    index.css
    logo.svg
    serviceWorker.js
  package.json
  README.md
```

Here's what each of these files and directories do:

- node_modules/: This directory contains all the dependencies (third-party packages) that your app uses. You don't need to manually manage these dependencies - they are installed automatically by npm when you run npm install.

- public/: This directory contains the public files that are served by your app. It contains the main index.html file that loads your React app, as well as other static files like images and fonts.

- src/: This directory contains the source code for your app. It contains the main index.js file that renders your React app, as well as other files like App.js that define your React components.

- App.js: This file defines the main component for your app.

- App.css: This file contains the CSS styles for your app.

- index.js: This file is the entry point for your app. It renders the main App component and mounts it to the DOM.

- index.css: This file contains global CSS styles that are applied to your entire app.

- logo.svg: This is the default logo for your app.

- serviceWorker.js: This file contains the code for a service worker that enables offline functionality for your app.

- package.json: This file contains metadata about your app, as well as the list of dependencies that your app uses.

- README.md: This file contains documentation and instructions for your app.

That's a brief overview of the file structure of a create-react-app project. Of course, you can add, remove, or modify files as needed to fit the requirements of your project.

# 3. React Ecosystem

## 3.1 React Components

In React, a component is a building block of a user interface. A component is essentially a piece of UI that can be reused across an application. It can be thought of as a self-contained module that renders a part of the UI.

Components can be either functional or class-based. Functional components are simpler and only receive props as input and return JSX as output. Class-based components are more powerful and can have state, lifecycle methods, and other features.

Here's an example of a functional component:

```
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

This component takes in a single prop called `name` and returns a greeting with the value of name included.

And here's an example of a class-based component:

```
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  handleClick = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.handleClick}>Increment</button>
      </div>
    );
  }
}
```

This component has a state variable called `count` and a method called `handleClick` that updates the state when a button is clicked. The component also includes a `render` method that returns the JSX markup for the component.

Components can be combined and nested to create complex UIs. By breaking an interface down into components, React makes it easier to maintain and reuse code.

### 3.1.1 Pure Component

In React, a pure component is a type of component that only re-renders when its props or state changes. A pure component is designed to be highly performant and efficient, because it avoids unnecessary re-rendering when there are no changes to its input.

A pure component is implemented as a subclass of the React.PureComponent base class. It inherits all the properties and methods of a regular React.Component, but it adds a shallow comparison of the current props and state with the previous props and state to determine if a re-render is necessary.

Here's an example of a pure component:

```
class MyComponent extends React.PureComponent {
  render() {
    return <div>{this.props.value}</div>;
  }
}
```

In this example, the `MyComponent` class extends the `React.PureComponent` base class. It has a single prop called `value` that is rendered inside a `div` element. When the component is rendered, React automatically performs a shallow comparison of the current `props` and `state` with the previous `props` and `state`. If they are equal, the component is not re-rendered.

Pure components are a useful optimization technique, because they reduce the amount of unnecessary re-renders that can slow down a React application. However, they should only be used when the performance benefits are significant, because they can also make it more difficult to debug and maintain the code.

### 3.1.2 Lifecycle of a component

In React, components have a lifecycle that is divided into several phases. These phases are:

1. Mounting: This is the phase where the component is created and added to the DOM. The following methods are called in order during this phase:

- - constructor()
    static getDerivedStateFromProps()
    render()
    componentDidMount()

2. Updating: This is the phase where the component's state or props are updated and the component is re-rendered. The following methods are called in order during this phase:

- - static getDerivedStateFromProps()
    shouldComponentUpdate()
    render()
    getSnapshotBeforeUpdate()
    componentDidUpdate()

3. Unmounting: This is the phase where the component is removed from the DOM. The following method is called during this phase:

- - componentWillUnmount()

4. Error Handling: This is the phase where errors are handled during rendering, in a lifecycle method, or in the constructor of any child component. The following method is called during this phase:

- - static getDerivedStateFromError()
    componentDidCatch()

Each of these methods can be implemented in a component to perform custom logic at different points in the component's lifecycle. The `render()` method is the only required method for a React component, as it is responsible for returning the JSX that represents the component.

## 3.2 Props

In React, `props` (short for "properties") are a way to pass data and configuration to a component. A component can accept `props` as input and use them to determine what to render and how to behave.

`Props` are similar to function arguments in that they allow data to be passed from one part of the application to another. However, unlike function arguments, `props` are read-only and cannot be modified by the component that receives them.

Here's an example of how props can be used in a functional component:

```
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

In this example, the `Greeting` component accepts a single `prop` called `name`. When the component is rendered, it uses the value of `props.name` to generate a greeting.

Props can also be used in class-based components:

```
class Counter extends React.Component {
  render() {
    return <div>Count: {this.props.count}</div>;
  }
}
```

In this example, the `Counter` component accepts a single `prop` called `count`. When the component is rendered, it displays the value of` this.props.count`.

Props can be any type of data, including strings, numbers, objects, and functions. They can also be used to pass callbacks and event handlers between components, allowing for complex interactions between different parts of the application.

### 3.2.1 Passing data though props

In React, data is passed to a component as props by specifying them as attributes on the component when it is rendered. Here's an example:

```
function MyComponent(props) {
  return <div>{props.title}</div>;
}

ReactDOM.render(
  <MyComponent title="Hello, World!" />,
  document.getElementById('root')
);
```

In this example, the `MyComponent` function accepts a single prop called `title`. When the component is rendered, the value of `title` is passed to the component as an attribute. The component then uses the value of `props.title` to render the content of the `div` element.

In a class-based component, props can be accessed using the `this.props` syntax:

```
class MyComponent extends React.Component {
  render() {
    return <div>{this.props.title}</div>;
  }
}

ReactDOM.render(
  <MyComponent title="Hello, World!" />,
  document.getElementById('root')
);
```

In this example, the `MyComponent` class has a render method that returns the content of a `div` element. The value of the title prop is accessed using `this.props.title..`

Props can be used to pass any type of data, including strings, numbers, objects, and functions. They can also be used to pass callbacks and event handlers between components, allowing for complex interactions between different parts of the application.

### 3.2.2 Combining Components and Props to embed components inside a Component

In React, components can be composed of other components by including them in the render method of the parent component. Here's an example:

```
function ChildComponent(props) {
  return <div>{props.text}</div>;
}

function ParentComponent(props) {
  return (
    <div>
      <h1>{props.title}</h1>
      <ChildComponent text={props.text} />
    </div>
  );
}

ReactDOM.render(
  <ParentComponent title="Example" text="Hello, World!" />,
  document.getElementById('root')
);
```

In this example, the `ChildComponent` is included inside the `ParentComponent` by calling it inside the JSX of the `ParentComponent`'s render method. The `ChildComponent` is passed a `prop` called `text`, which is set to the value of `props.text` from the ParentComponent.

When the ParentComponent is rendered, it will display a heading with the value of props.title and the ChildComponent, which will display the value of `props.text`.

This is just one way to compose components in React. Components can be nested within each other to create complex component hierarchies and user interfaces.

## 3.3 React State Pattern

In React, the `state` is a JavaScript object that represents the internal `state` of a component. The `state` of a component can be changed over time based on user interaction, network requests, or any other events that occur during the lifecycle of the component.

The `state` is managed by the component itself, and changes to the `state` trigger a re-render of the component. When the `state` of a component changes, React updates the DOM to reflect the new `state` of the component.

Here's an example of a stateful component that manages a `count` variable:

```
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Increment
        </button>
      </div>
    );
  }
}
```

In this example, the `Counter` component has a `count` variable in its `state`, which is initially set to 0 in the constructor. The render method displays the value of `this.state.count` in a paragraph element, and a button that increments the `count` when clicked by calling the `setState` method.

When the button is clicked, the `setState` method is called with a new state object that increments the `count` variable by 1. This triggers a re-render of the component, and the updated value of `count` is displayed in the paragraph element.

## 3.4 React Events

In React, you can handle events by passing a function as a prop to a DOM element, which will be called when the event occurs.

Here's an example of how to handle a click event in React:

```jsx
import React from "react";

class Button extends React.Component {
  handleClick = () => {
    console.log("Button was clicked!");
  };

  render() {
    return <button onClick={this.handleClick}>Click me</button>;
  }
}
```

In this example, we define a `handleClick` method on the `Button` component that logs a message to the console. We then pass this method as a prop to the `onClick` event of the button element.

When the button is clicked, the `handleClick` method is called, and the message "Button was clicked!" is logged to the console.

You can also pass arguments to event handlers by using arrow functions, like this:

```jsx
import React from "react";

class Button extends React.Component {
  handleClick = (name) => {
    console.log(`Hello, ${name}!`);
  };

  render() {
    return (
      <button onClick={() => this.handleClick("Alice")}>
        Say hello to Alice
      </button>
    );
  }
}
```

In this example, we pass an arrow function to the `onClick` event that calls the `handleClick` method with the argument `'Alice'`. When the button is clicked, the message "Hello, Alice!" is logged to the console.

Note that when you pass an arrow function to an event handler like this, a new function is created on every render. This can have performance implications, especially for large components with many event handlers. To avoid this, you can define event handlers as instance methods, like we did in the first example.

## 3.5 Rendering lists in React

In React, you can render a list of items using the `map` function to loop through an array of data and create a list of components.

Here's an example of how to render a list of names in React:

```jsx
import React from "react";

class NameList extends React.Component {
  render() {
    const names = ["Alice", "Bob", "Charlie"];
    const nameListItems = names.map((name) => <li key={name}>{name}</li>);

    return <ul>{nameListItems}</ul>;
  }
}
```

In this example, we define an array of names and use the `map` function to create an array of `<li>` elements, each containing a name from the `names` array. We also include a `key` prop with a unique identifier for each item, which helps React to efficiently update the list when it changes.

Finally, we render the list of `<li>` elements within an `<ul>` element.

When this component is rendered, it will display a list of names:

- Alice
- Bob
- Charlie

Note that in the `map` function, we use an arrow function to create the `<li>` element for each name. This is a concise way to define a function that takes an argument and returns a value. The `key` prop is important for performance reasons, as it helps React to efficiently update the list when items are added, removed, or reordered.

## 3.6 Handling Forms

Working with forms in React involves a few key steps:

1. Create a component to represent the form. This component should define an initial state for the form data and include input fields for the user to enter data.

2. Add an event handler function for the `onSubmit` event of the form. This function should prevent the default form submission behavior, retrieve the form data from the state, and perform any necessary validation or processing.

3. Add event handler functions for each input field to update the corresponding state property when the user enters data.

Here's an example of a simple form component in React:

```jsx
import React from "react";

class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "",
      email: "",
      message: "",
    };
  }

  handleNameChange = (event) => {
    this.setState({ name: event.target.value });
  };

  handleEmailChange = (event) => {
    this.setState({ email: event.target.value });
  };

  handleMessageChange = (event) => {
    this.setState({ message: event.target.value });
  };

  handleSubmit = (event) => {
    event.preventDefault();
    // TODO: perform form validation and processing
  };

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input
            type="text"
            value={this.state.name}
            onChange={this.handleNameChange}
          />
        </label>
        <label>
          Email:
          <input
            type="email"
            value={this.state.email}
            onChange={this.handleEmailChange}
          />
        </label>
        <label>
          Message:
          <textarea
            value={this.state.message}
            onChange={this.handleMessageChange}
          />
        </label>
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

In this example, we define a component `MyForm` that includes input fields for the user to enter their name, email, and a message. We also define event handler functions for the `onChange` events of each input field to update the corresponding state property as the user enters data. Finally, we define an event handler function for the `onSubmit` event of the form that prevents the default form submission behavior and performs any necessary validation or processing.

Note that in the `render` function, we bind the input fields to the corresponding state properties using the `value` prop, and specify the event handler function to be called when the user enters data using the `onChange` prop. We also include a `button` element with the `type` prop set to "submit" to allow the user to submit the form.

When this component is rendered, it will display a form with input fields for the user to enter data. When the user submits the form, the `handleSubmit` function will be called, allowing you to retrieve the form data from the state and perform any necessary processing.

## 3.7 Routing in React

React provides several libraries to handle routing in web applications, but one of the most popular is `react-router`. Here's a brief overview of how to use `react-router` for routing in a React application:

1. Install `react-router-dom` using npm or yarn:

   ```
   npm install react-router-dom
   ```

   or

   ```
   yarn add react-router-dom
   ```

2. Wrap your top-level component with a `Router` component from `react-router-dom`. This will provide routing functionality to your entire application:

   ```jsx
   import React from "react";
   import { BrowserRouter as Router } from "react-router-dom";
   import MyComponent from "./MyComponent";

   function App() {
     return (
       <Router>
         <MyComponent />
       </Router>
     );
   }

   export default App;
   ```

3. Define your routes using `Route` components from `react-router-dom`. A `Route` component takes two props: `path`, which specifies the URL path for the route, and `component`, which specifies the component to render when the URL matches the path. You can define as many `Route` components as you need to cover all the pages of your application:

   ```jsx
   import React from "react";
   import { Route, Switch } from "react-router-dom";
   import Home from "./Home";
   import About from "./About";
   import Contact from "./Contact";

   function MyComponent() {
     return (
       <div>
         <Switch>
           <Route exact path="/" component={Home} />
           <Route path="/about" component={About} />
           <Route path="/contact" component={Contact} />
         </Switch>
       </div>
     );
   }

   export default MyComponent;
   ```

4. Use `Link` components from `react-router-dom` to navigate between pages. A `Link` component takes a `to` prop, which specifies the URL path to navigate to when the link is clicked. You can define `Link` components anywhere in your application, such as in a navigation menu:

   ```jsx
   import React from "react";
   import { Link } from "react-router-dom";

   function NavigationMenu() {
     return (
       <nav>
         <ul>
           <li>
             <Link to="/">Home</Link>
           </li>
           <li>
             <Link to="/about">About</Link>
           </li>
           <li>
             <Link to="/contact">Contact</Link>
           </li>
         </ul>
       </nav>
     );
   }

   export default NavigationMenu;
   ```

That's a basic overview of how to handle routing in a React application using `react-router`. There are many other features and options available in `react-router`, such as nested routes, URL parameters, and programmatic navigation, so be sure to check out the official documentation for more information: https://v5.reactrouter.com/

### 3.7.1 react-router-dom v6

React Router version 6 introduces some changes compared to version 5, so the approach to routing is slightly different. Here's a brief overview of how to handle routing in a React application using React Router version 6:

1. Install `react-router-dom` using npm or yarn:

   ```
   npm install react-router-dom
   ```

   or

   ```
   yarn add react-router-dom
   ```

2. Wrap your top-level component with a `Routes` component from `react-router-dom`. This will provide routing functionality to your entire application:

   ```jsx
   import React from "react";
   import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
   import MyComponent from "./MyComponent";

   function App() {
     return (
       <Router>
         <Routes>
           <Route path="/" element={<MyComponent />} />
         </Routes>
       </Router>
     );
   }

   export default App;
   ```

3. Define your routes using `Route` components from `react-router-dom`. A `Route` component takes two props: `path`, which specifies the URL path for the route, and `element`, which specifies the component to render when the URL matches the path. You can define as many `Route` components as you need to cover all the pages of your application:

   ```jsx
   import React from "react";
   import { Route } from "react-router-dom";
   import Home from "./Home";
   import About from "./About";
   import Contact from "./Contact";

   function MyComponent() {
     return (
       <div>
         <Routes>
           <Route path="/" element={<Home />} />
           <Route path="/about" element={<About />} />
           <Route path="/contact" element={<Contact />} />
         </Routes>
       </div>
     );
   }

   export default MyComponent;
   ```

4. Use `Link` components from `react-router-dom` to navigate between pages. A `Link` component takes a `to` prop, which specifies the URL path to navigate to when the link is clicked. You can define `Link` components anywhere in your application, such as in a navigation menu:

   ```jsx
   import React from "react";
   import { Link } from "react-router-dom";

   function NavigationMenu() {
     return (
       <nav>
         <ul>
           <li>
             <Link to="/">Home</Link>
           </li>
           <li>
             <Link to="/about">About</Link>
           </li>
           <li>
             <Link to="/contact">Contact</Link>
           </li>
         </ul>
       </nav>
     );
   }

   export default NavigationMenu;
   ```

That's a basic overview of how to handle routing in a React application using React Router version 6. There are many other features and options available in React Router, such as nested routes, URL parameters, and programmatic navigation, so be sure to check out the official documentation for more information: https://reactrouter.com/en/6.11.0

## 3.8 React Memo

`React.memo()` is a higher-order component (HOC) in React that helps to optimize the performance of functional components. It's similar to the `PureComponent` class for class components, but it works for functional components.

By default, when the parent component renders, all child components will also re-render, even if their props haven't changed. This can lead to unnecessary rendering and decreased performance, especially if the child components are complex or have a lot of data.

`React.memo()` solves this problem by memoizing the output of a component based on its props. This means that if a component is rendered with the same props as before, it won't re-render and will reuse the previously rendered output. This can significantly improve the performance of your React application.

Here's an example of how to use `React.memo()`:

```jsx
import React, { memo } from "react";

function MyComponent(props) {
  // ... component code ...
}

export default memo(MyComponent);
```

In this example, the `memo` HOC wraps the `MyComponent` function and returns a memoized version of it. The memoized component will only re-render if its props have changed.

Note that `React.memo()` only does a shallow comparison of props by default, so if your props contain complex objects or arrays, you may need to implement your own comparison function to ensure that the component only re-renders when necessary. You can do this by passing a second argument to `React.memo()`, which is a custom comparison function that returns `true` if the props are equal and `false` otherwise.

## 3.9 React Styling

There are several ways to style elements in React:

1. Inline styles: You can use the `style` attribute to add inline styles to an element. The value of the `style` attribute is an object that contains CSS properties and their values in camelCase format.

   ```jsx
   function MyComponent() {
     const style = {
       backgroundColor: "red",
       color: "white",
       padding: "10px",
       borderRadius: "5px",
     };

     return <div style={style}>Hello World</div>;
   }
   ```

2. CSS Modules: CSS Modules are a way to modularize CSS in your React components. They allow you to write CSS styles in a separate file and import them into your component using JavaScript. This helps to avoid naming conflicts and makes it easier to manage styles.

   ```css
   /* styles.module.css */
   .container {
     background-color: red;
     color: white;
     padding: 10px;
     border-radius: 5px;
   }
   ```

   ```jsx
   import styles from "./styles.module.css";

   function MyComponent() {
     return <div className={styles.container}>Hello World</div>;
   }
   ```

3. CSS-in-JS libraries: There are several libraries that allow you to write CSS styles in JavaScript, such as styled-components, emotion, and Material-UI. These libraries provide a more powerful and flexible way to style your components, and they often come with additional features like theming and responsive design.

   ```jsx
   import styled from "styled-components";

   const Container = styled.div`
     background-color: red;
     color: white;
     padding: 10px;
     border-radius: 5px;
   `;

   function MyComponent() {
     return <Container>Hello World</Container>;
   }
   ```

These are just a few examples of how you can style elements in React. Choose the approach that works best for your project and team.

## 3.10 Hooks In React

Hooks are a feature introduced in React 16.8 that allow you to use state and other React features without writing a class component. They provide a way to reuse stateful logic between components and make it easier to write reusable and modular code.

There are several built-in hooks in React, including:

1. `useState`: Allows you to add state to your function components. It returns a stateful value and a function to update that value.

2. `useEffect`: Allows you to perform side effects in your function components, such as fetching data or updating the document title. It runs after every render by default.

3. `useContext`: Allows you to access context values from a context provider in your function components.

4. `useReducer`: A more powerful alternative to `useState` that allows you to manage state with a reducer function, similar to how you would manage state in a Redux store.

5. `useCallback`: Allows you to memoize a function and only recompute it when its dependencies change. This can improve performance by avoiding unnecessary re-renders.

6. `useMemo`: Allows you to memoize a value and only recompute it when its dependencies change. This can also improve performance by avoiding unnecessary re-renders.

7. `useRef`: Allows you to create a mutable ref object that persists between renders. This can be used to access the DOM node of a component or to store any mutable value.

These are just a few examples of the built-in hooks in React. You can also create your own custom hooks to reuse stateful logic between components.

### 3.10.1 useState

To use the `useState` hook in a React functional component, you first need to import it from the `react` library:

```
import React, { useState } from 'react';
```

Then, you can call the `useState` function and pass in the initial state value. It returns an array containing the current state value and a function to update that value:

```
const [count, setCount] = useState(0);
```

In this example, we're using `useState` to manage a `count` state variable, which starts with an initial value of `0`. The `setCount` function can be called to update the `count` value.

Here's an example of how you could use `useState` in a React functional component to display a count and a button that increments the count when clicked:

```
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return (
    <div>
      <p>You clicked the button {count} times</p>
      <button onClick={handleClick}>Click me</button>
    </div>
  );
}
```

In this example, we're rendering a paragraph that displays the current count value and a button that calls the `handleClick` function when clicked. The `handleClick` function updates the count value using the `setCount` function, which triggers a re-render of the component.

### 3.10.2 useEffect

To use the `useEffect` hook in a React functional component, you first need to import it from the `react` library:

```
import React, { useEffect } from 'react';
```

Then, you can call the `useEffect` function and pass in two arguments: a function that performs the effect, and an optional array of dependencies that determine when the effect should be re-run:

```
useEffect(() => {
  // perform effect here
}, [dependency1, dependency2]);
```

The function you pass to `useEffect` will be executed after every render of the component. You can use this function to perform side effects such as fetching data, subscribing to events, or updating the DOM.

The second argument to `useEffect` is an array of dependencies. If any of these dependencies change, the effect will be re-run. If the dependencies array is empty, the effect will only be run once after the initial render.

Here's an example of how you could use `useEffect` in a React functional component to fetch data from an API when the component mounts:

```
import React, { useState, useEffect } from 'react';

function MyComponent() {
  const [data, setData] = useState(null);

  useEffect(() => {
    async function fetchData() {
      const response = await fetch('https://example.com/data');
      const data = await response.json();
      setData(data);
    }
    fetchData();
  }, []);

  return (
    <div>
      {data ? (
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      ) : (
        <p>Loading...</p>
      )}
    </div>
  );
}
```

In this example, we're using `useEffect` to fetch data from an API when the component mounts. The `fetchData` function is defined inside the `useEffect` callback and is marked as `async` so that we can use `await` to wait for the response. When the response arrives, we update the component state using the `setData` function.

Note that we're passing an empty dependencies array `[]` as the second argument to `useEffect`. This means that the effect will only be run once, after the initial render of the component. If we had passed `data` as a dependency, the effect would be re-run every time the `data` state variable changed.

#### Cleaning a useEffect

When you use the `useEffect` hook in a React functional component, the function that you pass to it will run on every render of the component, unless you specify a dependency array as the second argument.

To clean up an effect in React, you can return a function from the effect function that will be executed before the effect is run again or before the component is unmounted. This cleanup function is commonly used to cancel subscriptions, clear timeouts or intervals, or remove event listeners.

Here's an example of how you could use the cleanup function in a `useEffect` hook:

```
import React, { useState, useEffect } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setCount((prevCount) => prevCount + 1);
    }, 1000);

    return () => clearInterval(interval);
  }, []);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}
```

In this example, we're using the `useEffect` hook to set up a timer that increments a count state variable every second. We're returning a cleanup function that clears the interval when the component unmounts or when the effect is run again.

When the `Reset` button is clicked, the count is reset to 0 and the timer starts again.

Note that the cleanup function is defined inside the `useEffect` callback and is returned from it. This ensures that it will be executed before the effect is run again or before the component is unmounted.

### 3.10.3 useContext

The `useContext` hook allows you to consume values from a React context in a functional component.

Here is an example of how to use `useContext`:

```jsx
import React, { useContext } from "react";

const MyContext = React.createContext("defaultValue");

function MyComponent() {
  const valueFromContext = useContext(MyContext);

  return <div>{valueFromContext}</div>;
}
```

In this example, we create a context using `React.createContext` with a default value of "defaultValue". We then define a functional component called `MyComponent` which uses the `useContext` hook to get the value from the context. The value returned from the hook is the value that was passed to the nearest `<MyContext.Provider>` component higher up in the component tree.

To use this component with a custom value, you would wrap it in a `<MyContext.Provider>` component and pass a value prop, like this:

```jsx
function App() {
  return (
    <MyContext.Provider value="customValue">
      <MyComponent />
    </MyContext.Provider>
  );
}
```

In this example, the value passed to `<MyContext.Provider>` is "customValue", so the `MyComponent` component will receive "customValue" as its context value.

You can also use multiple contexts in a single component by calling `useContext` multiple times with different contexts. The hook returns the current value of the context, so you can use it like any other variable in your component.

#### Best Practices

While React context can be a useful tool, there are a few downsides to consider:

1. Overuse can lead to "prop drilling": When you have a deeply nested component tree, using context can be a great way to pass data down without needing to pass props through all the intermediary components. However, if you use context too liberally, it can lead to "prop drilling" - where you pass more props through components than necessary, making your code more complex than it needs to be.

2. It can be harder to track where data is coming from: Because context allows you to pass data through a component tree without props, it can be harder to understand where that data is coming from when you're debugging your code. This can make it harder to track down bugs and fix them.

3. It can make your code less modular: When you use context to pass data between components, it can make your code less modular and harder to reuse. Because your components are no longer self-contained, it can be harder to extract them and use them in other parts of your code.

4. It can lead to more complex code: While context can simplify your code in some cases, it can also make it more complex. When you use context, you need to create a context object, a provider component, and a consumer component. This can add extra complexity to your code and make it harder to read and understand.

#### Controlling re-renders

React context can cause re-renders in certain situations, just like any other state update in React.

When the value of the context changes, all components that use that context will re-render. This is because React needs to ensure that all components that consume the context have access to the latest value.

However, there are some ways to optimize context updates to prevent unnecessary re-renders:

1. Use `React.memo()`: Wrap the child components that consume context with `React.memo()`. This can help prevent unnecessary re-renders by ensuring that the child component only updates when its props or context value changes.

2. Use `useMemo()`: If you're using a complex object as the value of your context, you can use the `useMemo()` hook to memoize the value. This will ensure that the value only updates when its dependencies change, preventing unnecessary re-renders.

3. Use separate contexts: If you have multiple pieces of data that are unrelated to each other, it's best to create separate contexts for each piece of data. This will prevent unnecessary re-renders by ensuring that only the components that consume the context that changed will re-render.

4. Use context sparingly: As I mentioned earlier, overusing context can lead to more re-renders and make your code harder to manage. Use context only when you need to share data between components that are far apart in the component tree. For data that needs to be shared between sibling components or between parent and child components, consider using props instead.

### 3.10.4 useReducer

The `useReducer` hook is used to manage complex state in a React component. It's similar to the `useState` hook, but it's more suitable for cases where the state logic is complex and involves multiple sub-values or actions. Here's an example of how to use the `useReducer` hook in a functional component:

```jsx
import React, { useReducer } from "react";

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: "increment" })}>+</button>
      <button onClick={() => dispatch({ type: "decrement" })}>-</button>
    </div>
  );
}
```

In this example, we create an initial state object called `initialState` with a `count` property set to `0`. We also create a `reducer` function that takes a `state` object and an `action` object, and returns a new state object based on the type of action.

We then use the `useReducer` hook to create a `state` object and a `dispatch` function that we can use to dispatch actions to the reducer function. The `useReducer` hook takes two arguments: the `reducer` function and the `initialState` object.

Finally, we use the `state` object to display the current count value and the `dispatch` function to dispatch `increment` and `decrement` actions when the user clicks the corresponding buttons.

By using the `useReducer` hook, we can manage complex state in a more concise and predictable way, and avoid the potential pitfalls of using `setState` in complex state scenarios.

### 3.10.5 useCallback

The `useCallback` hook is used to memoize functions in React. It's useful when you need to pass a function down to a child component as a prop, but you don't want to create a new function on every render. This can be a performance optimization, especially if the child component is a deeply nested component or a component that renders frequently.

Here's an example of how to use the `useCallback` hook:

```jsx
import React, { useState, useCallback } from "react";

function Parent() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <Child onClick={increment} />
    </div>
  );
}

function Child({ onClick }) {
  return <button onClick={onClick}>Click me</button>;
}
```

In this example, we have a `Parent` component that renders a `Child` component and passes down an `increment` function as a prop. The `increment` function is created using the `useCallback` hook, which takes two arguments: the function that we want to memoize and an array of dependencies that the function depends on.

In this case, we pass `count` as a dependency, which means that the `increment` function will be recreated whenever the `count` state changes. This ensures that the `increment` function always has access to the latest `count` value.

We then pass the `increment` function down to the `Child` component as a prop, and use it as an event handler for a button click. Because we're using `useCallback` to memoize the function, the `increment` function will not be recreated on every render, which can improve performance.

Note that `useCallback` is not always necessary, and should only be used when you need to memoize a function. If the function doesn't need to be memoized, you can simply pass it down as a regular prop.

### 3.10.6 useMemo

The `useMemo` hook is used to memoize a value that is expensive to compute. It takes two arguments: a function that computes the value, and an array of dependencies. The computed value is only re-computed if one of the dependencies changes.

Here's an example of how to use `useMemo`:

```jsx
import React, { useMemo } from "react";

function MyComponent(props) {
  const expensiveValue = useMemo(() => {
    // some expensive computation
    return props.someProp * 2;
  }, [props.someProp]);

  return <div>{expensiveValue}</div>;
}
```

In this example, `expensiveValue` is computed by multiplying `props.someProp` by 2. This computation is expensive, so we use `useMemo` to memoize the value. The second argument to `useMemo` is an array containing `props.someProp`, which means that `expensiveValue` will only be recomputed if `props.someProp` changes.

### 3.10.7 useRef

The `useRef` hook is used to create a reference to an element in a React component. Here's an example of how to use the `useRef` hook in a functional component:

```jsx
import React, { useRef } from "react";

function MyComponent() {
  const myRef = useRef(null);

  function handleClick() {
    myRef.current.focus();
  }

  return (
    <div>
      <input type="text" ref={myRef} />
      <button onClick={handleClick}>Focus Input</button>
    </div>
  );
}
```

In this example, we create a reference called `myRef` using the `useRef` hook and initialize it with `null`. We then use this reference to attach it to the `input` element using the `ref` attribute.

We also create a `handleClick` function that uses the `focus` method of the `myRef` reference to focus the `input` element when the `button` is clicked.

By using the `useRef` hook, we can create a reference to a DOM element or any other value that we want to persist across renders.

### 3.10.8 Custom Hooks

A custom hook is a JavaScript function that uses one or more of the built-in React hooks (`useState`, `useEffect`, `useContext`, etc.) to provide some reusable functionality. Custom hooks allow you to abstract away common patterns and make your code more reusable and composable.

Here's an example of how to write a custom hook:

```jsx
import { useState, useEffect } from "react";

function useCounter(initialValue, step) {
  const [count, setCount] = useState(initialValue);

  useEffect(() => {
    const timer = setInterval(() => {
      setCount((c) => c + step);
    }, 1000);

    return () => clearInterval(timer);
  }, [step]);

  return count;
}
```

In this example, `useCounter` is a custom hook that provides a simple counter that increments by a given step every second. It uses the `useState` and `useEffect` hooks to manage the state of the counter and the timer, respectively.

To use the custom hook, you simply call it like any other hook:

```jsx
import { useCounter } from "./useCounter";

function MyComponent() {
  const count = useCounter(0, 1);

  return <div>{count}</div>;
}
```

In this example, `MyComponent` is using the `useCounter` hook to render the current value of the counter. Whenever the value of the counter changes, the component will re-render automatically.

# 4. React Best Practices/Patterns

## 4.1 Composition

Composition in React is the practice of building complex UIs by combining simpler, reusable components. Instead of creating a large, monolithic component that does everything, you break your UI down into smaller, more manageable pieces and compose them together to create the final UI.

Composition is a powerful tool for building scalable and maintainable UIs because it allows you to separate concerns and create highly modular code. Each component is responsible for a specific piece of the UI, and can be easily reused in other parts of the application.

Here's an example of how you can use composition in React:

```jsx
import React from "react";

function Button({ children, onClick }) {
  return <button onClick={onClick}>{children}</button>;
}

function Card({ title, body, footer }) {
  return (
    <div>
      <h2>{title}</h2>
      <p>{body}</p>
      <div>{footer}</div>
    </div>
  );
}

function App() {
  return (
    <Card
      title="Hello, World!"
      body="Lorem ipsum dolor sit amet, consectetur adipiscing elit."
      footer={
        <Button onClick={() => alert("Button clicked!")}>Click me!</Button>
      }
    />
  );
}
```

In this example, we're using composition to create a `Card` component that consists of a title, a body, and a footer. The footer is a `Button` component that we've passed as a prop to the `Card` component. By using composition in this way, we can easily reuse the `Button` component in other parts of the application and keep our code more modular and maintainable.

## 4.2 `children` in React

In React, `children` is a special prop that allows you to pass child components and elements to a parent component. The `children` prop is used to pass elements and components between components in a nested hierarchy.

Here's an example:

```jsx
function ParentComponent({ children }) {
  return (
    <div>
      <h2>Parent Component</h2>
      {children}
    </div>
  );
}

function ChildComponent() {
  return (
    <div>
      <h3>Child Component</h3>
      <p>This is the child component.</p>
    </div>
  );
}

function App() {
  return (
    <ParentComponent>
      <ChildComponent />
    </ParentComponent>
  );
}
```

In this example, we have a `ParentComponent` that renders its `children` prop. We also have a `ChildComponent` that will be passed as a child to the `ParentComponent`. When we render the `App` component, the `ChildComponent` will be nested inside the `ParentComponent` and its contents will be rendered as the `children` of the parent.

The `children` prop can also be used to pass arbitrary content to a component. For example:

```jsx
function Button({ children }) {
  return <button>{children}</button>;
}

function App() {
  return (
    <div>
      <Button>Click me!</Button>
      <Button>
        <span>Click me too!</span>
      </Button>
    </div>
  );
}
```

In this example, the `Button` component accepts the `children` prop and renders it inside a button element. We can pass a string to the `children` prop, as in the first example, or we can pass a complex nested structure, as in the second example.

## 4.3 Higher Order Components

Higher Order Components (HOC) is a design pattern used in React to enhance the functionality of components. A HOC is a function that takes a component as an argument and returns a new component with additional functionality. The idea is to abstract away the common functionalities from different components and make them reusable across multiple components.

To create a Higher Order Component, you need to:

1. Define a function that accepts a component as an argument.
2. Create a new component that wraps the passed-in component.
3. Add additional functionality to the new component, like state or props.
4. Return the new component.

Here's an example of a simple Higher Order Component that adds a `isLoggedIn` prop to a component:

```jsx
function withAuth(Component) {
  return function (props) {
    const isLoggedIn = true; // check if user is logged in
    return <Component {...props} isLoggedIn={isLoggedIn} />;
  };
}
```

This function takes a component as an argument, and returns a new function that takes props and renders the passed-in component with an additional prop, `isLoggedIn`. The new component can then be used like this:

```jsx
const MyComponentWithAuth = withAuth(MyComponent);
```

Now, `MyComponentWithAuth` will have an additional `isLoggedIn` prop that can be used inside the component. This way, you can reuse the authentication logic across multiple components without having to repeat the same code.

## 4.4 Conditional Rendering

Conditional rendering is a technique in React that allows you to conditionally render components or elements based on a certain condition or set of conditions. It allows you to control what gets displayed on the page based on the current state of your application.

In React, conditional rendering can be achieved in several ways, including:

1. Using the ternary operator:

```jsx
{
  condition ? <Component /> : null;
}
```

This will render `<Component />` if the condition is true, otherwise it will render `null`.

2. Using the logical AND operator:

```jsx
{
  condition && <Component />;
}
```

This will render `<Component />` if the condition is true, otherwise it will render nothing.

3. Using the logical OR operator:

```jsx
{
  condition || <Component />;
}
```

This will render `<Component />` if the condition is false, otherwise it will render nothing.

You can also use if statements or switch statements inside your component's `render()` method to conditionally render components or elements.

For example, here's how you can conditionally render a button based on whether a user is logged in or not:

```jsx
function MyComponent({ isLoggedIn }) {
  return (
    <div>{isLoggedIn ? <button>Logout</button> : <button>Login</button>}</div>
  );
}
```

In this example, the `isLoggedIn` prop is used to conditionally render either a "Logout" button or a "Login" button.

## 4.5 Lift up the State

In React, "lifting state up" refers to a pattern where you move the state from a child component up to its parent component so that multiple children can share the same state. This is useful when you have two or more components that need to access or modify the same state, but are not in a parent-child relationship.

By lifting the state up to a common ancestor component, you can pass the state down to the child components via props, and any changes made to the state will be reflected across all the components that use it. This helps to avoid data inconsistencies and makes your code easier to maintain and reason about.

Lifting state up is a common pattern used in many React applications, particularly those that involve complex user interfaces with multiple components that need to share state.

## 4.6 Fragments

In React, a fragment is a way to group together a list of child elements without creating an additional DOM element. It's a common pattern used when you want to return multiple elements from a component's render method, but you don't want to create a parent element that wraps all of them.

Fragments were introduced in React 16.2 as a way to solve the problem of returning multiple sibling elements from a component's render method. Prior to that, you had to wrap the elements in a parent element, such as a div, which could add unnecessary markup to the DOM.

With fragments, you can group together a list of child elements by wrapping them in a special syntax that looks like empty tags, like this:

```jsx
<>
  <ChildComponent1 />
  <ChildComponent2 />
  <ChildComponent3 />
</>
```

This allows you to return multiple elements from a component's render method without creating a parent element in the DOM. Fragments are also useful for improving the performance of your React application by reducing the number of unnecessary DOM elements that are created.

## 4.7 Portals

In React, portals provide a way to render a child component into a DOM node that is outside of the component hierarchy. This means that the child component can be rendered in a different location in the DOM than its parent component.

Portals are useful when you need to render a child component into a container that is outside of the parent component's DOM hierarchy. For example, if you have a modal component that needs to be rendered at the top level of the DOM, you can use a portal to render the modal into a container that is outside of the parent component.

To use portals in React, you can use the `ReactDOM.createPortal()` method. This method takes two arguments: the child component to render, and the DOM node to render the component into. Here is an example:

```jsx
import React from "react";
import ReactDOM from "react-dom";

function Modal(props) {
  const portalNode = document.getElementById("modal-root");
  return ReactDOM.createPortal(props.children, portalNode);
}

function App() {
  return (
    <div>
      <h1>Hello World</h1>
      <Modal>
        <h2>Modal Title</h2>
        <p>This is some modal content.</p>
      </Modal>
    </div>
  );
}

ReactDOM.render(<App />, document.getElementById("root"));
```

In this example, we have a `Modal` component that uses `ReactDOM.createPortal()` to render its child elements into a DOM node with an ID of `modal-root`. We also have an `App` component that renders the `Modal` component as one of its child elements. When the `Modal` component is rendered, it will be rendered into the `modal-root` node, which is outside of the `App` component's DOM hierarchy.

## 4.8 Reconciliation

Reconciliation is the process in which React updates the user interface by comparing the new changes in the virtual DOM with the old ones, and then, only the changed parts are updated in the real DOM. React's reconciliation algorithm is responsible for efficient updates of the DOM. It is an important part of React's performance optimization and helps to minimize the number of DOM manipulations needed to keep the UI up-to-date.

The reconciliation process starts from the root of the virtual DOM tree and then recursively traverses down the tree, comparing the new and old nodes at each level. React uses several heuristics to optimize the reconciliation process, such as comparing the node types, keys, and refs.

When a change is detected, React updates the affected part of the virtual DOM tree and then generates a new set of changes that need to be applied to the real DOM. Finally, React applies these changes to the real DOM, resulting in an updated user interface. By using this approach, React ensures that the updates are performed efficiently, without causing unnecessary re-renders or DOM manipulations, thus improving the overall performance of the application.

## 4.9 Virtual-DOM

The Virtual DOM (Document Object Model) is a concept in React that allows developers to update and modify the user interface (UI) in an efficient manner. It is a lightweight copy of the actual DOM tree that React creates and uses to keep track of all the changes in the UI.

When an update occurs in the React app, the entire Virtual DOM is updated, and then React checks the difference between the old Virtual DOM and the new one. After that, it only updates the parts of the actual DOM that have changed, instead of re-rendering the entire page. This makes React very fast and efficient compared to other frameworks that re-render the entire page every time there is a change.

## 4.10 Render Props

Render props is a pattern in React that allows a component to pass a function as a prop to its child components. The child components can then call that function and receive some data in return. This allows for greater flexibility and reusability of code, as the parent component does not need to know the specifics of what its child components will do with the data.

In the context of React, a "render prop" is a function that a component uses to render its output. The component passes this function as a prop to its child components, which can then use it to render their own output. This pattern is useful for creating components that can be easily customized and reused in different parts of an application.

Suppose we have a `Mouse` component that tracks the position of the mouse:

```jsx
import React from "react";

class Mouse extends React.Component {
  state = { x: 0, y: 0 };

  handleMouseMove = (event) => {
    this.setState({
      x: event.clientX,
      y: event.clientY,
    });
  };

  render() {
    return (
      <div onMouseMove={this.handleMouseMove}>
        {this.props.render(this.state)}
      </div>
    );
  }
}
```

The `Mouse` component defines a `handleMouseMove` method that updates its state with the current position of the mouse whenever the `mousemove` event is fired on the `div` element. It also renders the result of calling the `render` function that is passed to it as a prop, passing in its current state as an argument.

Now, we can use the `Mouse` component with a render prop like this:

```jsx
import React from "react";
import Mouse from "./Mouse";

const App = () => (
  <div>
    <h1>Mouse Position:</h1>
    <Mouse
      render={({ x, y }) => (
        <p>
          The mouse is at ({x}, {y})
        </p>
      )}
    />
  </div>
);

export default App;
```

Here, we're rendering the `Mouse` component and passing it a function as a `render` prop that takes in the current state of the `Mouse` component and returns some JSX to display it. This way, we can use the `Mouse` component in different parts of our application and customize the rendering based on our needs.

## 4.11 Type Checking with prop-types

PropTypes is a library in React that allows you to define the types of data expected to be passed to a component as props. This helps in catching errors early in the development process and ensures the correct usage of components.

To use PropTypes, you first need to install it via npm:

```bash
npm install prop-types
```

After installing, you can import it into your component file and define the expected types of props using the PropTypes object. Here is an example:

```jsx
import PropTypes from "prop-types";

function MyComponent(props) {
  return <div>{props.message}</div>;
}

MyComponent.propTypes = {
  message: PropTypes.string,
};
```

In the above example, we imported the PropTypes object and defined that the `message` prop should be of type `string`. If the component is rendered without the `message` prop, or with a prop of a different type, a warning will be logged to the console.

You can also specify that a prop is required by setting the `isRequired` flag:

```jsx
MyComponent.propTypes = {
  message: PropTypes.string.isRequired,
};
```

This will throw an error if the `message` prop is not provided to the component.

PropTypes allows you to define various other data types, such as arrays, objects, functions, and more. You can find a full list of types and their respective PropTypes in the official documentation.

## 4.12 Strict Mode

React Strict Mode is a development mode feature in React that helps developers find potential issues with their code early on. When enabled, it activates additional checks and warnings for common mistakes and anti-patterns.

Strict Mode applies to the entire tree below it, so it can be added once in the application's root component and affect all its children.

Some of the benefits of using Strict Mode include:

- Highlighting potential problems with legacy code
- Detecting unsafe lifecycle methods
- Detecting deprecated APIs usage
- Warning about possible typos in the code
- Spotting issues with asynchronous code, such as unintentional state updates

React Strict Mode does not modify the application behavior in production, but it helps developers write better code by detecting potential issues before they become a problem.

## 4.13 Controlled vs UnControlled Component

In React, a component is either controlled or uncontrolled based on how it manages its internal state.

An uncontrolled component is a component that manages its own state internally. This means that the component manages its own data and doesn't rely on the parent or any other external source to manage its state.

On the other hand, a controlled component is a component that relies on the parent or some other external source to manage its state. The parent component passes down the data as props and handles the changes in the component's state using callbacks passed as props.

Here's an example of a controlled component:

```jsx
import React, { useState } from "react";

function ControlledInput(props) {
  const [value, setValue] = useState("");

  const handleChange = (event) => {
    setValue(event.target.value);
    props.onChange(event.target.value);
  };

  return <input type="text" value={value} onChange={handleChange} />;
}
```

In this example, the `ControlledInput` component is a controlled component since it doesn't manage its own state internally. Instead, it receives its value through props and notifies the parent component of any changes using the `onChange` callback passed down as props.

Here's an example of an uncontrolled input component in React:

```jsx
import React from "react";

function UncontrolledInput() {
  const inputRef = React.createRef();

  function handleSubmit(event) {
    event.preventDefault();
    const value = inputRef.current.value;
    console.log("Submitted value:", value);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" ref={inputRef} />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```

In this example, the input component does not have a `value` prop defined, and instead uses a `ref` to access the value of the input field directly. This makes the component "uncontrolled", since its value is not being explicitly set and managed by React. Instead, any updates to the input's value will be managed by the browser DOM. While uncontrolled components can be simpler to write, they can also be harder to reason about and test compared to controlled components.

# 5. Testing in React

Unit tests are automated tests that verify the functionality of a small, isolated piece of code, typically a single function or method. The goal of unit testing is to catch and prevent bugs in the code as early as possible in the development cycle. Unit tests are written by the developer and are designed to ensure that each function or method works as intended and meets its requirements. These tests are typically run frequently during development and are an essential part of a comprehensive testing strategy.

To write unit tests for a React app, you can use a testing library such as Jest with React Testing Lib or Enzyme. Here is a basic example of a test case for a React component using Jest and React Testing Lib:

```jsx
import React from "react";
import { render } from "@testing-library/react";
import MyComponent from "./MyComponent";

describe("MyComponent", () => {
  it("renders a message", () => {
    const { getByText } = render(<MyComponent message="Hello, world!" />);
    expect(getByText("Hello, world!")).toBeInTheDocument();
  });
});
```

In this example, we import the `render` function from the `@testing-library/react` package to render the `MyComponent` component with a message prop of "Hello, world!". We then use the `getByText` function to find the text "Hello, world!" in the rendered component and check that it is in the document using the `toBeInTheDocument` matcher.

This is a simple example, but you can write more complex test cases to check for user interactions, state changes, and other component behaviors.
