# Setting Up a React Application using npx – Key Notes

## 1. Prerequisites Recap

- **Ensure Node.js is installed**, as it is required for React development.
- **Node.js is used to:**
  - Run a development server for React apps.
  - Convert React code into vanilla JavaScript for browsers.
  - Manage dependencies via **npm (Node Package Manager)**.
- **npm allows for:**
  - Installing and uninstalling packages.
  - Running a development server.
  - Creating and destroying React applications.
- **npx is bundled with npm** and is used to execute Node packages without installing them globally.

## 2. Setting Up a React App

### **Step 1: Create a GitHub Repository**
- Navigate to **GitHub** and **create a new repository**.
- Name the repository (e.g., `react`).
- This repository will be used for storing the project.

### **Step 2: Open the Repository Workspace**
- Once the repository is created, **open it in the workspace**.

### **Step 3: Run the Command to Create a React App**
- Open the **terminal** and run:
  ```sh
  npx create-react-app my-app --use-npm
  ``` 
# **This command:**
- **Creates** a new React app inside the `my-app` folder.
- **Installs** all necessary dependencies in the `node_modules` folder.

---

# **3. Running the React App**

## **Step 1: Change into the Project Directory**
- **Navigate into the newly created project folder by running:**

  ```sh
  cd my-app
  ``` 
- **Start the development server:**

  ```
  npm start
  ```
- **This launches the React app, making it ready for development**

# **4. Benefits of `create-react-app`**
- Provides all necessary boilerplate code for a React project.
- Developers can start quickly and remove unnecessary parts later.
- Uses npm as the package manager (default is Yarn, but `--use-npm` ensures npm is used).

# **5. Summary**
- **Node.js & npm** are crucial for React development.
- **npx create-react-app** sets up a React project with minimal effort.
- **npm start** runs the development server.
- The next step is learning about **React Developer Tools** for debugging.

# React Developer Tools - Summary Notes
## 1️⃣ Introduction to React Developer Tools
- A **Chrome Extension** for inspecting and debugging React applications.
- Helps view **React components, props, and state**.
- Similar to Chrome DevTools but specifically for **React apps**.
- Useful for testing **changes, debugging errors, and optimizing performance**.

## 2️⃣ Installing React Developer Tools
- **Search for "React Developer Tools"** in the Chrome Web Store.
- Click **"Add to Chrome"** and **pin it to the toolbar** for quick access.
- May require **restarting Chrome** after installation.

## 3️⃣ Why Use React Developer Tools?
- Lets you inspect **React components**, not just the HTML output.
- Identifies if a site uses React:
- - **Blue icon** = Production build (optimized).
- - **Orange icon** = Development build (unoptimized).
- Helps **debug component props and state** in real-time.

## 4️⃣ Using React Developer Tools
- The **Components tab** shows:
- - React elements and their **props (properties)**.
- - How components are structured in the app.
- The **Element Picker** lets you:
- - Select components directly from the page.
- - View **props and state** of selected components.
- On complex sites (e.g., **Twitter**), component names may be minified in production mode.

## 5️⃣ Performance Debugging Features
- **Highlight updates when components render:**
- - Shows when components re-render using **visual highlights**.
- - Helps find **unnecessary re-renders** that may slow the app.
- **Profiler tab** (for advanced users):
- - **Measures render time** for components.
- - Helps **optimize slow components**.

## 6️⃣ Key Takeaways
- React Developer Tools work alongside **Chrome DevTools** for debugging React apps.
- Useful for **inspecting props, debugging performance, and optimizing rendering**.
- Future lessons will cover building React components and adding interactivity.

# React Components - Summary Notes
## 1️⃣ Recap of Lesson 1
- Learned what React is and its benefits.
- Understood how a React application works.
- Created a React app from scratch using `npx create-react-app`.
- 
## 2️⃣ Introduction to React Components
- React apps are made up of **components**.
- Components can be **functional (stateless)** or **class-based (stateful)**.
- React **hooks** allow functional components to manage state and behave like class components.
  
## 3️⃣ Types of Components in React
**A) Functional (Stateless) Components**
- A *JavaScript function* that returns JSX (React’s HTML-like syntax).
- Uses *props* (properties) to customize output.
- Example:
``` js
  function FunctionalGreeting(props) {
    return <h1>Hello, {props.name}!</h1>;
  }
```
- Once rendered, functional components do not change unless their props update.
Best for static UI elements that don’t need interactivity.

