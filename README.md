# tech_theory
Here's a **README file** combining all previous sets of questions in the order of **HTML, CSS, JavaScript, React, and Redux**, with precise answers included:

---

# Frontend Advanced Interview Questions

This repository contains challenging and advanced frontend interview questions designed to test deep understanding of HTML, CSS, JavaScript, React, and Redux. Each section covers tricky, real-world problems and provides precise answers to help guide your preparation.

---

## **HTML**

1. **What does the `async` attribute do when applied to a `<script>` tag, and how is it different from `defer`?**  
   **Answer**:  
   - `async`: Loads the script asynchronously and executes it as soon as it's available, possibly before HTML parsing is complete.  
   - `defer`: Loads the script asynchronously but delays execution until after HTML parsing is complete.

2. **Explain why the `meta` viewport tag is essential in responsive web design.**  
   **Answer**: It controls the layout viewport's scale, allowing pages to scale properly on mobile devices. Without it, the page might appear zoomed out or too wide.

3. **What are Web Components and how do they differ from traditional HTML elements and React components?**  
   **Answer**: Web Components use Custom Elements, Shadow DOM, and HTML templates to create encapsulated, reusable components. They differ from React components by not requiring a framework and providing true DOM isolation.

4. **How would you optimize the critical rendering path for a large, content-heavy HTML page with multiple blocking assets (e.g., CSS, JavaScript)?**  
   **Answer**: Techniques include deferring or asynchronously loading resources, using preload/prefetch hints, minimizing render-blocking resources, and optimizing fonts.

---

## **CSS**

1. **How does the `contain` property affect layout performance in CSS?**  
   **Answer**: The `contain` property creates a containment context, limiting the scope of browser rendering, which prevents layout recalculations from affecting the entire document, improving performance.

2. **Explain the difference between `em`, `rem`, and `vw` units. What tricky edge cases might arise when using them?**  
   **Answer**:  
   - `em`: Relative to the font size of the parent element.  
   - `rem`: Relative to the root element (`<html>`) font size.  
   - `vw`: Relative to the viewport width.  
   Edge case: Nested `em` units can lead to unexpected scaling, and using `vw` can cause issues on mobile screens due to dynamic resizing.

3. **How would you handle CSS-in-JS performance bottlenecks in a React application with heavy dynamic styling, large media queries, and conditional rendering?**  
   **Answer**: Optimizing by memoizing dynamic styles, minimizing unnecessary re-renders, and using tools like `styled-components` with selective caching for dynamic styles.

4. **Explain how to create a fully accessible, custom-designed input range slider from scratch using only CSS and JavaScript. What challenges might arise in terms of cross-browser support and accessibility compliance?**  
   **Answer**: Implement ARIA attributes, handle focus states, and ensure compatibility across browsers with custom styling while supporting keyboard and screen reader navigation.

---

## **JavaScript**

1. **Why does `typeof null` return `"object"` in JavaScript?**  
   **Answer**: This is a historical bug in JavaScript where `null` was meant to be a primitive, but due to its internal representation, `typeof null` incorrectly returns `"object"`.

2. **How would you check if two objects are deeply equal without using `JSON.stringify()`?**  
   **Answer**: Use a recursive function to compare each property of both objects, ensuring that nested objects and arrays are compared at every level.

3. **What happens if you return a function from inside a `for` loop using `let` and `var` for the loop variable?**  
   **Answer**:  
   - Using `let`: The loop variable retains block-scoped behavior and correctly captures its value for each iteration.  
   - Using `var`: The variable is function-scoped, so all closures capture the same value, leading to unexpected behavior.

4. **Explain the difference between `Promise.allSettled()` and `Promise.all()` in handling promise results.**  
   **Answer**:  
   - `Promise.all()`: Fails fast; if any promise rejects, the entire operation is rejected.  
   - `Promise.allSettled()`: Waits for all promises to settle (fulfilled or rejected), returning an array of each result.

5. **Why can `typeof NaN` return `"number"` in JavaScript?**  
   **Answer**: NaN (Not a Number) is technically a special type of number in JavaScript, hence `typeof NaN` returns `"number"`, even though it's an invalid numeric result.

