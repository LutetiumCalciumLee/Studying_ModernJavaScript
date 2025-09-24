## The `useEffect` Hook
- **Purpose**: The `useEffect` hook is used to perform side effects in functional components. Side effects are operations that can affect other components and can't be done during rendering, such as API calls, subscriptions, or manually changing the DOM.
- **Lifecycle Equivalence**: It combines the functionality of several lifecycle methods from class components into a single API. It can replicate the behavior of `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
- **Basic Syntax**: The hook takes a function (the "effect") as its first argument and an optional dependency array as its second argument. The effect function runs after the component renders.
    ```jsx
    useEffect(() => {
      // Side effect logic goes here
      console.log('Component has rendered or a dependency has changed.');
    }, [dependency1, dependency2]);
    ```

## Controlling Execution with Dependencies
- **No Dependency Array**: If you omit the dependency array, the effect function will run after **every single render** of the component. This is useful for effects that need to be synchronized with every UI update, but can also lead to performance issues if not handled carefully.
    ```jsx
    // Runs after every render
    useEffect(() => {
      console.log('Component re-rendered');
    });
    ```
- **Empty Dependency Array `[]`**: When you provide an empty array, the effect function runs **only once**, after the component's initial render. This is the equivalent of `componentDidMount` and is ideal for one-time setup tasks like fetching initial data or setting up a subscription.
    ```jsx
    // Runs only once after the first render
    useEffect(() => {
      console.log('Component mounted. Fetching data...');
    }, []);
    ```
- **Dependency Array with Values `[prop, state]`**: The effect will run after the initial render and **only when any of the values in the dependency array have changed** between renders. This allows you to control when the effect re-runs, optimizing performance by avoiding unnecessary execution.
    ```jsx
    // Runs on mount and whenever 'userId' changes
    useEffect(() => {
      console.log(`Fetching profile for user ${userId}`);
      // API call to fetch user data
    }, [userId]);
    ```

## The Cleanup Function
- **Purpose**: The `useEffect` hook can return a function, which is known as the "cleanup" function. This function is used to clean up any resources established by the effect, such as timers, event listeners, or subscriptions, to prevent memory leaks.
- **Execution Timing**: The cleanup function runs in two scenarios:
    1.  Before the component is unmounted and removed from the UI (similar to `componentWillUnmount`).
    2.  Before the effect function runs again due to a change in its dependencies.
- **Implementation**: To use it, simply return a named or anonymous function from within your effect.
    ```jsx
    useEffect(() => {
      const timerId = setInterval(() => {
        console.log('Timer is ticking');
      }, 1000);

      // Cleanup function
      return () => {
        console.log('Cleaning up the timer.');
        clearInterval(timerId);
      };
    }, []); // Empty array means cleanup runs only on unmount
    ```

## Data Persistence with `useEffect`
- **Use Case**: `useEffect` is commonly used with `localStorage` to persist state across browser sessions. You can load data from `localStorage` on component mount and save data back whenever the state changes.
- **Loading Data**: An effect with an empty dependency array is used to read the initial state from `localStorage` when the component first loads.
- **Saving Data**: A separate effect, which depends on the state variable, is used to write any changes back to `localStorage`, ensuring the data is always synchronized.
    ```jsx
    function TodoList() {
      // Load initial todos from localStorage, or use an empty array
      const initialTodos = JSON.parse(localStorage.getItem('todos')) || [];
      const [todos, setTodos] = useState(initialTodos);

      // Effect to save todos to localStorage whenever they change
      useEffect(() => {
        localStorage.setItem('todos', JSON.stringify(todos));
      }, [todos]); // This effect runs every time 'todos' state changes

      // ... component logic to add/remove todos
    }
    ```
