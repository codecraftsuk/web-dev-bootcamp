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
- Add a method to the "App" component that takes a new todo item as an argument and adds it to the "todos" array
- Pass the method as a prop to the "TodoForm" component

Step 5: Render the todos

- Import the "Todo" component in the "App.js" file
- Inside the "Todo" component, map over the "todos" array and return a list item for each item in the array
- Add a key prop to each list item that is set to the index of the item in the array

Step 6: Delete a todo

- Inside the "App" component, add another method called "handleDeleteTodo"
- `handleDeleteTodo` will take the `id` of the todo as an argument which the user intends to delete.
- Filter out the todo which matches the `id` and set the todos state to new filtered todos.

Step 7: Completing a todo

- Inside the "App" component, add another method called "handleCompleteTodo"
- `handleCompleteTodo` will take the `id` of the todo as an argument which the user intends to complete.
- Map out the todos, find the todo which matches the `id` and and update the todo object in array.

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

# 4. Manage the State in App.js

1. Inside the "App" component, import useState and add a state object that contains a "todos" array

```jsx
const [todos, setTodos] = useState([]);
```

Note - again we are going to initialize the state with an empty array

2. Add a method to the "App" component that takes a new todo item as an argument and adds it to the "todos" array

```jsx
const handleFormSubmit = (newTodo) => {
  const obj = { id: todos.length + 1, completed: false, text: newTodo };
  setTodos([...todos, obj]);
};
```

- `id` will be used for `key` prop rendering the list. The reason why we are setting it `todos.length + 1` is because to make to sure the id is unique.
- by default the todo will not be completed.

3. Pass the method as a prop to the "TodoForm" component

```jsx
<TodoForm handleFormSubmit={handleFormSubmit} />
```

so far, you should have something like this in App.js:

```jsx
import React, { useState } from "react";

function App() {
  const [todos, setTodos] = useState([]);

  const handleFormSubmit = (newTodo) => {
    const obj = { id: todos.length + 1, completed: false, text: newTodo };
    setTodos([...todos, obj]);
  };

  return (
    <div>
      <TodoForm handleFormSubmit={handleFormSubmit} />
    </div>
  );
}
```

# 5. Render `todos`

1. Import the "Todo" component in the "App.js" file
2. Under the "TodoForm" component, map over the "todos" array and return a `Todo` component for each item in the array

```jsx
{
  todos.map((todo) => <Todo todoText={todo.text} />);
}
```

3. Add a key prop to each list item that is set to the todo text.

```jsx
<Todo key={todo.id} todoText={todo.text} />
```

Note - It is a bad practice to have the todo text as key or even the array index as a key. The todo text is a bad because the array could have multiple items with the same text meaning multiple components with the same key. Array Indexes are bad because when the the order changes the whole list will be re-rendered.
The key should be unique, in most cases it would be the id returned by the Backend or Database.

App component should be something that looks like:

```jsx
function App() {
  const [todos, setTodos] = useState([]);

  const handleFormSubmit = (newTodo) => {
    const obj = { id: todos.length + 1, completed: false, text: newTodo };
    setTodos([...todos, obj]);
  };

  return (
    <div>
      <TodoForm handleFormSubmit={handleFormSubmit} />

      {todos.map((todo) => (
        <Todo key={todo.id} todoText={todo.text} />
      ))}
    </div>
  );
}
```

So far your application should look something like this:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_06_milestone_2/todolist.png">
</p>

# 6. Delete a Todo

1. Inside the Todo component add a button to trigger the deletion of todo

```jsx
const Todo = ({ todoText }) => {
  return (
    <div>
      {todoText} <button>X</button>
    </div>
  );
};
```

2. The Todo component should also now be taking in the `id` as a prop as we will need it for passing it to the deletion handler. We need to pass in the id from when we are mapping over the todos in App component

```jsx
<Todo key={todo.id} todoText={todo.text} id={todo.id} />
```

3. Take in another prop called "handleDeleteTodo", add the event prop (onClick) for the function and pass the `id` of todo to the function

```jsx
const Todo = ({ todoText, id, handleDeleteTodo }) => {
  return (
    <div>
      {todoText} <button onClick={() => handleDeleteTodo(id)}>X</button>
    </div>
  );
};
```

4. Inside the "App" component, add another method called "handleDeleteTodo" and pass it to the Todo Component
5. `handleDeleteTodo` will take the `id` of the todo as an argument which the user intends to delete.
6. Filter out the todo which matches the `id` and set the todos state to new filtered todos.

```jsx
const handleDeleteTodo = (id) => {
  console.log("hi");
  const filteredTodos = todos.filter((todo) => todo.id !== id);
  setTodos(filteredTodos);
};
```

