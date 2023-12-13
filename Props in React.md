---
title: "Props in React"
seoTitle: "Props in React"
seoDescription: "React props can be categorized into several types based on their usage and purpose in a React component. Here are some common categories of React props:"
datePublished: Fri Oct 06 2023 16:52:31 GMT+0000 (Coordinated Universal Time)
cuid: clneuh36e000209jn94o441cv
slug: props-in-react
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/_SgRNwAVNKw/upload/6a44539227293f9a950c301eee151dd9.jpeg
tags: javascript, reactjs

---

React props can be categorized into several types based on their usage and purpose in a React component. Here are some common categories of React props:

1. **Data Props:**
    
    * These props are used to pass data from a parent component to a child component.
        
    * They are typically used to provide dynamic content and configuration to child components.
        
    * Examples include passing text, numbers, objects, arrays, or any other data type.
        
2. **Event Props:**
    
    * Event props are used to pass callback functions from a parent component to a child component.
        
    * These functions can be invoked by the child component to trigger actions in the parent component.
        
    * Examples include passing functions to handle click events, form submissions, or other user interactions.
        
3. **Boolean Props:**
    
    * Boolean props are often used to control the behavior or appearance of a component.
        
    * They are typically used to enable or disable certain features or conditional rendering.
        
    * Examples include props like `isDisabled`, `isVisible`, or `isActive`.
        
4. **Children Props:**
    
    * Children props are used to pass React elements or components as children to a parent component.
        
    * This allows for composing components and creating more complex UI structures.
        
    * Examples include the `children` prop, which is a special prop in React.
        
5. **Style Props:**
    
    * Style props are used to pass CSS styles or class names to a component for custom styling.
        
    * They can be used to make components adaptable to different design requirements.
        
    * Examples include `style`, `className`, or custom style-related props.
        
6. **Configuration Props:**
    
    * Configuration props are used to customize the behavior of a component.
        
    * They are often used for fine-tuning component settings.
        
    * Examples include props like `config`, `options`, or `settings`.
        
7. **Router Props (for React Router):**
    
    * In React applications using React Router, there are specific props for routing.
        
    * These props include `match`, `location`, and `history` and are used to access information about the current route and navigation.
        
8. **Context Props (for Context API):**
    
    * In applications using the React Context API, components can receive context values via props.
        
    * These props are provided by the `Context.Provider` and consumed by the `Context.Consumer` or the `useContext` hook.
        
9. **Custom Props:**
    
    * These are user-defined props specific to a particular component's functionality.
        
    * Custom props can vary widely depending on the requirements of the component.
        
    * Examples might include props like `data-tested` for testing, or any other application-specific prop.
        
10. **Controlled and Uncontrolled Props:**
    
    * Components can have controlled and uncontrolled props. Controlled props are controlled by the parent component, while uncontrolled props allow the child component to manage its state independently.
        

Remember that the specific props used in a React component depend on the component's design and functionality. Properly managing and documenting props is essential for creating reusable and maintainable React components.

---

### React props with detailed examples for better understanding:

# **1\. Data Props:**

Data props, also known as data properties, are a type of prop used in React components to pass data from a parent component to a child component. These props typically contain information that the child component needs to render its content or to perform certain operations. Data props can take various forms, including:

1. **Primitive Data Types:** Data props can consist of simple, primitive data types such as strings, numbers, booleans, or dates. For example, you might pass a title as a string or a count as a number to a child component.
    
    ```jsx
    <ChildComponent title="Welcome" count={42} />
    ```
    
2. **Objects:** Data props can be objects that contain structured data. This is useful when you need to pass multiple related values to the child component.
    
    ```jsx
    <ChildComponent user={{ name: "John", age: 30 }} />
    ```
    
3. **Arrays:** You can pass arrays as data props to provide lists of items or data sets to the child component.
    
    ```jsx
    <ChildComponent items={['apple', 'banana', 'cherry']} />
    ```
    
4. **Functions:** Data props can also be functions that the child component can call to perform specific actions or retrieve additional data.
    
    ```jsx
    <ChildComponent fetchData={fetchDataFunction} />
    ```
    

Data props are crucial for building dynamic and reusable React components because they allow you to customize the content and behavior of child components based on the data provided by their parent components. Inside the child component, you can access data props like regular JavaScript props using `props.propertyName`.

Data props are used to pass data from a parent component to a child component. Here's an example:

```jsx
// ParentComponent.js
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const greeting = "Hello, React!";
  const numbers = [1, 2, 3, 4, 5];

  return (
    <ChildComponent greeting={greeting} numbers={numbers} />
  );
}

// ChildComponent.js
import React from 'react';

function ChildComponent({ greeting, numbers }) {
  return (
    <div>
      <p>{greeting}</p>
      <ul>
        {numbers.map((number) => (
          <li key={number}>{number}</li>
        ))}
      </ul>
    </div>
  );
}
```

