# React

## 1. Environment Setup in VSCode

Before coding:

Install Node.js (LTS version recommended): https://nodejs.org

Open VSCode → Install extensions:

ES7+ React/Redux/React-Native snippets

Prettier - Code Formatter

## 2. Update npm first (since it’s suggesting it)

npm install -g npm@latest

After this, restart your terminal so the update takes effect.

## 3. Run the create command again

From inside C:\React_Sample1:

npx create-react-app@latest my-app

💡 Adding @latest ensures you get the newest version.

## 4. Wait for the installation

It will download React, ReactDOM, and other dependencies — this can take a few minutes.

If it succeeds, you’ll see something like:

Success! Created my-app at C:\React_Sample1\my-app

## 5. Enter and run

cd my-app

npm start

This should open your browser at http://localhost:3000 with the default React page.

## 6. Learn React with Samples

### 6.1. First Component — Hello World

📂 File: src/App.js

```react
import React from "react";

function App() {
  return <h1>Hello, React!</h1>;
}

export default App;
```

💡 Feature learned: JSX syntax, functional component, export default.

### 6.2. Props — Passing Data to Components

📂 File: src/App.js

import React from "react";
import Greeting from "./Greeting";

function App() {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
    </div>
  );
}

export default App;

📂 File: src/Greeting.js

import React from "react";

function Greeting({ name }) {
  return <p>Hello, {name}!</p>;
}

export default Greeting;

💡 Feature learned: Props, reusable components.

### 6.3. State — Managing Data Inside Components

📂 File: src/Counter.js

import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;

💡 Feature learned: useState hook, event handling.

### 6.4. Effect — Running Code on Render or Data Change

📂 File: src/Timer.js

```react
import React, { useState, useEffect } from "react";

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const timer = setInterval(() => setSeconds(s => s + 1), 1000);
    return () => clearInterval(timer); // cleanup on unmount
  }, []);

  return <p>Seconds passed: {seconds}</p>;
}

export default Timer;
```

💡 Feature learned: useEffect hook, cleanup functions.

### 6.5. Conditional Rendering

```react
import React, { useState } from "react";

function LoginControl() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  return (
    <div>
      {isLoggedIn ? <h2>Welcome back!</h2> : <h2>Please log in</h2>}
      <button onClick={() => setIsLoggedIn(!isLoggedIn)}>
        {isLoggedIn ? "Logout" : "Login"}
      </button>
    </div>
  );
}

export default LoginControl;
```

💡 Feature learned: Ternary operator for conditional UI.

### 6.6. Lists and Keys

```react
import React from "react";

function TodoList() {
  const todos = ["Learn React", "Build a project", "Get a job"];

  return (
    <ul>
      {todos.map((todo, index) => (
        <li key={index}>{todo}</li>
      ))}
    </ul>
  );
}

export default TodoList;
```

💡 Feature learned: Array .map() in JSX, keys for list items.

### 6.7. Bringing It All Together

📂 File: src/App.js

```javascript
import React from "react";
import Greeting from "./Greeting";
import Counter from "./Counter";
import Timer from "./Timer";
import LoginControl from "./LoginControl";
import TodoList from "./TodoList";

function App() {
  return (
    <div>
      <Greeting name="Developer" />
      <Counter />
      <Timer />
      <LoginControl />
      <TodoList />
    </div>
  );
}

export default App;
```