**B) Class (Stateful) Components**
- Uses state to store dynamic values.
- Can change over time, unlike functional components.
- - Example:
``` js
  class StatefulGreeting extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  setCount = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <h1>Count: {this.state.count}</h1>
        <button onClick={this.setCount}>Increase</button>
      </div>
    );
  }
}
```
- Best for ***components that need interactivity*** (eg, buttons, forms, counters).

## 4️⃣ Props vs. State
| Feature           | Functional Component (Props)  | Class Component (State)  |
|------------------|-----------------------------|--------------------------|
| **Data Type**    | Passed in as properties     | Stored internally        |
| **Changeable?**  | ❌ No (static)              | ✅ Yes (dynamic)         |
| **Best For**     | Displaying static content   | Interactive UI elements  |

## 5️⃣ React Hooks: The Modern Alternative
- **Hooks let functional components use state, like class components.**
- `useState` is the most common hook:
```js
  import { useState } from "react";

  function HooksCounter() {
    const [count, setCount] = useState(0);

    return (
      <div>
        <h1>Count: {count}</h1>
        <button onClick={() => setCount(count + 1)}>Increase</button>
      </div>
    );
  }
```

- **Advantages of Hooks over Class Components:**
- - **Less code** → No need for a constructor or this keyword.
- - **Easier to manage state** in simple functions.
- - **Becoming the standard** in modern React development.

## 6️⃣ When to Use Each Type of Component
**✅ Use Functional Components when:**

- The component *does not need state* (static content).
- The component only *renders based on props*.
- 
**✅ Use Class Components when:**

- The component *needs to manage its own state*.
- There is *complex logic that requires lifecycle methods*.
- 
**✅ Use Hooks (Functional + State) when:**

- You want the *simplicity of functional components* but *need interactivity*.
- You want to avoid the complexity of *class components* (e.g., constructors, this.state).

## 7️⃣ Next Steps
- Write a functional component from scratch.
- Learn more about how props work in upcoming lessons.
- Later, transition to using hooks for stateful behavior.

# Creating a Functional Component in React - Notes & Instructions

## 1️⃣ Recap of Previous Lesson

- Learned about stateless functional components and stateful class components.
- Functional components can become stateful using React hooks.

## 2️⃣ Setting Up Your Workspace
- ✅ Prerequisites:

- - Ensure you have a React app set up (my-app folder).
- - Open your workspace in VS Code.
- - Start the server:
```sh
cd my-app
npm start
```
- Live reloading should work, but if not, refresh the browser manually.

## 3️⃣ Creating a Functional Component from Scratch
📌 Follow these steps:

**Step 1: Create a New Component File**
- 1. Inside the src/ directory, create a new folder:
`components/`

- 2. Inside components/, create a new file:
`FunctionalGreeting.js`

**Step 2: Write a Basic Functional Component**
- 1. Open FunctionalGreeting.js.
- 2. Add this code:
```js

import React from "react";

function FunctionalGreeting() {
  return <h1>Hello from React!</h1>;
}

export default FunctionalGreeting;
```

**✅ Explanation:**

- import React from "react"; → Gives access to React functions.
- Function returns JSX (<h1>Hello from React!</h1>) → This is the UI output.
- export default FunctionalGreeting; → Makes it available for import in other files.

**Step 3: Import & Use the Component in App.js**
- 1. Open src/App.js.
- 2. Import the FunctionalGreeting component:
```js

import FunctionalGreeting from "./components/FunctionalGreeting";
```

- 3. Replace the existing <h1> with your new component:
``` js
function App() {
  return (
    <div>
      <FunctionalGreeting />
    </div>
  );
}
export default App;
```

- 4. Save the file → React automatically updates the browser.
  
**✅ Why Self-Closing?**

- Since FunctionalGreeting does not wrap other components, it can be self-closed like:
```js
<FunctionalGreeting />
```
- If it wrapped content, you would write:
```js

<FunctionalGreeting>Content here</FunctionalGreeting>
```

## 4️⃣ Converting to an Arrow Function (Modern Approach)
📌 Refactor FunctionalGreeting.js into an arrow function:

```js
import React from "react";

const FunctionalGreeting = () => <h1>Hello from React!</h1>;

export default FunctionalGreeting;
```

**✅ Arrow Function Benefits:**

- Less code, cleaner syntax.
- No need for the return statement if it's a single-line function.
- You can use either method, but arrow functions are preferred in modern React.

