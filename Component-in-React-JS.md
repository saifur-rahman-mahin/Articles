---
title: "Component in React JS"
seoTitle: "Component in React JS"
seoDescription: "React components can be categorized into several types based on their functionality and purpose in a React application. Here are some common types of React"
datePublished: Fri Oct 06 2023 14:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clnepemw1000209ic9nkw5p93
slug: component-in-react-js
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/f77Bh3inUpE/upload/3320f0ec837e95c3134df00efb58e3b6.jpeg
tags: javascript, reactjs

---

React components can be categorized into several types based on their functionality and purpose in a React application. Here are some common types of React components:

# **Functional Components**

1. * Written as plain JavaScript functions.
        
    * Used for simple UI elements or when the component doesn't need to manage its own state.
        
    * Introduced in React 16.8 with the introduction of hooks.
        

```jsx
function MyFunctionalComponent(props) {
  return <div>{props.text}</div>;
}
```

1. **Class Components**:
    
    * Traditional React components that extend the `React.Component` class.
        
    * Used for more complex components that need to manage state, lifecycle methods, and props.
        

```jsx
class MyClassComponent extends React.Component {
  render() {
    return <div>{this.props.text}</div>;
  }
}
```

1. **Stateful Components**:
    
    * Components that manage and store their own state data using `setState`.
        
    * Can be either functional components using hooks or class components.
        
2. **Stateless Components**:
    
    * Components that do not manage their own state and rely solely on props.
        
    * Typically functional components.
        
3. **Higher-Order Components (HOCs)**:
    
    * A pattern in React where a component is wrapped by another component to enhance its functionality.
        
    * Often used for sharing behavior or code among multiple components.
        
4. **Render Props**:
    
    * A pattern where a component accepts a function as a prop and uses that function to render content.
        
    * Useful for creating reusable components that can be customized by their consumers.
        
5. **Pure Components**:
    
    * Class components that automatically optimize rendering by performing a shallow comparison of props and state before rendering.
        
    * Prevent unnecessary re-renders.
        
6. **Container Components**:
    
    * Components that are responsible for fetching and managing data or application logic.
        
    * Often used in combination with presentational components.
        
7. **Presentational Components**:
    
    * Components that focus solely on the presentation of UI.
        
    * Receive data and callbacks via props and don't have much internal logic.
        
8. **Functional Stateless Components (FSC)**:
    
    * A subset of functional components that are entirely stateless and rely only on props.
        
9. **Controlled Components**:
    
    * Components that receive all their data via props and notify changes via callbacks.
        
    * Common in forms and input elements.
        
10. **Uncontrolled Components**:
    
    * Components that maintain their state internally without being controlled by React state.
        
    * Less common and often used when integrating with non-React code.
        
11. **Dynamic Components**:
    
    * Components that are created dynamically at runtime based on conditions or data.
        
12. **Conditional Rendering Components**:
    
    * Components that render different content based on conditions or state.
        
13. **Context Providers and Consumers**:
    
    * Components that provide and consume context to share data across the component tree.
        
14. **Lazy Loaded Components**:
    
    * Components that are loaded asynchronously when they are needed, improving initial page load times.
        
15. **Error Boundary Components**:
    
    * Components that catch and handle errors that occur within their child components.
        
16. **Suspense Components**:
    
    * Components that are used with React Suspense to handle loading states for asynchronous operations.
        

These are some of the common categorizations of React components, and a single component can belong to multiple categories depending on its functionality and usage within an application.

---

### Here are examples for each of the mentioned types of React components:

1. **Functional Components (Stateless Components):**
    
    ```jsx
    import React from 'react';
    
    function MyFunctionalComponent(props) {
      return <div>{props.text}</div>;
    }
    ```
    
2. **Class Components:**
    
    ```jsx
    import React, { Component } from 'react';
    
    class MyClassComponent extends Component {
      render() {
        return <div>{this.props.text}</div>;
      }
    }
    ```
    
3. **Stateful Components:**
    
    Functional Component with Hooks:
    
    ```jsx
    import React, { useState } from 'react';
    
    function MyStatefulComponent() {
      const [count, setCount] = useState(0);
    
      const handleIncrement = () => {
        setCount(count + 1);
      };
    
      return (
        <div>
          <p>Count: {count}</p>
          <button onClick={handleIncrement}>Increment</button>
        </div>
      );
    }
    ```
    
    Class Component with `setState`:
    
    ```jsx
    import React, { Component } from 'react';
    
    class MyStatefulComponent extends Component {
      constructor(props) {
        super(props);
        this.state = { count: 0 };
      }
    
      handleIncrement = () => {
        this.setState({ count: this.state.count + 1 });
      };
    
      render() {
        return (
          <div>
            <p>Count: {this.state.count}</p>
            <button onClick={this.handleIncrement}>Increment</button>
          </div>
        );
      }
    }
    ```
    
4. **Stateless Components:**
    
    Stateless components are similar to functional components in the first example. They rely solely on props and do not manage their own state.
    
5. **Higher-Order Components (HOCs):**
    
    Here's a simplified example of a Higher-Order Component that logs props:
    
    ```jsx
    import React from 'react';
    
    function logProps(WrappedComponent) {
      return class extends React.Component {
        render() {
          console.log('Props:', this.props);
          return <WrappedComponent {...this.props} />;
        }
      };
    }
    
    // Usage
    const EnhancedComponent = logProps(MyClassComponent);
    ```
    
