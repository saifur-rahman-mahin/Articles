---
title: "Built-in Functions in PHP"
seoTitle: "Built-in Functions in PHP"
seoDescription: "PHP comes with a large number of built-in functions that cover a wide range of tasks. These functions are part of the PHP core and can be used without the"
datePublished: Fri Nov 24 2023 13:35:39 GMT+0000 (Coordinated Universal Time)
cuid: clpco0nah000z08jj980kevuf
slug: built-in-functions-in-php
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Bj6ENZDMSDY/upload/6a118b023e6edb8f08374e7f31a23584.jpeg
tags: php

---

# Built-in Functions in PHP

PHP comes with a large number of built-in functions that cover a wide range of tasks. These functions are part of the PHP core and can be used without the need for additional installations. Examples of built-in functions include `strlen()` for calculating the length of a string, `array_push()` for adding elements to an array, and `file_get_contents()` for reading the contents of a file.

It's not practical to provide an exhaustive list of all PHP functions categorized due to the extensive nature of PHP and the constant updates to the language. However, I can provide a general categorization of some common types of PHP functions:

1. **String Functions:**
    
    * Manipulation: `strlen()`, `str_replace()`, `substr()`
        
    * Case: `strtolower()`, `strtoupper()`, `ucfirst()`
        
    * Formatting: `printf()`, `sprintf()`
        
2. **Array Functions:**
    
    * Creation: `array()`, `range()`
        
    * Modification: `array_push()`, `array_pop()`, `array_merge()`
        
    * Iteration: `foreach()`, `array_map()`, `array_filter()`
        
    * Sorting: `sort()`, `asort()`, `ksort()`
        
3. **Math Functions:**
    
    * Basic: `round()`, `floor()`, `ceil()`
        
    * Random: `rand()`, `mt_rand()`, `shuffle()`
        
    * Mathematical Constants: `M_PI`, `M_E`
        
4. **File System Functions:**
    
    * Reading/Writing: `file_get_contents()`, `file_put_contents()`
        
    * File Info: `file_exists()`, `is_file()`, `filesize()`
        
    * Directories: `mkdir()`, `rmdir()`, `scandir()`
        
5. **Date and Time Functions:**
    
    * Formatting: `date()`, `strtotime()`, `strftime()`
        
    * Time Manipulation: `time()`, `mktime()`, `date_diff()`
        
6. **Database Functions:**
    
    * MySQLi: `mysqli_connect()`, `mysqli_query()`, `mysqli_fetch_assoc()`
        
    * PDO: `new PDO()`, `prepare()`, `execute()`
        
7. **Session Functions:**
    
    * Session Management: `session_start()`, `session_destroy()`, `$_SESSION`
        
8. **JSON Functions:**
    
    * Encoding/Decoding: `json_encode()`, `json_decode()`
        
9. **Regular Expression Functions:**
    
    * Matching: `preg_match()`, `preg_match_all()`
        
    * Replacement: `preg_replace()`
        
10. **HTTP Functions:**
    
    * Header: `header()`
        
    * cURL: `curl_init()`, `curl_exec()`
        
11. **Miscellaneous Functions:**
    
    * Variable Handling: `isset()`, `unset()`, `empty()`
        
    * Script Termination: `die()`, `exit()`
        