App component should like this:

```jsx
function App() {
  const [todos, setTodos] = useState([]);

  const handleFormSubmit = (newTodo) => {
    const obj = { id: todos.length + 1, completed: false, text: newTodo };
    setTodos([...todos, obj]);
  };

  const handleDeleteTodo = (id) => {
    console.log("hi");
    const filteredTodos = todos.filter((todo) => todo.id !== id);
    setTodos(filteredTodos);
  };

  return (
    <div>
      <TodoForm handleFormSubmit={handleFormSubmit} />

      {todos.map((todo) => (
        <Todo
          key={todo.id}
          todoText={todo.text}
          id={todo.id}
          handleDeleteTodo={handleDeleteTodo}
        />
      ))}
    </div>
  );
}
```

your app should look something like this:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_06_milestone_2/deletetodo.png">
</p>

# 7. Completing a Todo

1. Inside the Todo component take in another prop function called `handleCompleteTodo`
2. Add `handleCompleteTodo` to the `div` as a double-click event (onDoubleClick)

```jsx
const Todo = ({ todoText, id, handleDeleteTodo, handleCompleteTodo }) => {
  return (
    <div onDoubleClick={() => handleCompleteTodo(id)}>
      {todoText} <button onClick={() => handleDeleteTodo(id)}>X</button>
    </div>
  );
};
```

3. Inside the "App" component, add another method called "handleCompleteTodo" and pass it to the Todo component
4. `handleCompleteTodo` will take the `id` of the todo as an argument which the user intends to complete.
5. Map out the todos, find the todo which matches the `id` and and update the todo object in array.

```jsx
const handleCompleteTodo = (id) => {
  const updatedTodos = todos.map((todo) => {
    if (todo.id === id) {
      todo.completed = !todo.completed;
    }
    return todo;
  });
  setTodos(updatedTodos);
  console.log(updatedTodos);
};
```

- we are looping over the todos and searching for one that matches the `id`
- when we find one that matches, we simply invert the value of `completed` property, simply by putting `!` in front of the the current value. if current value is true it will be inverted to false and false to true.

6. Apply css class to the div if the todo is completed.

   - Pass the `completed` prop to Todo Component

   ```jsx
   {
     todos.map((todo) => (
       <Todo
         key={todo.id}
         todoText={todo.text}
         id={todo.id}
         handleDeleteTodo={handleDeleteTodo}
         handleCompleteTodo={handleCompleteTodo}
         completed={todo.completed}
       />
     ));
   }
   ```

   - Take in the `completed` prop in Todo component and apply a `className` to the `div`.

   ```jsx
   const Todo = ({
     todoText,
     id,
     handleDeleteTodo,
     handleCompleteTodo,
     completed,
   }) => {
     return (
       <div
         className={completed ? "completed" : ""}
         onDoubleClick={() => handleCompleteTodo(id)}
       >
         {todoText} <button onClick={() => handleDeleteTodo(id)}>X</button>
       </div>
     );
   };
   ```

   Note - we are checking if the `completed` is `true`, if its we will apply 'completed` class to the div, if not we will add an empty string to class, in other words no class name.

   - in App.css add styles for the `completed` class.

   ```css
   .completed {
     text-decoration: line-through;
     color: red;
   }
   ```

   - In App.js file make sure you have imported the css file.

   ```jsx
   import "./App.css";
   ```

App component should look like this:

```jsx
function App() {
  const [todos, setTodos] = useState([]);

  const handleFormSubmit = (newTodo) => {
    const obj = { id: todos.length + 1, completed: false, text: newTodo };
    setTodos([...todos, obj]);
  };

  const handleDeleteTodo = (id) => {
    const filteredTodos = todos.filter((todo) => todo.id !== id);
    setTodos(filteredTodos);
  };

  const handleCompleteTodo = (id) => {
    const updatedTodos = todos.map((todo) => {
      if (todo.id === id) {
        todo.completed = !todo.completed;
      }
      return todo;
    });
    setTodos(updatedTodos);
    console.log(updatedTodos);
  };

  return (
    <div>
      <TodoForm handleFormSubmit={handleFormSubmit} />

      {todos.map((todo) => (
        <Todo
          key={todo.id}
          todoText={todo.text}
          id={todo.id}
          handleDeleteTodo={handleDeleteTodo}
          handleCompleteTodo={handleCompleteTodo}
          completed={todo.completed}
        />
      ))}
    </div>
  );
}
```

Your application should look like this:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_06_milestone_2/completedtodo.png">
</p>
