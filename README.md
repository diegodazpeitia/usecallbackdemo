# React Example for useCallback Hook

This project demonstrates the usage of the `useCallback` hook in React to optimize function references.

## Description

The `useCallback` hook is used in React to memoize functions. This means it memoizes the provided function instance between re-renders, preventing unnecessary re-creations of the function on each render. This can be beneficial for performance optimization in scenarios where functions are passed to child components that rely on reference equality to prevent unnecessary re-renders.

### How useCallback Works

1. **Memoization of Functions**:
   - When you define a function inside a functional component, it gets recreated on every render. This behavior can lead to unnecessary re-renders in child components that rely on reference equality of props.

2. **Optimizing with useCallback**:
   - `useCallback` allows you to memoize a function, so it will only be recreated if any of its dependencies change. It returns a memoized version of the function.

3. **Dependencies Array**:
   - You provide an array of dependencies as the second argument to `useCallback`. The function will only be re-created if any of these dependencies change. If the dependencies don't change, `useCallback` returns the same memoized function on subsequent renders.

4. **Usage in this Example**:
   - In this example (`App.js`), `useCallback` is used to memoize three functions:
     - `incrementCounter`
     - `decrementCounter`
     - `incrementNumber`
   - These functions are passed to buttons as event handlers (`onClick`). `useCallback` ensures that these functions retain the same reference across renders unless their dependencies (`count` or `number`) change.

```javascript
const incrementCounter = useCallback(() => {
  setCount(count + 1);
}, [count]);

const decrementCounter = useCallback(() => {
  setCount(count - 1);
}, [count]);

const incrementNumber = useCallback(() => {
  setNumber(number + 1);
}, [number]);
```

5. **Benefits**:
   - Reduces unnecessary re-renders in child components that rely on reference equality of props.
   - Improves performance by optimizing memory usage, especially in components with complex render logic or large dependency trees.

# What you will experience 

<img width="631" alt="Captura de pantalla 2024-07-24 a la(s) 20 08 12" src="https://github.com/user-attachments/assets/c09f37d0-d61d-4f34-b4af-f3ab411c7d69">

## Installation and Usage

Follow the installation and usage instructions as outlined in the main README to run and explore this example.

## Contributing

Feel free to contribute to enhance this example or fix any issues by submitting a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
