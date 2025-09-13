## 1. React Performance Optimization Overview

**Theory:**
Optimizing React performance involves reducing unnecessary renders, minimizing re-calculations, and managing state efficiently. Techniques include memoization, code splitting, lazy loading, and using React DevTools to profile components.

---

## 2. React.memo

**Theory:**
`React.memo` is a higher-order component that prevents functional components from re-rendering if their props haven’t changed. It is useful for expensive or frequently re-rendered components.

**Code Example:**

```js
const MyComponent = React.memo(({ value }) => <div>{value}</div>);
```

---

## 3. useMemo Hook

**Theory:**
`useMemo` memoizes the result of an expensive function, recomputing only when dependencies change. It helps reduce expensive recalculations on every render.

**Code Example:**

```js
const computedValue = useMemo(() => expensiveCalculation(a, b), [a, b]);
```

---

## 4. useCallback Hook

**Theory:**
`useCallback` memoizes a function instance so that it doesn’t get recreated on every render. This is especially useful when passing functions to child components wrapped in `React.memo`.

**Code Example:**

```js
const handleClick = useCallback(() => setCount(count + 1), [count]);
```

---

## 5. Code Splitting

**Theory:**
Code splitting breaks a React app into smaller chunks loaded on demand, reducing initial load time. React supports dynamic imports with `React.lazy`.

**Code Example:**

```js
const LazyComponent = React.lazy(() => import('./Component'));
<Suspense fallback={<div>Loading...</div>}><LazyComponent /></Suspense>
```

---

## 6. Lazy Loading Components

**Theory:**
Lazy loading delays rendering of components until they are needed. This improves performance for large applications by reducing bundle size.

---

## 7. Profiling Components

**Theory:**
React DevTools Profiler helps identify slow components and unnecessary re-renders. Use the Profiler to track render durations and optimize performance.

---

## 8. Virtualization

**Theory:**
Virtualization renders only visible items in a large list or table, reducing DOM nodes and improving performance. Libraries like `react-window` or `react-virtualized` are commonly used.

---

## 9. Avoiding Anonymous Functions in JSX

**Theory:**
Anonymous functions inside JSX can cause unnecessary re-renders because a new function reference is created each time. Use `useCallback` or define functions outside JSX.

---

## 10. React Key Prop Importance

**Theory:**
The `key` prop identifies list items uniquely, allowing React to optimize DOM updates. Avoid using indexes if the list can change dynamically.

---

## 11. Testing Overview

**Theory:**
Testing ensures code reliability and correctness. React testing libraries include Jest, React Testing Library, and Enzyme. Focus on unit testing components, hooks, and interactions.

---

## 12. Unit Testing React Components

**Theory:**
Unit testing involves testing individual components in isolation to verify that they render and behave correctly with different props and states.

**Code Example:**

```js
import { render } from '@testing-library/react';
import App from './App';
render(<App />);
```

---

## 13. Testing Events

**Theory:**
Simulate user interactions like clicks or typing to test component behavior using React Testing Library’s `fireEvent` or `userEvent`.

**Code Example:**

```js
fireEvent.click(getByText('Submit'));
```

---

## 14. Snapshot Testing

**Theory:**
Snapshot testing captures the rendered component output and compares it in future runs. Useful for detecting unexpected changes in UI.

**Code Example:**

```js
const { asFragment } = render(<App />);
expect(asFragment()).toMatchSnapshot();
```

---

## 15. Mocking API Calls

**Theory:**
Mocking API calls allows testing components that depend on external data without making real network requests.

**Code Example:**

```js
jest.mock('./api');
api.fetchData.mockResolvedValue({data: []});
```
