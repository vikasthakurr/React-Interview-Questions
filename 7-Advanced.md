## 1. React Fiber Architecture

**Theory:**
React Fiber is the reimplementation of React’s core algorithm for rendering. It allows incremental rendering, enabling React to pause, abort, or resume work, improving performance and responsiveness in complex applications.

---

## 2. Reconciliation in React

**Theory:**
Reconciliation is React’s process of updating the DOM with minimal operations. It compares the virtual DOM with previous renders and only applies necessary changes.

---

## 3. Concurrent Mode

**Theory:**
Concurrent Mode allows React to interrupt rendering to prioritize more important updates. It improves app responsiveness and allows better handling of heavy UI operations.

---

## 4. Suspense for Data Fetching

**Theory:**
Suspense is not only for lazy-loaded components; it can pause rendering while waiting for asynchronous data. This simplifies async UI handling and avoids loading states scattered across components.

---

## 5. Lazy Loading with Suspense

**Theory:**
React.lazy allows components to be loaded on demand. When combined with Suspense, it provides a fallback UI while the component loads.

---

## 6. useTransition Hook

**Theory:**
`useTransition` lets you mark updates as non-urgent, allowing urgent updates (like typing) to render immediately while deferred updates (like filtering a list) can render later.

---

## 7. useDeferredValue Hook

**Theory:**
`useDeferredValue` allows deferring a value until less urgent rendering tasks are done, useful for optimizing large lists or expensive calculations without blocking UI.

---

## 8. useId Hook

**Theory:**
`useId` generates stable unique IDs for accessibility or dynamic components, preventing hydration mismatches in SSR apps.

---

## 9. useImperativeHandle Hook

**Theory:**
`useImperativeHandle` customizes the instance value exposed by `forwardRef`. It allows controlling what methods/values are accessible from parent components.

---

## 10. Error Boundaries in Depth

**Theory:**
Advanced error boundaries can log errors to external services, recover gracefully, and provide fallback UIs for specific sections of the app.

---

## 11. Portals and Event Bubbling

**Theory:**
Events originating in a portal still bubble through the React component tree, allowing parent components to catch events even if rendered elsewhere in the DOM.

---

## 12. Context Performance Optimization

**Theory:**
Excessive context updates can cause re-renders. Use memoization, split context, or use selectors to avoid unnecessary re-renders.

---

## 13. useSyncExternalStore Hook

**Theory:**
`useSyncExternalStore` is used for subscribing to external stores safely in concurrent React. It ensures updates are consistent across server and client rendering.

---

## 14. useLayoutEffect vs useEffect

**Theory:**
`useLayoutEffect` fires synchronously after DOM mutations but before paint, useful for measuring layout. `useEffect` is deferred after paint, reducing blocking UI.

---

## 15. Memoization Patterns

**Theory:**
Advanced memoization patterns involve `React.memo`, `useMemo`, `useCallback` to prevent expensive re-renders in large or deeply nested components.

---

## 16. React Profiler API

**Theory:**
The Profiler API allows measuring rendering durations and identifying performance bottlenecks. Useful for profiling component trees programmatically.

---

## 17. Server-Side Rendering (SSR) with React

**Theory:**
SSR renders components on the server, improving first contentful paint and SEO. Combined with hydration, it allows full interactivity after server render.

---

## 18. Static Site Generation (SSG) vs SSR

**Theory:**
SSG pre-renders pages at build time, while SSR renders on request. Use SSG for static content and SSR for dynamic data needing real-time fetch.

---

## 19. React Profiler Flamegraphs

**Theory:**
Flamegraphs visualize component render times in Profiler, helping identify heavy components and unnecessary renders for optimization.

---

## 20. React Concurrent Features in Production

**Theory:**
Concurrent features like transitions, deferred values, and suspense improve app responsiveness. They must be carefully tested in production for hydration, async behavior, and backward compatibility.