## 5️⃣ Understanding export default
- Why use export default?

- - Allows you to import the component with any name.
- - Example:
```js

import Greeting from "./components/FunctionalGreeting";
```
- - Though renaming is possible, it's best practice to keep the original component name.
- Named exports (export { ComponentName }) exist but will be covered in more advanced lessons.

## 6️⃣ Key Takeaways
✅ Functional components are simple JavaScript functions that return JSX.
✅ They are reusable and independent.
✅ Must be exported and imported to be used in other files.
✅ Arrow functions offer a cleaner syntax but are optional.
✅ This is a stateless functional component—it does not change dynamically.

# Using Props in Functional Components - Notes & Instructions

## 1️⃣ Recap of the Previous Lesson
- Created a basic functional component (FunctionalGreeting.js).
- Learned how to export, import, and render components.
- Components currently display static content.

## 2️⃣ Why Use Props?
- Props (short for properties) allow components to become dynamic.
- They work like attributes in HTML but are fully customizable.
- Instead of rendering the same greeting every time, we can pass different values to the component.
- **Props are Parameters you pass into your React component in order to tell it what to render, and how.** 

## 3️⃣ Setting Up a Component with Props

**Step 1: Create a New Component**
📌 Duplicate the existing component and rename it:

1. Copy FunctionalGreeting.js
2. Rename it to FunctionalGreetingWithProps.js.
3. Change the function and export statement inside it:
4. 
```js
import React from "react";

function FunctionalGreetingWithProps() {
  return <h1>Hello!</h1>;
}

export default FunctionalGreetingWithProps;
```

**Step 2: Import & Use the Component in App.js**

1. Open App.js and import the new component:
```js

import FunctionalGreetingWithProps from "./components/FunctionalGreetingWithProps";
```

2. Render the new component below the original one:
```js

<FunctionalGreetingWithProps />
```

3. Save the file → Check if both components render in the browser.
4. 
✅ At this stage, the new component is still static.

## 4️⃣ Adding & Using Props in a Component
**Step 1: Pass Props to the Component in App.js**
- Modify the component tag to pass a prop:

```js

<FunctionalGreetingWithProps greeting="Nice to meet you!" />
```
✅ Now the component receives a greeting prop, but it won’t display it yet.

**Step 2: Retrieve & Use Props in the Component**
1. Open FunctionalGreetingWithProps.js.
2. Modify the function to accept props as a parameter:
```js

function FunctionalGreetingWithProps(props) {
  return <h1>{props.greeting}</h1>;
}
```
3. Save the file → The browser should now display:
```css
Nice to meet you!
```
✅ The component now dynamically displays different text based on props.

## 5️⃣ Adding Multiple Props
1. Modify App.js to pass more props:
```js
<FunctionalGreetingWithProps greeting="Nice to meet you!" name="Alex" age={25} />
```
2. Modify FunctionalGreetingWithProps.js to display all props:
```js

function FunctionalGreetingWithProps(props) {
  return (
    <div>
      <h1>{props.greeting}</h1>
      <p>Name: {props.name}</p>
      <p>Age: {props.age}</p>
    </div>
  );
}
```
3. Save the file → Now the browser should display:
```vbnet

Nice to meet you!
Name: Alex
Age: 25
```
✅ You can now pass and display multiple props dynamically.

## 6️⃣ Understanding How Props Work
- Props are passed like HTML attributes:
```js
<ComponentName propName="value" />
```

- Props are received as an object (props) inside the component.
- Use curly braces ({}) to display props in JSX:
```js
<h1>{props.greeting}</h1>
```
✅ Props allow the same component to display different content depending on the values passed in.

## 7️⃣ Challenge: Convert to an Arrow Function
- Try refactoring FunctionalGreetingWithProps.js to use an arrow function:
```js

const FunctionalGreetingWithProps = (props) => (
  <div>
    <h1>{props.greeting}</h1>
    <p>Name: {props.name}</p>
    <p>Age: {props.age}</p>
  </div>
);

export default FunctionalGreetingWithProps;
```
✅ This achieves the same result but with cleaner syntax.

## 8️⃣ Key Takeaways
✅ Props make functional components dynamic.
✅ Props are passed like HTML attributes and accessed via props in the component.
✅ Use curly braces ({}) to display prop values inside JSX.
✅ Multiple props can be passed and used together.
✅ Arrow functions offer a shorter syntax but are optional.