In this example, `greeting` and `numbers` are data props passed from the `ParentComponent` to the `ChildComponent`.

# **2.Event Props:**

Event props in React are a way to allow communication between parent and child components. They involve passing functions from a parent component to a child component as props. These functions can be triggered in response to specific events, such as button clicks, form submissions, or user interactions, allowing the child component to inform the parent component about the event occurrence.

Here's a breakdown of event props in React:

1. **Defining Event Handlers in Parent Component:**
    
    * In the parent component, you define functions to handle specific events.
        
    
    ```jsx
    // ParentComponent.js
    const handleButtonClick = () => {
      // Code to handle button click event
    };
    ```
    
2. **Passing Event Handlers to Child Component as Props:**
    
    * Pass the event handler functions down to the child component as props.
        
    
    ```jsx
    // ParentComponent.js
    <ChildComponent onClick={handleButtonClick} />
    ```
    
3. **Invoking Event Handlers in Child Component:**
    
    * In the child component, attach the event handler to an element's event (e.g., onClick, onChange).
        
    
    ```jsx
    // ChildComponent.js
    <button onClick={props.onClick}>Click Me</button>
    ```
    
    * When the button is clicked, the `handleButtonClick` function in the parent component will be executed.
        
4. **Passing Data Back to Parent Component:**
    
    * You can also pass data from the child component to the parent component using event props. For example, passing the input value from a form field.
        
    
    ```jsx
    // ParentComponent.js
    const handleInputChange = (inputValue) => {
      // Code to handle input change event with data
    };
    
    // ...
    
    <ChildComponent onInputChange={handleInputChange} />
    ```
    
    ```jsx
    // ChildComponent.js
    <input onChange={(e) => props.onInputChange(e.target.value)} />
    ```
    
    * In this case, the `handleInputChange` function in the parent component receives the input value whenever the user types in the input field.
        

By using event props, React components can maintain a clear separation of concerns and allow for reusability, as child components can trigger actions in their parent components without having to know the implementation details of those actions. Event props are a fundamental concept in React development, enabling the creation of interactive and dynamic user interfaces.

**Event props are used to pass callback functions from a parent component to a child component. Here's an example:**

```jsx
// ParentComponent.js
import React, { useState } from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <ChildComponent onIncrement={incrementCount} />
  );
}

// ChildComponent.js
import React from 'react';

function ChildComponent({ onIncrement }) {
  return (
    <button onClick={onIncrement}>Increment</button>
  );
}
```

In this example, the `ParentComponent` passes the `incrementCount` function as an event prop to the `ChildComponent`. When the button in the child component is clicked, it triggers the `onIncrement` function defined in the parent.

# **3\. Boolean Props:**

Here are examples for each of the topics related to boolean props in React:

**1\. Passing Boolean Props:**

* In the parent component, you can pass boolean props to a child component to enable or disable certain features or behaviors.
    

```jsx
// ParentComponent.js
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  return (
    <div>
      {/* Passing a boolean prop to ChildComponent */}
      <ChildComponent isDisabled={true} />
    </div>
  );
}

export default ParentComponent;
```

**2\. Using Boolean Props in Child Component:**

* In the child component, you can access and use the boolean prop to conditionally render content or change behavior.
    

```jsx
// ChildComponent.js
import React from 'react';

function ChildComponent(props) {
  return (
    <div>
      {/* Using the boolean prop to conditionally render content */}
      {props.isDisabled ? (
        <button disabled>Disabled Button</button>
      ) : (
        <button>Enabled Button</button>
      )}
    </div>
  );
}

export default ChildComponent;
```

**3\. Toggle Features or Behavior:**

* Boolean props are often used to toggle features like enabling/disabling buttons, showing/hiding elements, or controlling the behavior of a component.
    

Here's a more detailed example of using a boolean prop to toggle the visibility of an element:

```jsx
// ChildComponent.js
import React from 'react';

function ChildComponent(props) {
  return (
    <div>
      {/* Toggle the visibility of a message based on a boolean prop */}
      {props.showMessage && <p>This message is visible.</p>}
    </div>
  );
}

export default ChildComponent;
```

In this example, the `showMessage` boolean prop controls whether the `<p>` element is rendered or not.

**Common Use Cases:**

* **Conditional Rendering:**
    

```jsx
// ParentComponent.js
import React, { useState } from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const [isModalOpen, setIsModalOpen] = useState(false);

  return (
    <div>
      <button onClick={() => setIsModalOpen(!isModalOpen)}>Toggle Modal</button>
      {/* Conditionally render a modal based on the boolean prop */}
      <ChildComponent isOpen={isModalOpen} />
    </div>
  );
}

export default ParentComponent;
```

* **Styling:**
    

