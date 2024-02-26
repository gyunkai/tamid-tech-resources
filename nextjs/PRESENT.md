---
marp: true
theme: gaia
class: invert
---

<!-- _class: lead -->

# Hands on with Next.js

---

# 1. Build a little counter app

JavaScript Basics:

- Variables
  - use `const` and `let`
- Functions
  - `function` keyword
  - anonymous arrow functions

---

- Props
  - pass in anonymous arrow function to `onClick`
- JavaScript console
  - `console.log`

Add the following code to `<button>`:

```js
  onClick={() => {
    number++;
  }}
```

---

# Why doesn't it work?

- Concept of Reactivity
  - React only re-renders when state changes
  - Web page doesn't automatically keep track of the value of `number`
- In vanilla JS, we use different methods to change web page content
  - `document.getElementById`
  - `document.querySelector`
  - select elements / update variable / update element

---

- In React, we use `useState` to keep track of state change (you can understand "state" as variables that will cause UI update)
  - `useState` returns an array with two elements
    - first element is the state variable
    - second element is a function to update the state variable
  - Add this to your code:

```js
const [number, setNumber] = useState(0);
```

- Notice we are working with constants here, because you do not want to reassign the state variable directly, but use `setNumber(number + 1)` instead

---

# Imperative vs Declarative

- Imperative: tell the computer what to do
- Declarative: tell the computer what you want
- React is declarative
  - You tell React what you want to render
  - React will figure out how to render it
  - React compiles declarative code into imperative code

---

# 2. Build a to-do app

## Think about how to solve the problem:

- What are the elements?
  - A list of to-do items
  - A text input and button to add new items
- What are the states?
  - The list of to-do items
  - The text input

---

- More JavaScript Basics:
  - Arrays
    - `map`
    - `filter`
  - For loops
- `useState` can be used to store any type of data, that also includes arrays
- using `map` to render an array of items

---

# 3. Refactor the frameworks page

- Using components
  - components allow you to reuse code
  - components are functions that return JSX
  - components can be nested
- Using props
  - props are informations passed into components

---

Define a component:

```js
function MyComponent(props) {
  return <div>{props.text}</div>;
}
```