6. **Render Props:**
    
    Render props allow you to pass a function as a prop to a component. Here's an example:
    
    ```jsx
    import React from 'react';
    
    function RenderPropsComponent(props) {
      return <div>{props.render("Hello, Render Props!")}</div>;
    }
    
    // Usage
    <RenderPropsComponent render={(text) => <p>{text}</p>} />
    ```
    
7. **Pure Components:**
    
    Pure components are class components that automatically optimize rendering. You can use the `React.PureComponent` base class:
    
    ```jsx
    import React, { PureComponent } from 'react';
    
    class MyPureComponent extends PureComponent {
      render() {
        return <div>{this.props.text}</div>;
      }
    }
    ```
    
8. **Container Components:**
    
    Container components are often responsible for managing data or application logic. Here's a simplified example:
    
    ```jsx
    import React, { Component } from 'react';
    
    class DataContainer extends Component {
      constructor(props) {
        super(props);
        this.state = { data: [] };
      }
    
      componentDidMount() {
        // Fetch data and update state
      }
    
      render() {
        return <PresentationalComponent data={this.state.data} />;
      }
    }
    ```
    
9. **Presentational Components:**
    
    Presentational components focus on rendering UI and receiving data via props. They don't have much internal logic. Here's a simplified example:
    
    ```jsx
    import React from 'react';
    
    function PresentationalComponent(props) {
      return <div>{props.data}</div>;
    }
    ```
    
10. **Functional Stateless Components (FSC):**
    
    This is the same as Functional Components (Stateless Components) mentioned earlier.
    
11. **Controlled Components:**
    
    Controlled components receive data via props and notify changes via callbacks. Common in forms and input elements. Here's an example of a controlled input component:
    
    ```jsx
    import React, { Component } from 'react';
    
    class ControlledInput extends Component {
      constructor(props) {
        super(props);
        this.state = { inputValue: '' };
      }
    
      handleInputChange = (event) => {
        this.setState({ inputValue: event.target.value });
      };
    
      render() {
        return (
          <input
            type="text"
            value={this.state.inputValue}
            onChange={this.handleInputChange}
          />
        );
      }
    }
    ```
    
12. **Uncontrolled Components:**
    
    Uncontrolled components maintain their state internally. They are less common and often used when integrating with non-React code.
    
13. **Dynamic Components:**
    
    Dynamic components are created based on conditions or data at runtime. Here's an example of rendering different components based on a condition:
    
    ```jsx
    import React from 'react';
    
    function DynamicComponent(props) {
      const condition = props.someCondition;
      return condition ? <ComponentA /> : <ComponentB />;
    }
    ```
    
14. **Conditional Rendering Components:**
    
    Components that render different content based on conditions or state. This can be seen in many React components where `if` or ternary operators are used to conditionally render parts of the UI.
    
15. **Context Providers and Consumers:**
    
    Context Providers and Consumers are used to share data across the component tree. A Provider provides data, and Consumers can access that data. Here's a simplified example:
    
    ```jsx
    import React, { createContext, useContext } from 'react';
    
    const MyContext = createContext();
    
    function MyProvider({ children }) {
      const sharedData = "Data from Context";
    
      return <MyContext.Provider value={sharedData}>{children}</MyContext.Provider>;
    }
    
    function MyConsumer() {
      const data = useContext(MyContext);
      return <div>{data}</div>;
    }
    ```
    
16. **Lazy Loaded Components:**
    
    Lazy loading components asynchronously improves initial page load times. React provides a `lazy` function and `Suspense` for this purpose. Here's a simplified example:
    
    ```jsx
    import React, { lazy, Suspense } from 'react';
    
    const LazyComponent = lazy(() => import('./LazyComponent'));
    
    function App() {
      return (
        <div>
          <Suspense fallback={<div>Loading...</div>}>
            <LazyComponent />
          </Suspense>
        </div>
      );
    }
    ```
    
17. Error Boundary Components:
    
    Error Boundary components are used to catch and handle errors that occur within their child components. Here's an example:
    
    ```jsx
    import React, { Component } from 'react';
    
    class ErrorBoundary extends Component {
      constructor(props) {
        super(props);
        this.state = { hasError: false };
      }
    
      componentDidCatch(error, errorInfo) {
        this.setState({ hasError: true });
        // Log the error or handle it in some way
      }
    
      render() {
        if (this.state.hasError) {
          return <div>Something went wrong.</div>;
        }
    
        return this.props.children;
    
    
      }
    }
    ```
    
18. **Suspense Components:**
    
    Suspense components are used in combination with React Suspense to handle loading states for asynchronous operations. They allow components to suspend rendering until data is available. Here's a simplified example:
    
    ```jsx
    import React, { Suspense } from 'react';
    
    function MyComponent() {
      return (
        <Suspense fallback={<div>Loading...</div>}>
          {/* Render components that may suspend */}
        </Suspense>
      );
    }
    ```
    

These examples demonstrate the different types of React components and their respective use cases. Keep in mind that real-world components may be more complex and often combine multiple characteristics from the categories mentioned.