```jsx
// ChildComponent.js
import React from 'react';

function ChildComponent(props) {
  // Apply different styles based on a boolean prop
  const buttonStyle = props.isPrimary ? 'primary-button' : 'secondary-button';

  return (
    <div>
      <button className={buttonStyle}>Click Me</button>
    </div>
  );
}

export default ChildComponent;
```

* **Controlled Behavior:**
    

```jsx
// ChildComponent.js
import React from 'react';

function ChildComponent(props) {
  // Conditionally enable or disable a button based on a boolean prop
  return (
    <div>
      <button onClick={props.onClick} disabled={props.isDisabled}>
        Click Me
      </button>
    </div>
  );
}

export default ChildComponent;
```

* **Feature Toggles:**
    

```jsx
// ParentComponent.js
import React, { useState } from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const [newFeatureEnabled, setNewFeatureEnabled] = useState(true);

  return (
    <div>
      {/* Enable or disable a new feature using a boolean prop */}
      <ChildComponent isNewFeatureEnabled={newFeatureEnabled} />
    </div>
  );
}

export default ParentComponent;
```

In these examples, boolean props are used to control various aspects of component behavior, rendering, styling, and feature toggles in React applications.

Boolean props are used to control the behavior or appearance of a component. Here's an example:

```jsx
// ToggleButton.js
import React from 'react';

function ToggleButton({ isToggled, onToggle }) {
  return (
    <button onClick={onToggle}>
      {isToggled ? 'ON' : 'OFF'}
    </button>
  );
}
```

In this example, the `isToggled` prop controls whether the button displays 'ON' or 'OFF', and the `onToggle` prop is an event handler to toggle the state.

# **4\. Children Props:**

Here are examples for each of the topics related to children props in React:

**1\. Passing Children Props:**

* In the parent component, you can pass child elements or components as children props to the child component.
    

```jsx
// ParentComponent.js
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  return (
    <div>
      {/* Passing child elements as children props */}
      <ChildComponent>
        <p>This is a child paragraph.</p>
        <button>Click Me</button>
      </ChildComponent>
    </div>
  );
}

export default ParentComponent;
```

**2\. Accessing and Rendering Children:**

* In the child component, you can access the children passed to it using the `props.children` property. You can then render or manipulate these children as needed.
    

```jsx
// ChildComponent.js
import React from 'react';

function ChildComponent(props) {
  return (
    <div>
      <h2>Child Component</h2>
      <div className="content">
        {/* Accessing and rendering the children */}
        {props.children}
      </div>
    </div>
  );
}

export default ChildComponent;
```

In this example, the child elements (e.g., `<p>` and `<button>`) passed to `ChildComponent` within the `<ChildComponent>` tags are accessed and rendered within the `ChildComponent` using `props.children`.

**Use Cases for Children Props:**

1. **Layout Components:**
    
    * Children props are commonly used for creating layout components that wrap and style their child content. Here's an example of a simple layout component:
        

```jsx
// LayoutComponent.js
import React from 'react';

function LayoutComponent(props) {
  return (
    <div className="layout">
      <header>{props.header}</header>
      <main>{props.children}</main>
      <footer>{props.footer}</footer>
    </div>
  );
}

export default LayoutComponent;
```

1. **Conditional Rendering:**
    
    * You can conditionally render child components based on certain conditions in the parent component. For example, rendering different child components based on a boolean prop:
        

```jsx
// ParentComponent.js
import React from 'react';
import ChildA from './ChildA';
import ChildB from './ChildB';

function ParentComponent(props) {
  return (
    <div>
      {props.condition ? <ChildA /> : <ChildB />}
    </div>
  );
}

export default ParentComponent;
```

1. **Component Composition:**
    
    * Children props enable you to compose complex components by combining multiple child components within a parent component. For example, creating a Tab component:
        

```jsx
// Tab.js
import React from 'react';

function Tab(props) {
  return (
    <div>
      {/* Render the selected tab content */}
      {props.children}
    </div>
  );
}

export default Tab;
```

1. **Transclusion:**
    
    * Transclusion allows you to inject content into a component's template. Here's an example of a Card component that transcludes content:
        

```jsx
// Card.js
import React from 'react';

function Card(props) {
  return (
    <div className="card">
      {props.children}
    </div>
  );
}

export default Card;
```

1. **Higher-Order Components (HOCs):**
    
    * Children props are used in higher-order components to wrap and enhance the functionality of child components. Here's a simplified example of an HOC:
        

```jsx
// withLogging.js
import React from 'react';

function withLogging(Component) {
  return function WithLogging(props) {
    console.log(`Rendered ${Component.name}`);
    return <Component {...props} />;
  };
}

export default withLogging;
```

In these examples, children props are utilized for various purposes, including layout, conditional rendering, component composition, transclusion, and higher-order components, demonstrating their versatility in creating dynamic and customizable user interfaces in React.

**Children props allow passing React elements or components as children to a parent component. Here's an example:**

