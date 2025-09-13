## 1. Controlled vs Uncontrolled Components

**Theory:**
Controlled components have their form data managed by React state, allowing predictable behavior and validation. Uncontrolled components rely on the DOM for state, often using refs to access values.

**Code Example:**

```js
// Controlled
const [value, setValue] = useState('');
<input value={value} onChange={e => setValue(e.target.value)} />

// Uncontrolled
const inputRef = useRef();
<input ref={inputRef} />
```

---

## 2. Handling Dynamic Forms

**Theory:**
Dynamic forms are forms where fields can be added or removed at runtime. This is managed by keeping form structure in state and rendering fields dynamically.

**Code Example:**

```js
const [fields, setFields] = useState([{name:''}]);
fields.map((f, i) => <input key={i} value={f.name} onChange={e => updateField(i, e.target.value)} />)
```

---

## 3. Debouncing Input in React

**Theory:**
Debouncing limits the rate a function is called, often used with search inputs to reduce API calls.

**Code Example:**

```js
const debounce = (fn, delay) => {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
};
```

---

## 4. Throttling in React

**Theory:**
Throttling limits a function to execute once every X milliseconds, useful for scroll or resize events.

**Code Example:**

```js
const throttle = (fn, limit) => {
  let inThrottle;
  return (...args) => {
    if(!inThrottle){
      fn(...args);
      inThrottle = true;
      setTimeout(() => inThrottle = false, limit);
    }
  };
};
```

---

## 5. Error Boundaries

**Theory:**
Error boundaries catch JavaScript errors in child components and display fallback UI instead of crashing the entire app. Only class components can be error boundaries.

**Code Example:**

```js
class ErrorBoundary extends React.Component {
  state = {hasError:false};
  static getDerivedStateFromError() { return {hasError:true}; }
  render() { return this.state.hasError ? <h1>Error occurred</h1> : this.props.children; }
}
```

---

## 6. Higher-Order Components (HOC)

**Theory:**
HOCs are functions that take a component and return a new enhanced component. They are used for reusing logic like authentication, theming, or data fetching.

**Code Example:**

```js
const withLogger = Wrapped => props => {
  console.log('Rendering', Wrapped.name);
  return <Wrapped {...props} />;
};
```

---

## 7. Render Props

**Theory:**
Render props involve passing a function as a prop to a component to dynamically render content.

**Code Example:**

```js
const DataProvider = ({ render }) => {
  const data = [1,2,3];
  return render(data);
};
<DataProvider render={data => <ul>{data.map(d => <li>{d}</li>)}</ul>} />
```

---

## 8. Portals

**Theory:**
Portals allow rendering a component outside its parent DOM hierarchy, useful for modals, tooltips, or notifications.

**Code Example:**

```js
ReactDOM.createPortal(<Modal />, document.getElementById('modal-root'));
```

---

## 9. Refs Forwarding

**Theory:**
`forwardRef` allows parent components to pass a ref down to a child component to access its DOM node.

**Code Example:**

```js
const Input = React.forwardRef((props, ref) => <input ref={ref} />);
```
