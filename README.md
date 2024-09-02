# tech_theory


---

# Frontend Advanced Interview Questions

This repository contains tricky and advanced frontend interview questions that test deep understanding of various technologies including CSS, JavaScript, HTML, React, and Redux.

### **CSS**

1. **How does `contain` property affect layout performance in CSS?**  
   **Answer**: The `contain` property creates a containment context, which limits the scope of browser rendering. It prevents layout recalculations from affecting the entire document, improving performance by isolating the element from the rest of the layout.

2. **Explain the difference between `em`, `rem`, and `vw` units. What tricky edge cases might arise when using them?**  
   **Answer**:  
   - `em`: Relative to the font size of the parent element.  
   - `rem`: Relative to the root element (`<html>`) font size.  
   - `vw`: Relative to the viewport width.  
   Edge case: Nested `em` units can lead to unexpected scaling, and using `vw` can cause issues on mobile screens due to dynamic resizing.

---

### **JavaScript**

3. **Why can `typeof null` return `"object"` in JavaScript?**  
   **Answer**: This is a long-standing bug in JavaScript. `null` was intended to be a primitive value, but due to how values are represented internally, `typeof null` incorrectly returns `"object"`.

4. **How would you check if two objects are deeply equal without using `JSON.stringify()`?**  
   **Answer**: Use recursive comparison of the objects' properties. You need to check if both objects have the same keys and that each key's value is deeply equal.

5. **What happens if you return a function from inside a `for` loop using `let` and `var` for the loop variable?**  
   **Answer**:  
   - Using `let`: The loop variable retains block-scoped behavior and captures the correct value for each iteration.  
   - Using `var`: The variable is function-scoped, so the same value is used for all closures, leading to unexpected behavior.

6. **Explain the difference between `Promise.allSettled()` and `Promise.all()` in handling promise results.**  
   **Answer**:  
   - `Promise.all()`: Fails fast; if any promise rejects, it stops and rejects immediately.  
   - `Promise.allSettled()`: Waits for all promises to settle (fulfilled or rejected) and returns an array of their results.

---

### **HTML**

7. **What does the `async` attribute do when applied to a `<script>` tag, and how is it different from `defer`?**  
   **Answer**:  
   - `async`: Loads the script asynchronously and executes it as soon as it's available, potentially before HTML parsing is complete.  
   - `defer`: Loads the script asynchronously but delays execution until after HTML parsing is complete.

8. **Explain why the `meta` viewport tag is essential in responsive web design.**  
   **Answer**: It controls the layout viewport's scale, allowing pages to scale properly on mobile devices. Without it, the page might appear zoomed out or too wide.

---

### **React**

9. **Why does React use a virtual DOM, and how does it improve performance?**  
   **Answer**: The virtual DOM allows React to batch updates and minimize direct DOM manipulation. It computes the minimal set of changes needed to update the UI, which reduces expensive operations like reflows and repaints.

10. **What issue can arise when using hooks inside loops or conditionals?**  
    **Answer**: Hooks must be called in the same order on every render. Using hooks inside loops or conditionals can break this order, leading to bugs and unpredictable behavior.

11. **How would you prevent unnecessary re-renders in a functional component using React hooks?**  
    **Answer**: Use `React.memo()` to memoize the component, and use `useCallback()` or `useMemo()` to memoize callbacks and expensive calculations that cause re-renders.

12. **What potential problem does React.StrictMode help identify in development?**  
    **Answer**: It highlights side effects and issues like unintentional re-renders, deprecated lifecycle methods, and improper usage of hooks by rendering components twice in development mode.

---

### **Redux**

13. **Why should reducers be pure functions in Redux?**  
    **Answer**: Reducers must be predictable and consistent. Pure functions ensure that the same inputs always produce the same outputs without causing side effects, making state management predictable.

14. **What’s the significance of immutability in Redux, and how would breaking it cause issues?**  
    **Answer**: Immutability ensures that state changes are tracked correctly. Mutating the state directly can lead to unpredictable bugs and prevents Redux from accurately determining when to trigger re-renders.

15. **Why is dispatching an action from inside a reducer considered an anti-pattern in Redux?**  
    **Answer**: Reducers should only calculate the new state and must remain pure. Dispatching actions inside reducers can lead to infinite loops, side effects, and unpredictable behavior.

---
---
