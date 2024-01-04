# React Redux Basic 👶

`npm start`

# React Redux Basics

## Overview

Redux is a predictable state container for JavaScript applications.
It's often used with React to manage application-wide state in a centralized and organized way.
Key concepts:
Store: Holds the application's state.
Actions: Describe events that can change the state.
Reducers: Pure functions that update the state based on actions.

## Core Principles

Single Source of Truth: The entire application state is stored in a single store.
State is Read-Only: State can only be modified by dispatching actions.
Changes are Made with Pure Functions: Reducers are pure functions that always return the same output for the same input.

## Setting Up Redux with React

Install necessary packages:
Bash
npm install redux react-redux
Use code with caution. Learn more
Create a store:
JavaScript
import { createStore } from 'redux';
import rootReducer from './reducers'; // Import your combined reducers

const store = createStore(rootReducer);
Use code with caution. Learn more
Connect React components to the store:
JavaScript
import { Provider } from 'react-redux';

ReactDOM.render(
<Provider store={store}>
<App />
</Provider>,
document.getElementById('root')
);
Use code with caution. Learn more
Wrap components with connect:
JavaScript
import { connect } from 'react-redux';

const MyComponent = ({ stateValue }) => {
// Access state and dispatch actions here
};

const mapStateToProps = (state) => ({
stateValue: state.someValue,
});

export default connect(mapStateToProps)(MyComponent);
Use code with caution. Learn more

## Reducers:

Pure functions that take the current state and an action, and return the new state.
Example:
JavaScript
const counterReducer = (state = 0, action) => {
switch (action.type) {
case

'INCREMENT':
return state + 1;
case

'DECREMENT':
return state - 1;
default:
return state;
}
};
Use code with caution. Learn more

## Actions:

Plain JavaScript objects that describe state change requests.
Must have a type property.
Can have additional payload data.
Example:
JavaScript
const incrementAction = { type: 'INCREMENT' };
Use code with caution. Learn more

## Dispatching Actions:

Use the store.dispatch() method to dispatch actions.
Example:
JavaScript
store.dispatch(incrementAction);
Use code with caution. Learn more

## Connecting Components:

connect function from react-redux connects components to the store.
mapStateToProps: Maps state to component props.
mapDispatchToProps: Maps dispatch functions to component props.

## Additional Notes

Consider using middleware for asynchronous actions and side effects (e.g., Redux Thunk or Redux Saga).
Organize reducers using combineReducers for larger applications.
Use tools like Redux DevTools for debugging and inspecting state changes.