```jsx
// Card.js
import React from 'react';

function Card({ children }) {
  return (
    <div className="card">
      {children}
    </div>
  );
}
```

In this example, the `Card` component can receive any content as its children, allowing for flexible composition.

```jsx
// Usage of Card component
<Card>
  <h2>Title</h2>
  <p>Content goes here.</p>
</Card>
```

# **5\. Style Props:**

Style props in React are used to pass CSS styles or class names as properties to a component, allowing for dynamic styling based on props. These props are commonly used to customize the appearance of a component or to conditionally apply styles based on certain conditions. Here's how style props work:

1. **Passing Style Props:**
    
    * In the parent component, you can pass style props as objects containing CSS properties and values to a child component.
        
    
    ```jsx
    // ParentComponent.js
    import React from 'react';
    import ChildComponent from './ChildComponent';
    
    function ParentComponent() {
      const buttonStyle = {
        backgroundColor: 'blue',
        color: 'white',
        fontSize: '16px',
      };
    
      return (
        <div>
          <ChildComponent customStyle={buttonStyle} />
        </div>
      );
    }
    
    export default ParentComponent;
    ```
    
2. **Accessing and Applying Styles:**
    
    * In the child component, you can access the style props passed to it using `props.customStyle` and apply these styles to the rendered elements.
        
    
    ```jsx
    // ChildComponent.js
    import React from 'react';
    
    function ChildComponent(props) {
      return (
        <div>
          <button style={props.customStyle}>Styled Button</button>
        </div>
      );
    }
    
    export default ChildComponent;
    ```
    

In this example, the `ParentComponent` defines a `buttonStyle` object containing CSS properties and values. It then passes this object as a `customStyle` prop to the `ChildComponent`. Inside the `ChildComponent`, the styles are applied to the `<button>` element using the `style` prop.

### Use Cases for Style Props:

1. **Dynamic Styling:** Style props allow you to dynamically change the appearance of a component based on the props or state of the parent component.
    
2. **Customizable Components:** You can create customizable components by allowing users of your component to pass custom styles.
    
3. **Conditional Styling:** Style props are often used to conditionally apply styles based on specific conditions, such as hover effects or error states.
    
4. **Component Libraries:** When building component libraries, style props provide users with flexibility in customizing the appearance of components.
    
5. **Responsive Design:** Style props can be used for responsive design, allowing components to adapt their styles based on screen size or device type.
    

It's important to note that while inline styles using the `style` prop are a common way to apply styles, you can also use class names and external CSS libraries to style components based on props.

Style props are a versatile tool in React development, enabling you to create visually appealing and flexible user interfaces while maintaining the benefits of component-based architecture.

**Style props are used to pass CSS styles or class names to a component for custom styling. Here's an example:**

```jsx
// StyledButton.js
import React from 'react';

function StyledButton({ style, className, onClick }) {
  return (
    <button style={style} className={className} onClick={onClick}>
      Click me
    </button>
  );
}
```

In this example, you can customize the button's style and class name by passing appropriate props.

```jsx
// Usage of StyledButton component
<StyledButton
  style={{ backgroundColor: 'blue', color: 'white' }}
  className="custom-button"
  onClick={() => alert('Button clicked!')}
/>
```

# **6\. Configuration Props:**

Configuration props, often referred to as config props, are a type of prop used in React components to customize and configure the behavior of a component. These props allow you to fine-tune how a component functions or how it appears, making the component adaptable to various use cases. Here's how configuration props work:

1. **Passing Configuration Props:**
    
    * In the parent component, you can pass configuration props to a child component when rendering it.
        
    
    ```jsx
    // ParentComponent.js
    import React from 'react';
    import ChildComponent from './ChildComponent';
    
    function ParentComponent() {
      const config = {
        option1: true,
        option2: false,
        option3: 'custom-value',
      };
    
      return (
        <div>
          <ChildComponent config={config} />
        </div>
      );
    }
    
    export default ParentComponent;
    ```
    
2. **Accessing Configuration Props:**
    
    * In the child component, you can access the configuration props using `props.config` and use them to modify the component's behavior or appearance.
        
    
    ```jsx
    // ChildComponent.js
    import React from 'react';
    
    function ChildComponent(props) {
      const { option1, option2, option3 } = props.config;
    
      // Use the configuration props to customize behavior
      // ...
    
      return (
        <div>
          {/* Render the component with custom configuration */}
        </div>
      );
    }
    
    export default ChildComponent;
    ```
    

In this example, the `ParentComponent` defines a `config` object with various configuration options and passes it as a `config` prop to the `ChildComponent`. Inside the `ChildComponent`, you can access these options and use them to customize the component's behavior as needed.

### Use Cases for Configuration Props:

1. **Feature Toggles:** Configuration props are often used to enable or disable specific features or functionalities within a component.
    
2. **Customization:** They allow users of a component to customize its appearance or behavior based on their needs.
    
