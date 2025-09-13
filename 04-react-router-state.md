## 1. What is React Router?

**Theory:**
React Router is a standard library for routing in React. It enables navigation between different views or components in a single-page application (SPA) without refreshing the browser. It maintains the UI in sync with the URL.

**Code Example:**

```js
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import Home from './Home';
import About from './About';

const App = () => (
  <Router>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  </Router>
);
```

---

## 2. Difference between BrowserRouter and HashRouter

**Theory:**

* `BrowserRouter` uses the HTML5 history API to create clean URLs.
* `HashRouter` uses URL hash (`#`) to simulate navigation. It is useful for static file hosting without server-side support.

---

## 3. Link vs NavLink

**Theory:**

* `Link` navigates to a route without reloading the page.
* `NavLink` is similar but can apply active styles when the link is active.

**Code Example:**

```js
<NavLink to="/about" activeClassName="active">About</NavLink>
```

---

## 4. useParams Hook

**Theory:**
`useParams` returns an object of key/value pairs from the URL parameters, allowing dynamic routing.

**Code Example:**

```js
const { id } = useParams();
```

---

## 5. useNavigate Hook

**Theory:**
`useNavigate` is used to programmatically navigate to different routes in a functional component.

**Code Example:**

```js
const navigate = useNavigate();
navigate('/home');
```

---

## 6. useLocation Hook

**Theory:**
`useLocation` returns the current location object, useful for accessing query parameters or pathname.

**Code Example:**

```js
const location = useLocation();
console.log(location.pathname);
```

---

## 7. State Management in React

**Theory:**
State management is handling the state of the application efficiently. React has local state, Context API, and external libraries like Redux, Zustand, or MobX.

---

## 8. Redux Basics

**Theory:**
Redux is a predictable state container for JavaScript apps. It centralizes state, making it easier to manage, debug, and share across components.

**Code Example:**

```js
import { createStore } from 'redux';
const reducer = (state = {count:0}, action) => {
  switch(action.type){
    case 'INCREMENT': return {count: state.count + 1};
    default: return state;
  }
};
const store = createStore(reducer);
```

---

## 9. Redux Actions and Reducers

**Theory:**
Actions are payloads of information that send data from the app to the store. Reducers specify how the state changes based on actions.

**Code Example:**

```js
const increment = () => ({ type: 'INCREMENT' });
function reducer(state, action){
  switch(action.type){
    case 'INCREMENT': return {...state, count: state.count+1};
    default: return state;
  }
}
```

---

## 10. Redux Provider

**Theory:**
The `Provider` component makes the Redux store available to all nested components using `connect` or hooks.

**Code Example:**

```js
import { Provider } from 'react-redux';
<Provider store={store}><App /></Provider>
```

---

## 11. useSelector Hook

**Theory:**
`useSelector` allows functional components to extract data from the Redux store.

**Code Example:**

```js
const count = useSelector(state => state.count);
```

---

## 12. useDispatch Hook

**Theory:**
`useDispatch` returns a reference to the Redux dispatch function to send actions to the store.

**Code Example:**

```js
const dispatch = useDispatch();
dispatch({type: 'INCREMENT'});
```

---

## 13. Context API

**Theory:**
Context API provides a way to share state globally across the component tree without passing props manually at every level.

**Code Example:**

```js
const ThemeContext = React.createContext();
<ThemeContext.Provider value="dark"><App /></ThemeContext.Provider>
```

---

## 14. Combining Context with useReducer

**Theory:**
For complex state management, combining Context API with useReducer allows centralized logic without external libraries.

**Code Example:**

```js
const [state, dispatch] = useReducer(reducer, initialState);
<Context.Provider value={{state, dispatch}}></Context.Provider>
```
