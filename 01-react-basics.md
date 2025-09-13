## 1. What is React and why is it used?

**Theory:**
React is a declarative, efficient, and flexible JavaScript library for building user interfaces, primarily for single-page applications. It allows developers to create reusable UI components, which makes the development process more organized and maintainable. React uses a virtual DOM to update only the parts of the UI that change, improving performance significantly compared to direct DOM manipulation.

**Code Example:**

```js
import React from 'react';
import ReactDOM from 'react-dom';

const App = () => <h1>Hello React!</h1>;

ReactDOM.render(<App />, document.getElementById('root'));
```

---

## 2. What is JSX?

**Theory:**
JSX (JavaScript XML) is a syntax extension for JavaScript that allows developers to write HTML-like code directly within JavaScript. JSX makes it easier to visualize the structure of the UI components and enables embedding JavaScript expressions inside curly braces `{}`. Although it looks like HTML, JSX is transformed into React.createElement calls under the hood.

**Code Example:**

```js
const element = <h1>Hello JSX</h1>;
```

---

## 3. Difference between JSX and HTML

**Theory:**
While JSX resembles HTML, there are key differences:

* `className` is used instead of `class` because `class` is a reserved keyword in JavaScript.
* `htmlFor` is used instead of `for` in labels.
* JavaScript expressions can be embedded using `{}`.
* JSX is compiled to JavaScript, making it possible to include dynamic content and logic directly within the markup.

**Code Example:**

```js
const element = <div className="container">The sum is {2 + 3}</div>;
```

---

## 4. What are Components?

**Theory:**
Components are the building blocks of a React application. They allow the UI to be broken down into independent, reusable pieces. Components can be functional (stateless) or class-based (stateful) and can receive inputs in the form of props. Using components makes your code modular, easier to maintain, and scalable.

**Code Example:**

```js
const Header = () => <h1>Header</h1>;
const App = () => <Header />;
```

---

## 5. Functional vs Class Components

**Theory:**
Functional components are simple JavaScript functions that return JSX. They are easier to read and write and can now use state and lifecycle features via hooks. Class components are ES6 classes that extend `React.Component` and have built-in lifecycle methods and state management. Functional components are recommended for most cases due to their simplicity and performance.

**Code Example:**

```js
// Functional Component
const App = () => <h1>Hello</h1>;

// Class Component
class App extends React.Component {
  render() {
    return <h1>Hello</h1>;
  }
}
```

---

## 6. What are Props?

**Theory:**
Props (short for properties) are read-only inputs that allow data to be passed from a parent component to a child component. They help in making components reusable by parameterizing them with different data. Props cannot be modified by the child component, ensuring a unidirectional data flow and predictable behavior.

**Code Example:**

```js
const Child = ({ name }) => <p>Hello {name}</p>;
const Parent = () => <Child name="John" />;
```

---

## 7. State in React

**Theory:**
State represents the internal, mutable data of a component. When state changes, React re-renders the component to reflect the updated data. In functional components, state is managed using the `useState` hook, while in class components, it is managed via `this.state`.

**Code Example:**

```js
import { useState } from 'react';
const Counter = () => {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
};
```

---

## 8. Difference between State and Props

**Theory:**
Props are immutable and passed from parent to child components. State is mutable and managed internally within a component. Props are used for configuration, while state represents dynamic data that changes over time.

---

## 9. Controlled vs Uncontrolled Components

**Theory:**
Controlled components have their form data controlled by React state. Uncontrolled components store their data in the DOM and can be accessed using refs. Controlled components offer better control and are generally preferred in React forms.

**Code Example:**

```js
// Controlled
<input value={value} onChange={e => setValue(e.target.value)} />

// Uncontrolled
<input ref={inputRef} />
```

---

## 10. Handling Events in React

**Theory:**
React wraps browser events into a SyntheticEvent object to ensure cross-browser compatibility. Event handlers are passed as functions in camelCase syntax. You can pass additional parameters using arrow functions.

**Code Example:**

```js
<button onClick={() => alert('Clicked!')}>Click Me</button>
```

---

## 11. Conditional Rendering

**Theory:**
You can render different UI elements based on certain conditions using JavaScript conditional operators such as ternary operators or logical &&.

**Code Example:**

```js
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

## 12. Rendering Lists

**Theory:**
Arrays of data can be rendered using the `map()` function. Each element must have a unique `key` prop to help React identify which items have changed, added, or removed, improving performance.

**Code Example:**

```js
const items = ['A', 'B', 'C'];
<ul>{items.map((item, index) => <li key={index}>{item}</li>)}</ul>
```

---

## 13. Fragments

**Theory:**
Fragments allow grouping multiple elements without adding extra nodes to the DOM. This helps in keeping the DOM clean and avoiding unnecessary wrapper elements.

**Code Example:**

```js
<>
  <h1>Title</h1>
  <p>Paragraph</p>
</>
```

---

## 14. Forms in React

**Theory:**
Forms in React can be controlled using state. Always prevent the default form submission using `event.preventDefault()` and handle the submission logic in your code. This gives full control over user input.

**Code Example:**

```js
<form onSubmit={handleSubmit}>
  <input value={name} onChange={e => setName(e.target.value)} />
</form>
```

---

## 15. Refs and useRef

**Theory:**
Refs provide a way to access DOM nodes or React elements directly. They can be used for managing focus, text selection, or integrating with third-party DOM libraries. `useRef` is the hook-based approach in functional components.

**Code Example:**

```js
const inputRef = useRef();
<input ref={inputRef} />
```

---

## 16. Lifting State Up

**Theory:**
When multiple components need to share state, it is best to lift the state to their nearest common ancestor. This avoids duplicating state and ensures consistent data flow.

**Code Example:**

```js
const Parent = () => {
  const [value, setValue] = useState('');
  return <><Child1 value={value} /><Child2 setValue={setValue} /></>;
};
```

---

## 17. useEffect Hook

**Theory:**
`useEffect` is used to handle side-effects such as data fetching, subscriptions, or manually updating the DOM. It runs after the component renders and can be controlled with dependency arrays.

**Code Example:**

```js
useEffect(() => {
  console.log('Component mounted');
}, []);
```

---

## 18. useEffect Dependencies

**Theory:**
The dependency array controls when the effect runs:

* `[]` – runs once after the first render
* No array – runs after every render
* `[var]` – runs when `var` changes

---

## 19. Cleanup in useEffect

**Theory:**
Return a cleanup function inside `useEffect` to clear timers, subscriptions, or event listeners when the component unmounts or dependencies change. This prevents memory leaks.

**Code Example:**

```js
useEffect(() => {
  const id = setInterval(tick, 1000);
  return () => clearInterval(id);
}, []);
```

---

## 20. Synthetic Events

**Theory:**
React wraps native events into a SyntheticEvent to provide a consistent interface across all browsers. Synthetic events are pooled for performance and have the same interface as native events.



