# A Simple React Project

A todo app is a simple application that allows users to create a list of tasks or items that they need to complete, also known as "to-dos." Users can add, delete, and update tasks as needed, as well as mark tasks as completed. A todo app can help individuals and teams stay organized and on track with their tasks and goals. It is a common example used in programming tutorials and can be built using a variety of frameworks and programming languages, including React, Vue, Angular, and more. In this tutorial we will be using React.

Here is a step-by-step guide to building a simple todo app in React JS:

Step 1: Set up the development environment

- Make sure you have Node.js and npm installed on your system
- Open your terminal and run the command "npx create-react-app todo-app"
- Change directory to "todo-app" and run "npm start" to start the development server
- Open http://localhost:3000/ in your browser to see the app

Step 1.1: Clean the project directory

- Remove all code from the App.css and index.css files
- Remove default code from App.js

Step 2: Create the Todo component

- In the "src" directory, create a new file named "Todo.js"
- In this file, create a functional component named "Todo"
- Inside the "Todo" component, return a div with text from props

Step 3: Create the TodoForm component

- In the "src" directory, create a new file named "TodoForm.js"
- In this file, create a functional component named "TodoForm"
- Inside the "TodoForm" component, return a form element with an input field and a submit button
- Add an "onSubmit" event handler to the form that prevents the default behavior
- Import the "TodoForm" component in the "App.js" file and render it inside the "App" component

Step 4: Manage state in the App component

- Inside the "App" component, add a state object that contains a "todos" array
- Pass the "todos" array as a prop to the "Todo" component
- Add a method to the "App" component that takes a new todo item as an argument and adds it to the "todos" array
- Pass the method as a prop to the "TodoForm" component
- Modify the "onSubmit" event handler in the "TodoForm" component to call the method with the value of the input field as an argument

Step 5: Render the todos

- Import the "Todo" component in the "App.js" file
- Inside the "Todo" component, map over the "todos" array and return a list item for each item in the array
- Add a key prop to each list item that is set to the index of the item in the array

# ADD MORE FESTURES!!!!

# 1. Setting up the React Environment locally

To set up a React environment locally, you will need to:

1. Install Node.js and npm: React is built on top of Node.js and npm is the Node.js package manager. You can download and install Node.js from the official Node.js website.

2. Install a code editor: You can use any code editor of your choice. Some popular code editors for React development are Visual Studio Code, Sublime Text, and Atom.

3. Create a new React app: Once you have installed Node.js and a code editor, you can create a new React app using the `create-react-app` tool. Open a terminal or command prompt and run the following command:

   ```bash
   npx create-react-app my-app
   ```

   Replace `my-app` with the name of your app.

4. Run the app: Once your app is created, you can navigate to the app directory and run the following command to start the development server:

   ```bash
   cd my-app
   npm start
   ```

   This will start the development server and open your app in a browser at `http://localhost:3000`.

That's it! You now have a local React environment set up and ready to start building your app. You can make changes to your code and the development server will automatically reload your app to reflect the changes.

## 1.1 Cleaning up

1. Delete all css code from index.css
2. Delete all css code from App.css
3. Replace default App.js code with this:

```jsx
import React from "react";

function App() {
  return <div>Hello, React</div>;
}

export default App;
```

#2. Todo Component
Lets write our own reusable Todo Component;

1. In src/ create a new empty file named; `Todo.js` or `Todo.jsx`

2. Write a functional component which returns a `div`, which should look something like this:

```jsx
import React from "react";

const Todo = () => {
  return <div></div>;
};
```

3. Make the Todo component take in a prop called `todoText` and render it in inside the `div`

```jsx
const Todo = ({ todoText }) => {
  return <div>{todoText}</div>;
};
```

Note - Here we don't have to write `props.todoText` because we have `destructured` the `todoText` from the `props` objects, hence we can eliminate the `props.` prefix.

# 3. TodoForm Component

Now lets a TdoForm component which will have the form and the input fields.

1.  In the "src" directory, create a new file named "TodoForm.js"

2.  In this file, create a functional component named "TodoForm"

3.  Inside the "TodoForm" component, return a form element with an input field and a submit button

So far, you should have created something similar to the following:

```jsx
const TodoForm = () => {
  return (
    <form>
      <input type="text" placeholder="New Todo" />
      <button type="submit">Add</button>
    </form>
  );
};
```

4.  Add an "onSubmit" event handler to the form that prevents the default behavior and take in a `handleFormSubmit` prop function.

```jsx
const TodoForm = ({ handleFormSubmit }) => {
  const onSubmit = (event) => {
    event.preventDefault();
    handleFormSubmit();
  };

  return (
    <form onSubmit={onSubmit}>
      <input type="text" placeholder="New Todo" />
      <button type="submit">Add</button>
    </form>
  );
};
```

- `event.preventDefault()` is stop the default behavior of the form submit event, meaning the page will not be refreshed.
- we are calling the `handleFormSubmit` prop function inside of the `onSubmit` function because we need to inform the parent component when "Add" button is clicked or form is submitted.

5. Add state for for the input field

- Bring in useState from react

```jsx
import React, { useState } from "react";
```

- Declare a state for a todo

```jsx
const [todo, setTodo] = useState("");
```

Note - we are passing in empty string as a default/initial value for state.

- Bind the input field to the state by using the `value` and `onChange` props.

```jsx
<input
  value={todo}
  onChange={(e) => setTodo(e.target.value)}
  type="text"
  placeholder="New Todo"
/>
```

The `value` prop will make sure the input has what ever is in the state.
the `onChange` prop will be called when ever the user changes the value in side of the input field. When `onChange` is called, we are given an `event` which has all the information about the input field, including the `value` of the input field, which is located inside event > target and can be accessed like `e.target.value`.

so far you should have something like this:

```jsx
const TodoForm = ({ handleFormSubmit }) => {
  const [todo, setTodo] = useState();

  const onSubmit = (event) => {
    event.preventDefault();
    handleFormSubmit();
  };

  return (
    <form onSubmit={onSubmit}>
      <input
        value={todo}
        onChange={(e) => setTodo(e.target.value)}
        type="text"
        placeholder="New Todo"
      />
      <button type="submit">Add</button>
    </form>
  );
};
```

6. Validation and calling `handleFormSubmit` with todo text.

- Inside the `onSubmit`, lets check if the state is holding empty string or has some valid input. If user has valid input we will call `handleFormSubmit` function and pass the `todo` state as the first argument, else, we will just return and do nothing.

```javascript
const onSubmit = (event) => {
  event.preventDefault();
  if (todo) return handleFormSubmit(todo);
};
```

7. Import the "TodoForm" component in the "App.js" file and render it inside the "App" component

```jsx
function App() {
  return (
    <div>
      <TodoForm />
    </div>
  );
}
```

save and now you will see a simple form with text field and a button on the screen.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_06_milestone_2/todoform.png">
</p>
