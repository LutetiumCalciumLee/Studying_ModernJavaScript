# Modern JavaScript

## Overview
- Modern JavaScript refers to ES6+ features and the surrounding tooling ecosystem used with frameworks like React, Vue, and Angular.  
- Core ideas include functional patterns and immutable updates, supported by tools such as package managers, bundlers, and transpilers.  

## Variables and Scope
- Prefer let/const over var due to block scope and safer behavior.  
- const prevents reassignment but still allows mutation of object/array contents; let allows reassignment.  

## Hoisting and TDZ
- var is hoisted and initialized to undefined, enabling access before declaration.  
- let/const are hoisted but not initialized (Temporal Dead Zone), causing ReferenceError if accessed early.  

## Template Literals
- Use backticks and ${} for string interpolation and embedding expressions, improving readability over + concatenation.  

## Arrow Functions
- Concise syntax that can omit function/return when a single expression; parentheses optional for a single parameter.  
- this is lexically bound, which is useful for callbacks and event handlers.  

## Destructuring
- Extract values from objects/arrays into variables; supports renaming and default values.  
- Object destructuring is key-based; array destructuring is order-based.  

## Default Values
- Provide safe fallbacks in function parameters and destructuring assignments when values are missing.  

## Spread and Rest (...)
- Spread expands arrays/objects for merging, shallow copying, and function argument passing.  
- Rest collects remaining function arguments into an array; must be the last parameter.  

## Shallow Copy Caution
- Assignment (=) copies references, so mutations affect the original.  
- Spread creates a new shallow copy; deep structures still need explicit deep copy handling.  

## Object Shorthand
- When property names match variable names, use shorthand: const user = { name, age }.  

## Array Higher-Order Functions
- map transforms elements and returns a new array (non-mutating).  
- filter selects elements that meet a condition.  
- reduce aggregates elements into a single value (number, string, object), with an initial accumulator.  

## Practice Patterns
- ES5 → ES6 refactors: var→let/const, string +→template literals, index access→destructuring, Object.assign→spread, arguments loops→rest + reduce.  
- Typical pipeline: map to adjust values (e.g., score +10) → filter by condition (≥ 80) → reduce to a total.  
- Common task: filter by score threshold (≥ 60) then map to extract names.

