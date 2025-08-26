## Ternary Operator
- Syntax: condition ? valueIfTrue : valueIfFalse; commonly used in React for conditional UI text or values.  
- Examples: quick even/odd check, welcome messages based on login or membership state.  

## Logical Operators (&&, ||)
- OR (||): returns the right-hand value if the left is falsy (null, undefined, 0, '', false, NaN). Useful for default fallbacks.  
- AND (&&): returns the right-hand value if the left is truthy; handy for concise conditional execution/assignment.  

## Practice Prompts
- Write a function to check if the sum of two integers exceeds 100 using a ternary.  
- Predict outputs using || defaults and && short-circuiting (e.g., nickname || 'Anonymous', score > 80 && set message).  

## Mini App: Dynamic UI with ES6
- HTML structure: title, a user card with name/status, and a toggle button to flip login state.  
- Script highlights:  
  - let/const for state and DOM references.  
  - Object destructuring from a userProfile object.  
  - Arrow functions and template literals to render UI text.  
  - Ternary operator for status and display name.  
  - Logical AND to conditionally change styles (green when logged in, red when logged out).  
  - Event listener toggles isLoggedIn and re-renders UI.  

## ES6 Patterns Emphasized
- Use const/let, destructuring, template literals, arrow functions for clean, reactive UI logic.  
- Prefer concise conditionals with ? : and short-circuiting (&& / ||) in DOM updates or component code.  