6. **Explain how a deep comparison algorithm works in JavaScript. Implement one from scratch that accurately compares two objects containing nested arrays, objects, and edge cases like `NaN`, `undefined`, and cyclic references.**  
   **Answer**: The algorithm should recursively compare the properties of each object, handle edge cases like `NaN` (where `NaN !== NaN`), and track visited objects to avoid infinite loops due to cyclic references.

7. **How would you design a JavaScript reactive system similar to Vue.js or Svelte from scratch?**  
   **Answer**: Use `Proxy` or getter/setter patterns to intercept state changes and notify subscribers (components) when a state update occurs, triggering a UI update.

8. **How would you implement a throttle function from scratch in JavaScript? What’s the difference between throttle and debounce?**  
   **Answer**:  
   - Throttle limits the function execution to once every set interval.  
   - Debounce delays the function execution until a certain period of inactivity.  
   Implementation involves timers to control when the function should be executed.

---

## **React**

1. **Why does React use a virtual DOM, and how does it improve performance?**  
   **Answer**: The virtual DOM batches updates and computes the minimal set of changes needed to update the actual DOM, reducing expensive operations like reflows and repaints.

2. **What issue can arise when using hooks inside loops or conditionals?**  
   **Answer**: Hooks must be called in the same order on every render. Using hooks inside loops or conditionals breaks this order, leading to bugs and unpredictable behavior.

3. **How would you prevent unnecessary re-renders in a functional component using React hooks?**  
   **Answer**: Use `React.memo()` to memoize the component and `useCallback()` or `useMemo()` to memoize functions and calculations, preventing re-renders when props or state haven't changed.

4. **What potential problem does React.StrictMode help identify in development?**  
   **Answer**: It highlights side effects, double rendering, deprecated lifecycle methods, and improper usage of hooks by rendering components twice in development.

5. **Explain how `useTransition` in React concurrent mode improves performance during state transitions.**  
   **Answer**: `useTransition` defers non-urgent state updates, allowing urgent UI updates to be rendered immediately while the non-critical updates happen in the background.

6. **What are React portals, and how do they help manage rendering outside the normal component hierarchy?**  
   **Answer**: Portals allow rendering of child components into a different part of the DOM tree without disrupting the component hierarchy, useful for modals, tooltips, etc.

7. **Explain the concept of "reconciliation" in React and how React determines which components to re-render.**  
   **Answer**: React compares the virtual DOM with the previous version (reconciliation) and determines the minimal number of changes to be applied to the actual DOM.

8. **What are the potential performance impacts of using dynamic `key` props in lists? How can improper use lead to bugs?**  
   **Answer**: Dynamic or unstable `key` values can cause React to unnecessarily re-render components or retain incorrect state, as React uses the `key` to identify elements during reconciliation.

---

## **Redux**

1. **Why should reducers be pure functions in Redux?**  
   **Answer**: Pure functions ensure that the same inputs always produce the same outputs without causing side effects, making the application's state management predictable and testable.

2. **What’s the significance of immutability in Redux, and how would breaking it cause issues?**  
   **Answer**: Immutability allows Redux to track changes correctly. Direct state mutation can lead to unpredictable behavior and incorrect updates, breaking the assumption that state should only be updated via actions.

3. **Why is dispatching an action from inside a reducer considered an anti-pattern in Redux?**  
   **Answer**: Reducers should be pure functions and should not have side effects, such as dispatching actions. Doing so can lead to infinite loops and unpredictable state changes.

4. **How would you implement optimistic UI updates in Redux, and what challenges could arise?**  
   **Answer**: Optimistic UI updates update the UI before receiving server confirmation. Challenges include ensuring data consistency in case of a server error, rolling back updates if needed, and maintaining user trust.

5. **How would you structure a Redux store for a real-time collaborative application with multiple users and frequent state changes?**  
   **Answer**: Use WebSocket middleware to synchronize actions across clients in real-time, ensuring that the Redux store is updated consistently across users while resolving conflicts and handling out-of-order messages.

6. **Explain the concept of middleware in Redux and how it can be used to handle asynchronous actions.**  
   **Answer**: Middleware in Redux intercepts dispatched actions

 before they reach reducers. It allows for handling side effects, such as asynchronous API calls, by dispatching different actions based on the success or failure of the operation.

---

# Made BY VIKASH
---

