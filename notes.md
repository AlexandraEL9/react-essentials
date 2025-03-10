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
