## Junior

1. ### What is React?

    React is an **open-source frontend JavaScript library** which is used for building user interfaces especially for single page applications.

2. ### What are the major features of React?

    The major features of React are:

    * It uses **VirtualDOM** instead RealDOM considering that RealDOM manipulations are expensive.
    * Supports **server-side rendering**.
    * Follows *Unidirectional** data flow or data binding.
    * Uses **reusable/composable** UI components to develop the view.

3. ### What is JSX?

    *JSX* is a XML-like syntax extension to ECMAScript (the acronym stands for *JavaScript XML*). Basically it just provides syntactic sugar for the `React.createElement()` function, giving us expressiveness of JavaScript along with HTML like template syntax.

4. ### What is the difference between Element and Component?

    An *Element* is a plain object describing what you want to appear on the screen in terms of the DOM nodes or other components. *Elements* can contain other *Elements* in their props. Creating a React element is cheap. Once an element is created, it is never mutated.


    Whereas a **component** can be declared in several different ways. It can be a class with a `render()` method. Alternatively, in simple cases, it can be defined as a function. In either case, it takes props as an input, and returns an JSX tree as the output:


5. ### How to create components in React?

    There are two possible ways to create a component.

    1. **Function Components:** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as first parameter and return React elements:

        ```jsx harmony
        function Greeting({ message }) {
          return <h1>{`Hello, ${message}`}</h1> 
        }
        ```

    2. **Class Components:** You can also use ES6 class to define a component. The above function component can be written as:

        ```jsx harmony
        class Greeting extends React.Component {
          render() {
            return <h1>{`Hello, ${this.props.message}`}</h1>
          }
        }
        ```

6. ### When to use a Class Component over a Function Component?

    If the component needs *state or lifecycle methods* then use class component otherwise use function component.

7. ### What are Pure Components?

    *`React.PureComponent`* is exactly the same as *`React.Component`* except that it handles the `shouldComponentUpdate()` method for you. When props or state changes, *PureComponent* will do a shallow comparison on both props and state. *Component* on the other hand won't compare current props and state to next out of the box. Thus, the component will re-render by default whenever `shouldComponentUpdate` is called.
    
8. ### What is state in React?

    *State* of a component is an object that holds some information that may change over the lifetime of the component. We should always try to make our state as simple as possible and minimize the number of stateful components. Let's create an user component with message state,
    
9. ### What are props in React?

    *Props* are inputs to components. They are single values or objects containing a set of values that are passed to components on creation using a naming convention similar to HTML-tag attributes. They are data passed down from a parent component to a child component.

    The primary purpose of props in React is to provide following component functionality:

    1. Pass custom data to your component.
    2. Trigger state changes.
    3. Use via `this.props.reactProp` inside component's `render()` method.
    
10. ### What is the difference between state and props?

    Both *props* and *state* are plain JavaScript objects. While both of them hold information that influences the output of render, they are different in their functionality with respect to component. Props get passed to the component similar to function parameters whereas state is managed within the component similar to variables declared within a function.
    
## Intermediate

1. ### What are synthetic events in React?

    ```SyntheticEvent` is a cross-browser wrapper around the browser's native event. It's API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers.
    
2. ### What are "key" props and what is the benefit of using them in arrays of elements?

    A `key` is a special string attribute you **should** include when creating arrays of elements. *Keys* help React identify which items have changed, are added, or are removed.


3. ### What are forward refs?

    *Ref forwarding* is a feature that lets some components take a *ref* they receive, and pass it further down to a child.
    
4. ### What is Virtual DOM?

    The *Virtual DOM* (VDOM) is an in-memory representation of *Real DOM*. The representation of a UI is kept in memory and synced with the "real" DOM. It's a step that happens between the render function being called and the displaying of elements on the screen. This entire process is called *reconciliation*.
    
5. ### What are controlled components?

    A component that controls the input elements within the forms on subsequent user input is called **Controlled Component**, i.e, every state mutation will have an associated handler function.
    
6. ### What are the different phases of component lifecycle?

    There are four different phases of component lifecycle.

    1. **Initialization:** In this phase component prepares setting up the initial state and default props.

    2. **Mounting:** The component is ready to mount in the browser DOM. This phase covers `componentWillMount()` and `componentDidMount()` lifecycle methods.

    3. **Updating:** In this phase, the component get updated in two ways, sending the new props and updating the state. This phase covers `shouldComponentUpdate()`, `componentWillUpdate()` and `componentDidUpdate()` lifecycle methods.

    4. **Unmounting:** In this last phase, the component is not needed and get unmounted from the browser DOM. This phase includes `componentWillUnmount()` lifecycle method.