3. **Conditional Rendering:** Configuration props can be used to conditionally render parts of a component's UI or control which elements are displayed.
    
4. **Localization:** Configuration props can determine the language or locale used in a component for internationalization purposes.
    
5. **Advanced Settings:** They can be used to provide advanced settings or options for a component, such as animation speed, data sources, or API endpoints.
    
6. **Theming:** Configuration props are useful for theming a component by allowing users to specify colors, fonts, or other styling details.
    

Configuration props provide a flexible way to make your React components versatile and adaptable, as users can customize them according to their specific requirements without needing to modify the component's source code.

**Configuration props are used to customize the behavior of a component. Here's an example:**

```jsx
// ConfigurableInput.js
import React from 'react';

function ConfigurableInput({ type, placeholder, value, onChange }) {
  return (
    <input
      type={type}
      placeholder={placeholder}
      value={value}
      onChange={onChange}
    />
  );
}
```

In this example, `type`, `placeholder`, `value`, and `onChange` are configuration props that control the input element's behavior.

```jsx
// Usage of ConfigurableInput component
<ConfigurableInput
  type="text"
  placeholder="Enter your name"
  value={name}
  onChange={(e) => setName(e.target.value)}
/>
```

These examples illustrate the different types of React props and how they can be used to create flexible and reusable components. The specific props you use in your components will depend on your application's requirements and design.

# **7\. Router Props (for React Router):**

In React applications using React Router for navigation, you can access router-related information through props provided by React Router. Here's an example:

```jsx
import React from 'react';
import { BrowserRouter as Router, Route, Link } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
          </ul>
        </nav>

        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
      </div>
    </Router>
  );
}

function Home(props) {
  return (
    <div>
      <h2>Home</h2>
      {/* Access router props */}
      <p>Current URL: {props.match.url}</p>
    </div>
  );
}

function About(props) {
  return (
    <div>
      <h2>About</h2>
      {/* Access router props */}
      <p>Current URL: {props.match.url}</p>
    </div>
  );
}
```

In this example, React Router provides `props.match` to access information about the current route, including the URL.

# **8\. Context Props (for Context API):**

Context props are a type of props used in React components when working with the Context API. The Context API is a built-in feature in React that allows you to manage global state and share data between components without having to pass props through every level of the component tree. Context props provide access to values stored in a context and allow components to consume and interact with that shared state. Here's how context props work in the context of the Context API:

1. **Creating a Context:**
    
    * First, you need to create a context using the `React.createContext()` function. This context will hold the shared state or data that you want to make accessible to components within a certain scope.
        
    
    ```jsx
    // MyContext.js
    import React from 'react';
    
    const MyContext = React.createContext();
    
    export default MyContext;
    ```
    
2. **Providing Context Value:**
    
    * You then need to wrap your component tree with a `Provider` component from the context. The `Provider` component allows you to set the value that will be shared with all components that are descendants of it.
        
    
    ```jsx
    // App.js
    import React from 'react';
    import MyContext from './MyContext';
    
    function App() {
      const sharedData = "This is shared data";
    
      return (
        <MyContext.Provider value={sharedData}>
          {/* Your component tree */}
        </MyContext.Provider>
      );
    }
    
    export default App;
    ```
    
3. **Accessing Context Props:**
    
    * In the child components that need access to the shared data, you can use the `useContext` hook or the `Consumer` component to access the context props.
        
    
    Using `useContext` (functional component):
    
    ```jsx
    // ChildComponent.js
    import React, { useContext } from 'react';
    import MyContext from './MyContext';
    
    function ChildComponent() {
      const sharedData = useContext(MyContext);
    
      return (
        <div>
          <p>Shared Data: {sharedData}</p>
        </div>
      );
    }
    
    export default ChildComponent;
    ```
    
    Using `Consumer` (class component):
    
    ```jsx
    // ChildComponent.js
    import React from 'react';
    import MyContext from './MyContext';
    
    class ChildComponent extends React.Component {
      render() {
        return (
          <MyContext.Consumer>
            {(sharedData) => (
              <div>
                <p>Shared Data: {sharedData}</p>
              </div>
            )}
          </MyContext.Consumer>
        );
      }
    }
    
    export default ChildComponent;
    ```
    

Context props allow you to share data, state, or configuration settings across different parts of your React application without the need for explicit prop drilling. This is especially useful for managing global state, themes, user authentication, and other shared information.

### Common use cases for context props in a React application include:

1. **Theme and Styling**: Context props can be used to manage themes and styles throughout your application. This allows you to dynamically switch between themes or provide a consistent styling approach across components.
    
2. **Global State Management**: Context props are often used for managing global application state that needs to be accessed and modified by multiple components. This can include user authentication status, shopping cart contents, or any other shared data.
    
3. **Localization and Internationalization**: When building a multilingual application, context props can help manage the selected language and provide translated strings to components based on the user's preferences.
    
