---
title: "My Hand notes of React JS"
seoTitle: "Custom function like useState Hook"
seoDescription: "The userProfile function initializes a user object with properties like name, age, and email.

It returns an array with two elements:"
datePublished: Sat Oct 07 2023 01:11:43 GMT+0000 (Coordinated Universal Time)
cuid: clnfcb1vq000609l54h0253ew
slug: my-hand-notes-of-react-js
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/4d046e565d0de96a87080795637b2800.jpeg
tags: javascript, reactjs

---

# Custom function like `useState` Hook

```jsx
function userProfile() {
  let user = {
    name: "",
    age: 0,
    email: "",
  };

  function setUser(name, age, email) {
    user.name = name;
    user.age = age;
    user.email = email;
  }

  function getUserData() {
    return user;
  }

  return [getUserData, setUser];
}

const [userData, setUser] = userProfile();

setUser("John Doe", 30, "johndoe@example.com");

console.log("User Data:", userData());
// Output: User Data: { name: 'John Doe', age: 30, email: 'johndoe@example.com' }

// You can also update user data using setUser
setUser("Alice Smith", 25, "alice.smith@example.com");

console.log("Updated User Data:", userData());
// Output: Updated User Data: { name: 'Alice Smith', age: 25, email: 'alice.smith@example.com' }

```

In this example:

* The `userProfile` function initializes a `user` object with properties like name, age, and email.
    
* It returns an array with two elements:
    
    * `getUserData`: Returns the current user data.
        
    * `setUser`: Allows you to set user data.
        

You can invoke `userProfile()` to create an instance, set user data using `setUser`, and retrieve user data using `userData()`. This demonstrates the desired syntax you mentioned.

---

# Creating a similar function

Creating a function similar to `useState` for your custom library called `useFunc` would involve implementing a state management mechanism that allows components to manage and update their state. Below is a simple example of how you can create a `useFunc` function that mimics the behavior of `useState`:

```jsx
// Your custom library - useFunc.js

// Create a variable to store the state and a function to update it.
let state;
let setStateCallbacks = [];

function useState(initialValue) {
  if (typeof state === 'undefined') {
    state = initialValue;
  }

  const currentIndex = setStateCallbacks.length;

  const setState = (newValue) => {
    state = newValue;
    setStateCallbacks.forEach((callback, index) => {
      if (index !== currentIndex) {
        callback(state);
      }
    });
  };

  setStateCallbacks.push(setState);

  return [state, setState];
}

function useFunc(initialValue) {
  return useState(initialValue);
}

export default useFunc;

```

In this example, we have `useState` that manages the state and provides a function to update it. We also have a global array `setStateCallbacks` to keep track of all the state update functions.

The `useFunc` function simply wraps `useState`, allowing you to use it in a way similar to `useState`:

```jsx
// Your component - MyComponent.js

import useFunc from 'useFunc';

function MyComponent() {
  const [count, setCount] = useFunc(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default MyComponent;

```

Now you can use `useFunc` in your components to manage state just like you would with `useState` from the React library. Remember that this is a simplified example, and the actual implementation of state management in React is more complex and handles various edge cases and optimizations. Depending on your use case, you might want to expand upon this example to handle more advanced scenarios.

---

# Converting the `userProfile` function into a functional component

Converting the `userProfile` function into a functional component using the `useState` hook, you can follow this example:

```jsx
import React, { useState } from 'react';

function UserProfile() {
  // Initialize user state with default values
  const [user, setUser] = useState({
    name: "",
    age: 0,
    email: "",
  });

  // Function to update user data
  const updateUser = (name, age, email) => {
    setUser({
      ...user, // Preserve existing user properties
      name: name,
      age: age,
      email: email,
    });
  };

  return (
    <div>
      <h1>User Profile</h1>
      <p>Name: {user.name}</p>
      <p>Age: {user.age}</p>
      <p>Email: {user.email}</p>

      <button onClick={() => updateUser("John Doe", 30, "johndoe@example.com")}>
        Set User Data
      </button>

      <button onClick={() => updateUser("Alice Smith", 25, "alice.smith@example.com")}>
        Update User Data
      </button>
    </div>
  );
}

export default UserProfile;

```

In this code:

1. We import `React` and `useState` from the React library.
    
2. We define the `UserProfile` functional component.
    
3. Inside the component, we use the `useState` hook to initialize the `user` state with default values.
    
4. We define the `updateUser` function to update the user data, merging the new data with the existing state using the spread operator (`...user`).
    
5. Within the component's JSX, we display the user's name, age, and email.
    
6. We provide buttons to set and update the user data, which trigger the `updateUser` function with the desired values.
    

This code converts your original `userProfile` function into a React functional component that uses the `useState` hook to manage and display user data.

---

---
