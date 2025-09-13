## 1. What are React Components?

**Theory:**
Components are the building blocks of a React application. They encapsulate the structure (JSX), logic (JavaScript), and styling (CSS) of a piece of UI. Components promote code reusability, modularity, and easier maintenance. There are two types of components: Functional and Class.

**Code Example:**

```js
const Header = () => <h1>Header</h1>;
const App = () => <Header />;
```

---

## 2. Functional Components

**Theory:**
Functional components are simple JavaScript functions that accept props as an argument and return JSX. They are lightweight, easier to read, and now support state and lifecycle features using hooks. Functional components are the preferred choice in modern React development.

**Code Example:**

```js
const Greeting = ({ name }) => <p>Hello, {name}!</p>;
```

---

## 3. Class Components

**Theory:**
Class components are ES6 classes that extend `React.Component`. They have access to state and lifecycle methods, making them suitable for complex components with more logic. However, with hooks, functional components can achieve similar functionality.

**Code Example:**

```js
class Greeting extends React.Component {
  render() {
    return <p>Hello, {this.props.name}!</p>;
  }
}
```

---

## 4. Props in React

**Theory:**
Props (properties) are read-only inputs passed from parent to child components. They allow customization of components without altering their internal logic. Props support a unidirectional data flow, ensuring predictable component behavior.

**Code Example:**

```js
const Button = ({ label }) => <button>{label}</button>;
const App = () => <Button label="Click Me" />;
```

---

## 5. State in React

**Theory:**
State represents the internal, mutable data of a component. Changing state triggers re-renders to update the UI. In class components, state is managed using `this.state` and `this.setState`. In functional components, the `useState` hook is used.

**Code Example:**

```js
const Counter = () => {
  const [count, setCount] = React.useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
};
```

---

## 6. Difference Between Props and State

**Theory:**

* Props are immutable and controlled by the parent component.
* State is mutable and managed internally by the component.
* Props allow data to flow down from parent to child, while state manages dynamic changes within the component itself.

---

## 7. Component Lifecycle Overview

**Theory:**
Every class component in React goes through a lifecycle: Mounting, Updating, and Unmounting. Lifecycle methods provide hooks to run code at specific stages, such as when a component is added to the DOM, updated, or removed.

---

## 8. Mounting Lifecycle Methods

**Theory:**
Mounting is the phase when a component is created and inserted into the DOM. Key methods include:

* `constructor()` – initializes state and binds methods.
* `static getDerivedStateFromProps()` – updates state based on props.
* `render()` – returns JSX to display.
* `componentDidMount()` – invoked after component is rendered; ideal for API calls and DOM manipulations.

**Code Example:**

```js
class App extends React.Component {
  componentDidMount() {
    console.log('Component mounted');
  }
  render() {
    return <h1>Hello</h1>;
  }
}
```

---

## 9. Updating Lifecycle Methods

**Theory:**
Updating occurs when state or props change. Important methods:

* `shouldComponentUpdate()` – decides whether to re-render.
* `getDerivedStateFromProps()` – updates state based on props.
* `render()` – re-renders UI.
* `componentDidUpdate()` – runs after update; useful for side-effects.

**Code Example:**

```js
componentDidUpdate(prevProps, prevState) {
  if(prevState.count !== this.state.count){
    console.log('Count updated');
  }
}
```

---

## 10. Unmounting Lifecycle Method

**Theory:**
`componentWillUnmount()` is called before a component is removed from the DOM. It is used for cleanup tasks like clearing timers or removing event listeners.

**Code Example:**

```js
componentWillUnmount() {
  clearInterval(this.timer);
}
```

---

## 11. useEffect Hook

**Theory:**
`useEffect` replaces most lifecycle methods in functional components. It can mimic `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` depending on its dependency array.

**Code Example:**

```js
React.useEffect(() => {
  console.log('Effect runs');
  return () => console.log('Cleanup');
}, [dependency]);
```

---

## 12. useState Hook

**Theory:**
`useState` manages local state in functional components. It returns a state variable and a function to update it.

**Code Example:**

```js
const [count, setCount] = React.useState(0);
```

---

## 13. Passing Functions as Props

**Theory:**
Functions can be passed as props to child components to allow child components to update parent state or trigger actions.

**Code Example:**

```js
const Child = ({ increment }) => <button onClick={increment}>Add</button>;
const Parent = () => {
  const [count, setCount] = React.useState(0);
  return <Child increment={() => setCount(count + 1)} />;
};
```

---

## 14. Conditional Rendering in Components

**Theory:**
Render different components or JSX based on conditions using ternary or logical && operators.

**Code Example:**

```js
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

## 15. Lists and Keys

**Theory:**
Keys are essential for rendering dynamic lists efficiently. They help React identify which items have changed, added, or removed, preventing unnecessary re-renders.

**Code Example:**

```js
const items = ['A', 'B', 'C'];
<ul>{items.map((item, index) => <li key={index}>{item}</li>)}</ul>
```