4. **User Authentication**: Context props can store information about the authenticated user, such as their user ID, username, or authentication token. This information can be made accessible to components that need to interact with user-specific data.
    
5. **Routing and Navigation**: Storing the current route or navigation state in context props can be useful for components that need to respond to changes in the URL or control navigation behavior.
    
6. **User Preferences**: Context props can be used to manage user preferences, such as dark mode settings, font size preferences, or other customizations that affect the user interface.
    
7. **Form State Management**: When building complex forms that involve multiple components, context props can help manage form state, input validation, and form submission logic.
    
8. **User Notifications**: Storing information about notifications or alerts in context can allow various components to display notifications to the user or respond to specific events.
    
9. **Permission Control**: Managing user roles and permissions in context props can help control access to certain features or sections of your application based on the user's role.
    
10. **Data Fetching and API Calls**: Context props can be used to encapsulate data fetching logic and API calls, making it easier to share data and manage loading and error states across components.
    
11. **WebSocket or Real-Time Updates**: If your application relies on real-time updates via WebSockets or other technologies, context props can help manage and distribute real-time data to components.
    
12. **Managing Modal Dialogs**: Context can be used to control the visibility and content of modal dialogs or pop-up windows that may appear throughout your application.
    
13. **Redux Replacement**: In some cases, context props can be used as a simpler alternative to state management libraries like Redux, especially for smaller to medium-sized applications.
    

Context props are a flexible tool for managing shared state and configuration data in React applications. They help reduce the need to pass props manually through multiple levels of components, making your code more maintainable and efficient.

**In applications using the React Context API, components can receive context values via props. Here's an example:**

```jsx
import React, { useContext } from 'react';

// Create a context
const ThemeContext = React.createContext('light');

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  // Access context using useContext hook
  const theme = useContext(ThemeContext);

  return (
    <div>
      <p>Current Theme: {theme}</p>
    </div>
  );
}
```

In this example, the `Toolbar` component accesses the theme information from the `ThemeContext` using the `useContext` hook.

# **9\. Custom Props:**

Custom props refer to props that you define in your React components based on the specific needs and functionality of those components. Unlike some of the more standardized props like data props or event props, custom props are unique to your component and are used to configure, control, or provide data to that component. Here's how custom props work:

1. **Defining Custom Props:**
    
    * In your component's definition, you can declare custom props by specifying them as parameters in the component's functional or class definition.
        
    
    ```jsx
    // MyComponent.js
    import React from 'react';
    
    function MyComponent(props) {
      // Custom props
      const { title, color, onClick } = props;
    
      return (
        <div style={{ backgroundColor: color }}>
          <h2>{title}</h2>
          <button onClick={onClick}>Click Me</button>
        </div>
      );
    }
    
    export default MyComponent;
    ```
    
    In this example, `title`, `color`, and `onClick` are custom props defined for the `MyComponent`.
    
2. **Passing Custom Props:**
    
    * When you use the `MyComponent` in another part of your application, you pass values for these custom props as attributes.
        
    
    ```jsx
    // ParentComponent.js
    import React from 'react';
    import MyComponent from './MyComponent';
    
    function ParentComponent() {
      const handleButtonClick = () => {
        alert('Button clicked!');
      };
    
      return (
        <div>
          <MyComponent title="Custom Component" color="blue" onClick={handleButtonClick} />
        </div>
      );
    }
    
    export default ParentComponent;
    ```
    
    In this example, `title`, `color`, and `onClick` are custom props passed to the `MyComponent` component when it is used in `ParentComponent`.
    

### Use Cases for Custom Props:

Custom props can serve a wide range of purposes and can be tailored to the specific requirements of your components. Some common use cases include:

* **Configuration Props:** Custom props can be used to configure the behavior or appearance of a component, as shown in the above example.
    
* **Data Props:** You can use custom props to pass data from a parent component to a child component.
    
* **Event Props:** Custom props can also represent event handlers that allow a child component to communicate with its parent or trigger actions.
    
* **Conditional Props:** Custom props can control conditional rendering or behavior within a component based on certain conditions.
    
* **Styling Props:** Custom props can include style-related information, such as CSS classes or inline styles.
    

Custom props are essential for building reusable and composable React components. They allow you to create components that can be customized and adapted to different use cases while encapsulating their functionality and behavior. Custom props are at the heart of building flexible and reusable UI components in React.

**Custom props are user-defined props specific to a component's functionality. These can vary widely depending on the component's purpose. For example, a custom prop for testing might look like this:**

```jsx
<MyComponent data-testid="my-component" />
```

In this case, the `data-testid` prop is not a built-in React prop but is used to set a test ID for the component, making it easier to target in testing.

# **10\. Controlled and Uncontrolled Props:**

