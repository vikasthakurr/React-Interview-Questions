## 1. What are React Hooks?

**Theory:**
Hooks are special functions introduced in React 16.8 that allow functional components to use state and other React features without writing class components. They simplify code, encourage reuse of logic, and improve readability.

**Code Example:**

```js
import React, { useState, useEffect } from 'react';
const Counter = () => {
  const [count, setCount] = useState(0);
  useEffect(() => {
    console.log('Count changed:', count);
  }, [count]);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
};
```

---

## 2. useState Hook

**Theory:**
`useState` manages local state in functional components. It returns an array with the current state and a function to update it. Multiple state variables can be declared individually.

**Code Example:**

```js
const [name, setName] = useState('John');
```

---

## 3. useEffect Hook

**Theory:**
`useEffect` handles side-effects in functional components. It can run after renders and optionally clean up resources to prevent memory leaks. Its behavior is controlled using a dependency array.

**Code Example:**

```js
useEffect(() => {
  console.log('Component mounted or updated');
  return () => console.log('Cleanup');
}, [dependency]);
```

---

## 4. useContext Hook

**Theory:**
`useContext` allows consuming context values in functional components without using Consumer components. It simplifies state sharing across the component tree.

**Code Example:**

```js
const ThemeContext = React.createContext('light');
const App = () => {
  const theme = React.useContext(ThemeContext);
  return <div>Current theme: {theme}</div>;
};
```

---

## 5. useReducer Hook

**Theory:**
`useReducer` is an alternative to `useState` for managing complex state logic, especially with multiple sub-values or actions. It mimics Redux-like reducers inside functional components.

**Code Example:**

```js
const initialState = {count: 0};
function reducer(state, action) {
  switch(action.type){
    case 'increment': return {count: state.count + 1};
    default: return state;
  }
}
const Counter = () => {
  const [state, dispatch] = useReducer(reducer, initialState);
  return <button onClick={() => dispatch({type: 'increment'})}>{state.count}</button>;
};
```

---

## 6. useMemo Hook

**Theory:**
`useMemo` memoizes the result of an expensive computation, recomputing only when dependencies change. This improves performance by avoiding unnecessary recalculations.

**Code Example:**

```js
const memoizedValue = useMemo(() => computeExpensive(value), [value]);
```

---

## 7. useCallback Hook

**Theory:**
`useCallback` memoizes a function instance so that it doesn't get recreated on every render. This is useful when passing functions to optimized child components.

**Code Example:**

```js
const memoizedCallback = useCallback(() => doSomething(a, b), [a, b]);
```

---

## 8. Custom Hooks

**Theory:**
Custom hooks are reusable functions that encapsulate logic using built-in hooks. They allow sharing behavior across multiple components without repeating code.

**Code Example:**

```js
function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);
  const increment = () => setCount(count + 1);
  return {count, increment};
}
```

---

## 9. useRef Hook

**Theory:**
`useRef` returns a mutable ref object that persists across renders. It is commonly used to access DOM nodes or store mutable values without triggering re-renders.

**Code Example:**

```js
const inputRef = useRef();
<input ref={inputRef} />
```

---

## 10. useLayoutEffect Hook

**Theory:**
`useLayoutEffect` runs synchronously after DOM mutations but before the browser paints. It is useful for reading layout or performing measurements before rendering.

**Code Example:**

```js
useLayoutEffect(() => {
  console.log('DOM updated, before paint');
}, []);
```

---

## 11. useImperativeHandle Hook

**Theory:**
`useImperativeHandle` customizes the instance value exposed when using `ref` with `forwardRef`. It is useful for exposing imperative methods from child components.

**Code Example:**

```js
useImperativeHandle(ref, () => ({
  focus: () => inputRef.current.focus()
}));
```

---

## 12. Forwarding Refs

**Theory:**
`forwardRef` allows passing refs from parent components to child components to access DOM nodes or child instance methods.

**Code Example:**

```js
const Input = React.forwardRef((props, ref) => <input ref={ref} />);
```
