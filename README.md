## Props and Component Composition
- **`defaultProps`**: Assign default values to props directly in a component's function signature using destructuring, such as `function Welcome({ name = "Guest" })`. This is a common practice to prevent errors if a parent component does not pass the required prop.
- **`children` Prop**: A special prop, `props.children`, automatically receives any content placed between a component's opening and closing tags. This pattern is highly effective for creating reusable wrapper components like layouts, cards, or modals.
- **Prop Destructuring**: Instead of repeatedly accessing props with `props.name` and `props.age`, you can destructure them directly in the function's parameter list for cleaner and more readable code: `function Profile({ name, age })`.

## State Management with `useState`
- **Definition**: State is a JavaScript object managed within a component that holds data that can change over time. When a state value is updated, React automatically re-renders the component to reflect the new data.
- **Syntax**: The `useState` hook is the standard way to add state to a functional component. It is declared as `const [stateVariable, setStateFunction] = useState(initialValue);`. Calling the `setStateFunction` triggers an update.
- **Props vs. State**: Props are read-only and are passed down from a parent component. State, however, is managed and can be modified internally by the component itself.
- **Updating Parent's State**: A child component cannot directly modify its parent's state. The standard pattern is for the parent to pass a function that modifies its own state down to the child as a prop. The child then invokes this function to signal a state change.

## React Event Handling
- **Handler Syntax**: Event handlers in JSX are written in camelCase (e.g., `onClick`) and are assigned a function reference, not a string or a function call (e.g., `<button onClick={handleClick}>`).
- **Passing Arguments**: When an event handler needs to receive arguments, it should be wrapped in an arrow function to prevent it from executing on render: `<button onClick={() => handlePurchase('item-1')}>`.
- **SyntheticEvent Object**: React normalizes the browser's native event into a `SyntheticEvent` object, ensuring consistent behavior across different browsers. Key properties include `e.target` (the DOM element that initiated the event), `e.key`, and `e.preventDefault()`.

## Controlled Components for Forms
- **Concept**: A controlled component is an input form element whose value is controlled by React state. The component's state serves as the "single source of truth" for the input's value.
- **Implementation**: The input element's `value` attribute is bound to a state variable, and an `onChange` event handler is used to update that state with every change (e.g., keystroke), typically using `e.target.value`.
- **Managing Multiple Inputs**: To handle multiple form inputs without creating separate state and handler functions for each, you can use a single state object. A unified `handleChange` function can then dynamically update the correct piece of state by using the input's `name` attribute to identify which field is being changed.