Remember that PHP is a versatile language, and its function library continues to evolve. For the most up-to-date and detailed information, always refer to the official PHP documentation: [PHP Manual](https://www.php.net/manual/en/).

---

---

---

# 1.String functions in PHP, categorized by their purposes:

1. **Manipulation:**
    
    * `strlen($string)`: Returns the length of a string.
        
    * `str_replace($search, $replace, $string)`: Replaces occurrences of a specified string with another string.
        
    * `substr($string, $start, $length)`: Returns a portion of a string.
        

Example:

```php
$str = "Hello, World!";
echo strlen($str);  // Outputs: 13
echo str_replace("Hello", "Hi", $str);  // Outputs: Hi, World!
echo substr($str, 0, 5);  // Outputs: Hello
```

1. **Case:**
    
    * `strtolower($string)`: Converts a string to lowercase.
        
    * `strtoupper($string)`: Converts a string to uppercase.
        
    * `ucfirst($string)`: Converts the first character of a string to uppercase.
        

Example:

```php
$str = "Hello, World!";
echo strtolower($str);  // Outputs: hello, world!
echo strtoupper($str);  // Outputs: HELLO, WORLD!
echo ucfirst($str);  // Outputs: Hello, World!
```

1. **Formatting:**
    
    * `printf($format, $arg1, $arg2, ...)`: Outputs a formatted string.
        
    * `sprintf($format, $arg1, $arg2, ...)`: Returns a formatted string.
        

Example:

```php
$name = "John";
$age = 25;
printf("Name: %s, Age: %d", $name, $age);
// Outputs: Name: John, Age: 25

$formattedString = sprintf("Name: %s, Age: %d", $name, $age);
// $formattedString now contains the formatted string
```

These functions are powerful tools for working with strings in PHP, providing flexibility and functionality for various tasks.

---

# 2.Array functions in PHP, categorized by their purposes:

1. **Creation:**
    
    * `array()`: Creates an array.
        
    * `range($start, $end, $step)`: Creates an array containing a range of elements.
        

Example:

```php
$array1 = array(1, 2, 3, 4, 5);
$array2 = range(1, 5);  // Same as array(1, 2, 3, 4, 5)
```

1. **Modification:**
    
    * `array_push($array, $value)`: Pushes one or more elements onto the end of an array.
        
    * `array_pop($array)`: Pops the element off the end of an array.
        
    * `array_merge($array1, $array2)`: Merges one or more arrays.
        

Example:

```php
$array = array(1, 2, 3);
array_push($array, 4, 5);  // $array is now array(1, 2, 3, 4, 5)
$lastElement = array_pop($array);  // $lastElement is 5, $array is array(1, 2, 3)
$array3 = array_merge($array1, $array2);  // Merges two arrays
```

1. **Iteration:**
    
    * `foreach($array as $key => $value)`: Iterates over each element in an array.
        
    * `array_map($callback, $array)`: Applies a callback function to each element of an array.
        
    * `array_filter($array, $callback)`: Filters elements of an array using a callback function.
        

Example:

```php
$array = array("apple" => "red", "banana" => "yellow", "grape" => "purple");

foreach ($array as $key => $value) {
    echo "Key: $key, Value: $value\n";
}

$uppercaseValues = array_map('strtoupper', $array);
// $uppercaseValues is array("apple" => "RED", "banana" => "YELLOW", "grape" => "PURPLE")

$filteredArray = array_filter($array, function ($value) {
    return $value === "yellow";
});
// $filteredArray is array("banana" => "yellow")
```

1. **Sorting:**
    
    * `sort($array)`: Sorts an array.
        
    * `asort($array)`: Sorts an array and maintains index association.
        
    * `ksort($array)`: Sorts an array by key.
        

Example:

```php
$array = array(3, 1, 4, 1, 5, 9, 2, 6, 5);

sort($array);  // $array is now sorted numerically: array(1, 1, 2, 3, 4, 5, 5, 6, 9)

asort($array);  // $array is sorted, but index association is maintained

$associativeArray = array("banana" => 2, "apple" => 5, "orange" => 1);
ksort($associativeArray);  // $associativeArray is sorted by keys: array("apple" => 5, "banana" => 2, "orange" => 1)
```

These array functions are fundamental for working with arrays in PHP, providing various tools for creation, modification, iteration, and sorting.

---

# 3.Math functions in PHP, categorized by their purposes:

1. **Basic:**
    
    * `round($number)`: Rounds a floating-point number to the nearest integer.
        
    * `floor($number)`: Rounds a floating-point number down to the nearest integer.
        
    * `ceil($number)`: Rounds a floating-point number up to the nearest integer.
        

Example:

```php
$number = 7.3;
echo round($number);  // Outputs: 7
echo floor($number);  // Outputs: 7
echo ceil($number);   // Outputs: 8
```

1. **Random:**
    
    * `rand($min, $max)`: Generates a random integer.
        
    * `mt_rand($min, $max)`: Generates a random integer using the Mersenne Twister algorithm.
        
    * `shuffle($array)`: Shuffles an array randomly.
        

Example:

```php
$randomNumber = rand(1, 10);  // Generates a random number between 1 and 10
$randomNumberMT = mt_rand(1, 10);  // Generates a random number using Mersenne Twister
$myArray = array(1, 2, 3, 4, 5);
shuffle($myArray);  // Shuffles the elements of $myArray randomly
```

1. **Mathematical Constants:**
    
    * `M_PI`: Represents the mathematical constant pi (π).
        
    * `M_E`: Represents the mathematical constant e.
        

Example:

```php
echo M_PI;  // Outputs: 3.1415926535898
echo M_E;   // Outputs: 2.718281828459
```

These functions and constants are useful for basic arithmetic operations, rounding, generating random numbers, and working with mathematical constants in PHP.

---

# 4.File system functions in PHP, categorized by their purposes:

1. **Reading/Writing:**
    
    * `file_get_contents($filename)`: Reads the entire contents of a file into a string.
        
    * `file_put_contents($filename, $data)`: Writes a string to a file.
        

Example:

```php
$contents = file_get_contents("example.txt");
echo $contents;

$data = "This is some content.";
file_put_contents("newfile.txt", $data);
```

1. **File Info:**
    
    * `file_exists($filename)`: Checks whether a file or directory exists.
        
    * `is_file($filename)`: Checks if the given path is a regular file.
        
    * `filesize($filename)`: Gets the size of a file.
        

Example:

```php
$file = "example.txt";

if (file_exists($file)) {
    echo "The file $file exists.";
}

if (is_file($file)) {
    echo "$file is a regular file.";
}

$size = filesize($file);
echo "The size of $file is $size bytes.";
```

1. **Directories:**
    
    * `mkdir($dirname)`: Creates a directory.
        
    * `rmdir($dirname)`: Removes a directory.
        
    * `scandir($directory)`: Returns an array of files and directories from the given directory.
        

Example:

```php
$directory = "my_directory";

if (!is_dir($directory)) {
    mkdir($directory);
    echo "Directory $directory created.";
}

// Do something with the directory...

// After finishing, remove the directory
rmdir($directory);
echo "Directory $directory removed.";
```

These file system functions in PHP are essential for working with files, directories, and their contents. They enable reading and writing data, checking file information, and managing directories in your PHP applications.

---

# 5.Date and time functions in PHP, categorized by their purposes:

1. **Formatting:**
    
    * `date($format, $timestamp)`: Formats a local time/date.
        
    * `strtotime($time, $now)`: Parses a time string into a Unix timestamp.
        
    * `strftime($format, $timestamp)`: Formats a local time/date according to the locale settings.
        

Example:

```php
echo date("Y-m-d H:i:s");  // Outputs the current date and time in the format: 2022-01-01 12:34:56

$timestamp = strtotime("next Sunday");
echo date("Y-m-d", $timestamp);  // Outputs the date of the next Sunday
```

1. **Time Manipulation:**
    
    * `time()`: Returns the current Unix timestamp.
        
    * `mktime($hour, $minute, $second, $month, $day, $year)`: Returns the Unix timestamp for a date.
        
    * `date_diff($date1, $date2)`: Returns the difference between two DateTime objects.
        

Example:

```php
$currentTimestamp = time();
echo "Current Unix timestamp: $currentTimestamp";

$customTimestamp = mktime(12, 0, 0, 1, 1, 2023);
echo "Custom Unix timestamp: $customTimestamp";

$date1 = new DateTime("2023-01-01");
$date2 = new DateTime("2023-12-31");
$interval = date_diff($date1, $date2);
echo "Difference between dates: " . $interval->format('%R%a days');
```

These date and time functions in PHP are fundamental for working with dates, times, and time intervals. They provide various tools for formatting, parsing, and manipulating date and time data in your PHP applications.

---

# 6.Database functions in PHP, categorized by their database access methods:

1. **MySQLi Functions:**
    
    * `mysqli_connect($host, $user, $password, $database)`: Opens a new connection to the MySQL server.
        
    * `mysqli_query($connection, $query)`: Performs a query on the database.
        
    * `mysqli_fetch_assoc($result)`: Fetches a result row as an associative array.
        

Example:

```php
$host = "localhost";
$user = "username";
$password = "password";
$database = "dbname";

// Create connection
$conn = mysqli_connect($host, $user, $password, $database);

// Check connection
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}

// Perform a query
$query = "SELECT * FROM users";
$result = mysqli_query($conn, $query);

// Fetch data
while ($row = mysqli_fetch_assoc($result)) {
    echo "User: " . $row["username"] . "<br>";
}

// Close connection
mysqli_close($conn);
```

1. **PDO Functions:**
    
    * `new PDO($dsn, $user, $password)`: Creates a new PDO instance representing a connection to a database.
        
    * `prepare($query)`: Prepares a statement for execution and returns a statement object.
        
    * `execute()`: Executes a prepared statement.
        

Example:

```php
$dsn = "mysql:host=localhost;dbname=dbname";
$user = "username";
$password = "password";

// Create a new PDO instance
$pdo = new PDO($dsn, $user, $password);

// Perform a query
$query = "SELECT * FROM users";
$stmt = $pdo->prepare($query);
$stmt->execute();

// Fetch data
while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {
    echo "User: " . $row["username"] . "<br>";
}

// Close connection (implicitly done when $pdo is unset)
unset($pdo);
```

These database functions in PHP, whether using MySQLi or PDO, are crucial for interacting with databases. They allow you to establish connections, perform queries, and retrieve data from databases in your PHP applications.

---

# 7.Session functions in PHP, categorized by their purposes:

1. **Session Management:**
    
    * `session_start()`: Starts a new session or resumes the existing session.
        
    * `session_destroy()`: Destroys all data registered to a session.
        
    * `$_SESSION`: A superglobal array used to store session variables.
        

Example:

```php
// Start or resume a session
session_start();

// Set a session variable
$_SESSION['user_id'] = 123;

// Retrieve a session variable
$userID = $_SESSION['user_id'];

// Destroy the session and log the user out
session_destroy();
```

In this example, `session_start()` initiates or resumes a session, `$_SESSION` is used to store and retrieve session variables, and `session_destroy()` ends the session, effectively logging the user out.

These session functions in PHP are fundamental for managing user sessions and persisting data across multiple pages during a user's visit to a website.

---

# 8.JSON functions in PHP, categorized by their purposes:

1. **Encoding/Decoding:**
    
    * `json_encode($data)`: Returns a JSON representation of the given data.
        
    * `json_decode($jsonString, $assoc = false, $depth = 512, $options = 0)`: Decodes a JSON string into a PHP variable.
        

Example:

```php
// Encoding an array to JSON
$data = array('name' => 'John', 'age' => 30, 'city' => 'New York');
$jsonString = json_encode($data);

echo $jsonString;
// Outputs: {"name":"John","age":30,"city":"New York"}

// Decoding a JSON string
$jsonString = '{"name":"Jane","age":25,"city":"San Francisco"}';
$decodedData = json_decode($jsonString, true);

echo $decodedData['name'];  // Outputs: Jane
```

In this example, `json_encode()` converts a PHP array into a JSON string, and `json_decode()` does the reverse, converting a JSON string into a PHP variable.

These JSON functions are essential for working with JSON data in PHP, allowing you to encode PHP data structures into JSON format and decode JSON strings back into PHP variables. This is particularly useful when interacting with APIs that send or receive data in JSON format.

---

# 9.Regular expression functions in PHP, categorized by their purposes:

1. **Matching:**
    
    * `preg_match($pattern, $subject, &$matches = null, $flags = 0, $offset = 0)`: Searches the subject string for a match to the regular expression pattern.
        
    * `preg_match_all($pattern, $subject, &$matches, $flags = PREG_PATTERN_ORDER, $offset = 0)`: Performs a global regular expression match.
        

Example:

```php
// Matching using preg_match
$subject = "Hello, World!";
$pattern = "/\bWorld\b/";

if (preg_match($pattern, $subject, $matches)) {
    echo "Match found: " . $matches[0];
} else {
    echo "No match found.";
}

// Matching using preg_match_all
$subject = "apple banana orange";
$pattern = "/\b\w+\b/";

if (preg_match_all($pattern, $subject, $matches)) {
    echo "Matches found: " . implode(", ", $matches[0]);
} else {
    echo "No matches found.";
}
```

1. **Replacement:**
    
    * `preg_replace($pattern, $replacement, $subject, $limit = -1, &$count = null)`: Performs a regular expression search and replace.
        

Example:

```php
$subject = "apple banana orange";
$pattern = "/\b\w+\b/";
$replacement = "fruit";

$result = preg_replace($pattern, $replacement, $subject);

echo $result;
// Outputs: fruit fruit fruit
```

In these examples, regular expression functions are used for matching patterns in strings and for replacing matched patterns with new values. Regular expressions provide powerful and flexible tools for string manipulation in PHP.

---

# 10.HTTP functions in PHP, categorized by their purposes:

1. **Header:**
    
    * `header($header, $replace = true, $http_response_code = null)`: Send a raw HTTP header to the browser.
        

Example:

```php
// Set a custom header
header("Content-Type: application/json");

// Redirect to another page
header("Location: https://example.com");
exit;  // Ensure that no further code is executed after a redirect
```

The `header()` function is often used to send HTTP headers, such as setting the content type or redirecting the user to another page.

1. **cURL:**
    
    * `curl_init()`: Initializes a new cURL session.
        
    * `curl_exec($ch)`: Executes the cURL session.
        

Example:

```php
// Initialize cURL session
$ch = curl_init();

// Set cURL options
curl_setopt($ch, CURLOPT_URL, "https://api.example.com/data");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

// Execute cURL session and retrieve the response
$response = curl_exec($ch);

// Check for cURL errors
if (curl_errno($ch)) {
    echo 'Curl error: ' . curl_error($ch);
}

// Close cURL session
curl_close($ch);

// Process $response as needed
```

cURL (Client URL) functions in PHP are commonly used for making HTTP requests to external servers, retrieving data, and interacting with APIs. The example above demonstrates a basic usage of cURL to fetch data from an API endpoint.

---

# 11.Miscellaneous functions in PHP, categorized by their purposes:

1. **Variable Handling:**
    
    * `isset($variable)`: Checks if a variable is set and is not null.
        
    * `unset($variable)`: Unsets a variable, freeing the associated memory.
        
    * `empty($variable)`: Checks if a variable is empty.
        

Example:

```php
$variable = "Hello";

if (isset($variable)) {
    echo "Variable is set and not null.";
}

unset($variable);  // Unset the variable

if (empty($variable)) {
    echo "Variable is empty or not set.";
}
```

These variable handling functions are commonly used to check the existence and status of variables, as well as to free up memory by unsetting variables.

1. **Script Termination:**
    
    * `die($message)`: Equivalent to `exit()`. Outputs a message and terminates the script.
        
    * `exit($status)`: Terminates the script.
        

Example:

```php
$error_message = "An error occurred.";

if (some_condition_is_met()) {
    die($error_message);
}

// Continue script execution if no error
echo "Script continues...";
```

These script termination functions are used to halt the execution of a PHP script, either with or without a specific message or status. They are often used in error handling scenarios or to stop the script under certain conditions.

---