Controlled and uncontrolled props are terms often used in the context of form components in React. They refer to how you manage and handle the data input and state of form elements such as input fields, checkboxes, and radio buttons. Understanding the difference between controlled and uncontrolled components is crucial for handling user input effectively in React.

**Controlled Components:**

A controlled component is a form element whose value is controlled by React through its state. In a controlled component, you set the value of the form element explicitly through its props (usually using the `value` prop) and handle changes through event handlers, such as `onChange`. The component's state is the single source of truth for the value of the input element.

Here's an example of a controlled input element:

```jsx
import React, { useState } from 'react';

function ControlledInput() {
  const [inputValue, setInputValue] = useState('');

  const handleInputChange = (event) => {
    setInputValue(event.target.value);
  };

  return (
    <input
      type="text"
      value={inputValue} // Controlled by React state
      onChange={handleInputChange} // Handles changes
    />
  );
}

export default ControlledInput;
```

In this example, the `inputValue` state variable controls the input element's value. When the user types into the input field, the `handleInputChange` function updates the state, which in turn updates the input field's value.

**Uncontrolled Components:**

An uncontrolled component is a form element whose value is not directly controlled by React. Instead, the input element keeps its own internal state. Uncontrolled components are often used when you want to integrate React with non-React code or libraries that manage their own state.

Here's an example of an uncontrolled input element:

```jsx
import React, { useRef } from 'react';

function UncontrolledInput() {
  const inputRef = useRef(null);

  const handleButtonClick = () => {
    alert(`Input value: ${inputRef.current.value}`);
  };

  return (
    <div>
      <input type="text" ref={inputRef} />
      <button onClick={handleButtonClick}>Get Input Value</button>
    </div>
  );
}

export default UncontrolledInput;
```

In this example, the input element uses the `ref` to access its value directly without involving React's state management. When the button is clicked, the value is retrieved from the input element using `inputRef.current.value`.

**Choosing Between Controlled and Uncontrolled Components:**

* Use controlled components when you want to keep React as the single source of truth for the form element's state, enabling you to validate, manipulate, or transform the input value before submission.
    
* Use uncontrolled components when you need to integrate React with non-React code or when you want to delegate the management of state to the DOM or external libraries.
    

The choice between controlled and uncontrolled components depends on your specific use case and requirements. Controlled components provide more control and flexibility over form elements but may involve more code. Uncontrolled components can be simpler but may be less integrated with React's state management.

Controlled and uncontrolled props refer to how a component manages its state. Controlled components have their state controlled by a parent component through props, while uncontrolled components manage their state internally.

Here's an example of a controlled input component:

```jsx
import React, { useState } from 'react';

function ControlledInput({ value, onChange }) {
  return <input type="text" value={value} onChange={onChange} />;
}

function App() {
  const [inputValue, setInputValue] = useState('');

  const handleInputChange = (e) => {
    setInputValue(e.target.value);
  };

  return (
    <ControlledInput value={inputValue} onChange={handleInputChange} />
  );
}
```

In this example, the `ControlledInput` component is controlled by the parent component (`App`) through the `value` and `onChange` props.

Uncontrolled components, on the other hand, manage their state internally without relying on props to control their value.

These examples illustrate the various types of React props and how they can be used to build flexible and versatile React components based on your application's needs and design patterns. Properly managing and documenting props is essential for creating maintainable and reusable components in React.

---

# Props validation

In React, prop validation is a technique used to specify the expected types and requirements of the props that a component should receive. Prop validation helps you catch and prevent common errors and bugs by checking that the props passed to a component meet the specified criteria. React provides a way to define prop types using a package called `prop-types` (prior to React 16.3, prop types were declared as a property of the component class).

Here's how to use prop validation in React:

1. **Install the** `prop-types` Package:
    
    * If you haven't already, you need to install the `prop-types` package. You can do this using npm or yarn:
        
    
    ```plaintext
    npm install prop-types
    ```
    
    or
    
    ```plaintext
    yarn add prop-types
    ```
    
2. **Import** `prop-types` in Your Component:
    
    * Import the `prop-types` package at the top of your component file.
        
    
    ```jsx
    import PropTypes from 'prop-types';
    ```
    
3. **Define Prop Types for Your Component:**
    
    * Inside your component, you can define the expected prop types using the `PropTypes` object. For example:
        
    
    ```jsx
    MyComponent.propTypes = {
      name: PropTypes.string.isRequired,
      age: PropTypes.number,
      email: PropTypes.string,
      onClick: PropTypes.func.isRequired,
    };
    ```
    
    In this example, we define prop types for a component called `MyComponent`. We expect `name` to be a required string, `age` to be an optional number, `email` to be an optional string, and `onClick` to be a required function.
    
4. **Use Prop Validation to Check Props:**
    
    * React will automatically check the prop types and issue warnings or errors in the console if the props don't match the defined types or requirements.
        

Here's a complete example:

