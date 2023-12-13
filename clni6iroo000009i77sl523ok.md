---
title: "JavaScript Promise"
seoTitle: "JavaScript Promise"
seoDescription: "Promises are widely used in real-world JavaScript applications for handling asynchronous operations and making code more readable and maintainable. Here are"
datePublished: Mon Oct 09 2023 00:53:04 GMT+0000 (Coordinated Universal Time)
cuid: clni6iroo000009i77sl523ok
slug: javascript-promise
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jLwVAUtLOAQ/upload/259fde5d8d203aa1de2d22f44800b2f3.jpeg
tags: javascript, javascript-promises

---

# JavaScript Promise

Promises are widely used in real-world JavaScript applications for handling asynchronous operations and making code more readable and maintainable. Here are some real-world applications of Promises:

1. **AJAX Requests**: Promises are commonly used for handling asynchronous HTTP requests, such as fetching data from APIs. Libraries like Axios and the Fetch API return Promises, making it easy to manage and chain multiple requests.
    
    ```javascript
    fetch('https://api.example.com/data')
      .then(response => {
        if (!response.ok) {
          throw new Error('Network response was not ok');
        }
        return response.json(); // Parse the response as JSON
      })
      .then(data => {
        // Handle the JSON data
        console.log(data);
      })
      .catch(error => {
        // Handle any errors that occurred during the fetch
        console.error('Fetch error:', error);
      });
    ```
    
2. **File Operations**: When reading or writing files asynchronously in a Node.js environment, Promises can simplify the code.
    
    ```javascript
    const fs = require('fs').promises;
    
    fs.readFile('file.txt', 'utf-8')
      .then(data => {
        // Handle file data
      })
      .catch(error => {
        // Handle error
      });
    ```
    
3. **Timeouts and Delays**: Promises can be used to create delayed execution or timeout mechanisms, ensuring that code executes after a specified time.
    
    ```javascript
    function delay(ms) {
      return new Promise(resolve => {
        setTimeout(resolve, ms);
      });
    }
    
    delay(2000)
      .then(() => {
        // Code to run after a 2-second delay
      });
    ```
    
4. **Database Operations**: Promises are often used in database interactions, such as connecting to databases, executing queries, and handling results.
    
    ```javascript
    const database = require('database-library');
    
    database.connect()
      .then(() => {
        return database.query('SELECT * FROM users');
      })
      .then(results => {
        // Handle database results
      })
      .catch(error => {
        // Handle database error
      });
    ```
    
5. **Parallel Processing**: When you need to perform multiple asynchronous operations concurrently and wait for all of them to complete, `Promise.all` is a powerful tool.
    
    ```javascript
    const promises = [fetchData1(), fetchData2(), fetchData3()];
    
    Promise.all(promises)
      .then(results => {
        // Handle all results when all Promises are resolved
      })
      .catch(error => {
        // Handle error if any Promise rejects
      });
    ```
    
6. **Animation and UI Updates**: Promises are used in animations and UI updates to ensure smooth transitions and interactions. Promises can be used to sequence animations or load assets asynchronously.
    
7. **Authentication and Authorization**: When implementing authentication flows, Promises can be used to manage login, token validation, and authorization checks.
    
    ```javascript
    authenticateUser()
      .then(user => {
        return validateToken(user.token);
      })
      .then(user => {
        return authorizeUser(user);
      })
      .catch(error => {
        // Handle authentication or authorization errors
      });
    ```
    

These are just a few examples of how Promises are applied in real-world JavaScript development. Promises simplify the handling of asynchronous code, making it more manageable and readable, while also providing a consistent pattern for error handling.

---

## another example

```javascript
const express = require('express');
const app = express();
const port = 3000;

app.use(express.json());

// Dummy database simulation
const database = {
  users: [
    { id: 1, name: 'John' },
    { id: 2, name: 'Jane' },
  ],
};

// Define a function that returns a Promise to fetch user by ID
function fetchUserById(id) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const user = database.users.find(user => user.id === id);
      if (user) {
        resolve(user);
      } else {
        reject('User not found');
      }
    }, 1000);
  });
}

// Define an endpoint that uses Promises
app.get('/users/:id', (req, res) => {
  const userId = parseInt(req.params.id);

  fetchUserById(userId)
    .then(user => {
      res.json(user);
    })
    .catch(error => {
      res.status(404).json({ error });
    });
});

// Start the server
app.listen(port, () => {
  console.log(`Server listening on port ${port}`);
});
```

## **Here's an example of using Promises in raw JavaScript to simulate fetching data from an API and displaying it on a webpage step by step:**

1. **Create an HTML File:**
    
    Create an HTML file (e.g., `index.html`) with the following content:
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Promise Example</title>
    </head>
    <body>
        <h1>User Information</h1>
        <div id="userInfo"></div>
    
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
2. **Create a JavaScript File:**
    
    Create a JavaScript file (e.g., `script.js`) in the same directory as your HTML file. This is where we'll write the JavaScript code:
    
    ```javascript
    // Define a function that returns a Promise to fetch user data from an API
    function fetchUserData() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          // Simulate fetching user data
          const userData = {
            id: 1,
            name: 'John Doe',
            email: 'john@example.com',
          };
          resolve(userData);
          // In a real application, you would use fetch() or another HTTP library here
        }, 2000);
      });
    }
    
    // Use the Promise to fetch user data and update the webpage
    function displayUserData() {
      const userInfoDiv = document.getElementById('userInfo');
      userInfoDiv.innerHTML = '<p>Loading user data...</p>';
    
      fetchUserData()
        .then(userData => {
          userInfoDiv.innerHTML = `
            <p>ID: ${userData.id}</p>
            <p>Name: ${userData.name}</p>
            <p>Email: ${userData.email}</p>
          `;
        })
        .catch(error => {
          userInfoDiv.innerHTML = `<p>Error: ${error}</p>`;
        });
    }
    
    // Call the displayUserData function to initiate the process
    displayUserData();
    ```
    
3. **Open the HTML File in a Browser:**
    
    Open the `index.html` file in a web browser. You will see a message "Loading user data..." on the webpage, and after a delay of 2 seconds (simulating an API request), the user data will be displayed on the page.
    

This example demonstrates how to use Promises to handle asynchronous operations, such as fetching data from an API, and update the webpage once the data is available. You can adapt this basic pattern to work with real API requests and more complex scenarios in your JavaScript applications.