```jsx
import React from 'react';
import PropTypes from 'prop-types';

function MyComponent(props) {
  return (
    <div>
      <h2>Hello, {props.name}!</h2>
      <p>Age: {props.age}</p>
      <p>Email: {props.email}</p>
      <button onClick={props.onClick}>Click Me</button>
    </div>
  );
}

MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number,
  email: PropTypes.string,
  onClick: PropTypes.func.isRequired,
};

export default MyComponent;
```

In this example, we've defined prop types using `PropTypes` for the `MyComponent` component. If a required prop (`name` and `onClick` in this case) is not provided or if the provided prop doesn't match the expected type, React will issue a warning in the console.

Prop validation is a helpful tool for improving the reliability and maintainability of your React code by documenting the expected props and catching issues early in development. It's especially useful when building larger and more complex components and applications.

# Props drilling

Prop drilling, also known as prop passing, is a challenge that arises in React when you need to pass data from a top-level component to a deeply nested child component. It occurs when data needs to be passed through multiple intermediary components that do not actually use the data themselves. Prop drilling can make your code less maintainable and harder to understand, as it requires you to pass props through many components that don't need them for their own functionality.

Here's how prop drilling works:

1. **Top-Level Component:** You have a top-level component that contains some data that you want to pass down to a deeply nested child component.
    
2. **Intermediate Components:** Between the top-level component and the target child component, there may be several intermediary components that don't actually use the data but are responsible for passing the data down as props.
    
3. **Target Child Component:** Finally, you have the child component at the bottom of the component hierarchy that needs access to the data.
    

Here's an example to illustrate prop drilling:

```jsx
// TopLevelComponent.js
import React, { useState } from 'react';
import IntermediateComponent from './IntermediateComponent';

function TopLevelComponent() {
  const [data, setData] = useState('Hello from TopLevelComponent');

  return (
    <div>
      <IntermediateComponent data={data} />
    </div>
  );
}

export default TopLevelComponent;
```

```jsx
// IntermediateComponent.js
import React from 'react';
import TargetChildComponent from './TargetChildComponent';

function IntermediateComponent(props) {
  return (
    <div>
      <TargetChildComponent data={props.data} />
    </div>
  );
}

export default IntermediateComponent;
```

```jsx
// TargetChildComponent.js
import React from 'react';

function TargetChildComponent(props) {
  return <div>{props.data}</div>;
}

export default TargetChildComponent;
```

In this example, `data` is being passed from `TopLevelComponent` to `IntermediateComponent` and then to `TargetChildComponent`. However, `IntermediateComponent` does not use `data` for its own functionality; it merely passes it down. This is an example of prop drilling.

While prop drilling is a common pattern in React, it can lead to several issues:

* It makes the code harder to maintain, as you need to track the flow of props through multiple components.
    
* It can result in unnecessary re-renders of intermediary components when the data changes.
    
* It can make the code less readable and less intuitive.
    

To mitigate prop drilling, you can consider using state management solutions like React Context API or a state management library like Redux. These tools allow you to share data across components without the need to pass props explicitly through every level of the component hierarchy.

# Destructuring props

Destructuring props is a common technique in React that allows you to extract values from the `props` object in a concise and readable way. It simplifies your component code by directly extracting the specific props you need and makes your component's usage clear and clean. Here's how to destructure props in React:

1. **Without Destructuring:**
    
    * Without destructuring, you access props directly from the `props` object.
        
    
    ```jsx
    function MyComponent(props) {
      return (
        <div>
          <p>Name: {props.name}</p>
          <p>Age: {props.age}</p>
        </div>
      );
    }
    ```
    
2. **With Destructuring:**
    
    * With destructuring, you extract the props you need within the function's parameter list.
        
    
    ```jsx
    function MyComponent({ name, age }) {
      return (
        <div>
          <p>Name: {name}</p>
          <p>Age: {age}</p>
        </div>
      );
    }
    ```
    

By using destructuring in the parameter list of the function, you directly create variables `name` and `age` from the corresponding props, which makes your code cleaner and more readable.

### Destructuring Default Values:

You can also provide default values when destructuring props to handle cases where a prop may not be defined:

```jsx
function MyComponent({ name = 'Unknown', age = 0 }) {
  return (
    <div>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </div>
  );
}
```

In this example, if the `name` or `age` props are not provided when using `MyComponent`, default values of `'Unknown'` and `0` will be used.

### Destructuring Nested Props:

You can also destructure nested props when dealing with complex data structures. For example, if you have an object prop:

```jsx
function UserProfile({ user }) {
  const { name, email } = user;
  return (
    <div>
      <p>Name: {name}</p>
      <p>Email: {email}</p>
    </div>
  );
}
```

Here, we destructure the `user` object to extract the `name` and `email` properties.

Destructuring props is a convenient way to improve the readability of your component code and make it more maintainable, especially in cases where you're dealing with a large number of props or deeply nested data structures.
