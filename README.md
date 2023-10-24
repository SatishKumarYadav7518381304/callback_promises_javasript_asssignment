# callback_promises_javasript_asssignment


Ques 1    Double using callback.

Ans      
Doubling the values of an array using a callback function is a common task in JavaScript. You can create a function that takes an array and a callback, which doubles each element in the array based on the callback's logic. Here's an example:
function doubleArrayElements(arr, callback) {
  const doubledArray = arr.map(callback);
  return doubledArray;
}

// Define a callback function to double a value
function double(value) {
  return value * 2;
}

const originalArray = [1, 2, 3, 4, 5];

// Use the doubleArrayElements function with the double callback
const doubledArray = doubleArrayElements(originalArray, double);

console.log("Original Array:", originalArray);
console.log("Doubled Array:", doubledArray);





In this code:

We define a doubleArrayElements function that takes an array arr and a callback function callback.

The map method is used to apply the callback function to each element in the array, which effectively doubles each value.

We define a double callback function that takes a value and returns its double.

We create an originalArray with some values.

We call the doubleArrayElements function with the originalArray and the double callback, resulting in a new array where each element is doubled.

The output will be:

Original Array: [1, 2, 3, 4, 5]
Doubled Array: [2, 4, 6, 8, 10]

This is a simple example of how you can use a callback function to transform the elements of an array based on a specific logic. The doubleArrayElements function can be reused with different callbacks to apply various transformations to the array elements.




Ques 2   String Manipulation

Ans    String manipulation involves various operations to modify, extract, or transform strings in JavaScript. Here are some common string manipulation tasks and examples of how to perform them:

        1   Concatenation:

         You can concatenate strings using the + operator or the concat method.


       const str1 = "Hello";
       const str2 = ", World!";
       const result = str1 + str2; // Using the + operator
       // or
       const result2 = str1.concat(str2); // Using the concat method


       2 Substring Extraction:
    
      To extract a substring from a string, you can use the slice or substring methods


      const text = "This is a sample text.";
      const extracted = text.slice(5, 12); // "is a sa"
      // or
     const sub = text.substring(5, 12); // "is a sa"



     3  String Length:

         To get the length of a string, you can use the length property.

          const text = "Hello, World!";
         const length = text.length; // 13



    4   Uppercase and Lowercase:

            You can convert a string to uppercase or lowercase using the toUpperCase and toLowerCase methods.



            const text = "This Is Mixed Case";
            const upper = text.toUpperCase(); // "THIS IS MIXED CASE"
            const lower = text.toLowerCase(); // "this is mixed case"


      5  Replace Substrings:

     To replace substrings within a string, you can use the replace method.     


     const text = "Hello, World!";
     const replaced = text.replace("World", "Universe"); // "Hello, Universe!"

     6  Splitting Strings:

     You can split a string into an array of substrings using the split method


     const text = "apple,banana,cherry";
     const fruits = text.split(","); // ["apple", "banana", "cherry"]


     7  Trimming Whitespace:

    To remove leading and trailing whitespace from a string, you can use the trim method.


    const text = "   Some text with spaces   ";
    const trimmed = text.trim(); // "Some text with spaces"


    8  String Interpolation:

     You can use template literals to create strings with variables or expressions embedded.

     const name = "John";
    const message = `Hello, ${name}!`; // "Hello, John!"

    These are some of the basic string manipulation tasks in JavaScript. Depending on your specific requirements, you can combine these operations to achieve more complex transformations and manipulations of strings.



    Ques 3 Age in Days
   
    Ans    To calculate a person's age in days, you can use JavaScript to compute the difference between their birthdate and the current date. Here's a code example to do that:


           function calculateAgeInDays(birthDate) {
           const oneDay = 24 * 60 * 60 * 1000; // 24 hours * 60 minutes * 60 seconds * 1000 milliseconds
           const birthDateObj = new Date(birthDate);
          const currentDate = new Date();

          // Calculate the difference in milliseconds
         const timeDifference = currentDate - birthDateObj;

         // Convert the time difference to days
         const days = Math.floor(timeDifference / oneDay);

         return days;
                }

          // Example usage: 
        const birthDate = new Date("1990-10-15"); // Replace with the person's birthdate
      const ageInDays = calculateAgeInDays(birthDate);

      console.log(`Your age in days is approximately ${ageInDays} days.`);



 In this code:

We define a function calculateAgeInDays that takes the person's birthdate as a Date object.

We calculate the difference in milliseconds between the birthdate and the current date using the subtraction operator.

We convert the time difference to days by dividing by the number of milliseconds in a day (24 hours * 60 minutes * 60 seconds * 1000 milliseconds).

The result is the person's age in days.

You can replace the birthDate with the actual birthdate you want to calculate the age for. This code will then provide the person's age in days as the output.

    


    Ques   Arrange in alphabetical order.


    Ans  To arrange an array of strings in alphabetical order in JavaScript, you can use the Array.prototype.sort() method. Here's an example:


        const fruits = ["banana", "apple", "cherry", "date", "grape"];

      // Use the sort method to arrange the array in alphabetical order
      fruits.sort();

      console.log(fruits);


      In this code, we have an array of fruits. By calling the sort() method on the array, it will be sorted in alphabetical order by default, and the result will be:

      [ 'apple', 'banana', 'cherry', 'date', 'grape' ]


    The sort() method sorts the array in place and returns the sorted array.

     If you need to sort the array in a case-insensitive manner (e.g., 'apple' and 'Apple' should be treated as equal), you can provide a custom comparison function to the sort() method:


     const fruits = ["banana", "Apple", "cherry", "Date", "grape"];

    // Sort the array in a case-insensitive alphabetical order
    fruits.sort((a, b) => a.localeCompare(b, undefined, { sensitivity: "base" }));

    console.log(fruits);


    In this case, the localeCompare function is used with the sensitivity option set to "base" to perform a case-insensitive comparison.

    The output will be:


    [ 'Apple', 'banana', 'cherry', 'Date', 'grape' ]


Ques  5  Greeting Promise.


Ans   You can create a simple Promise in JavaScript to represent a greeting. Promises are often used for asynchronous operations, but for this example, we'll use a Promise to greet someone. Here's an example of a greeting Promise:

function greetPerson(personName) {
  return new Promise((resolve, reject) => {
    if (personName) {
      const greeting = `Hello, ${personName}!`;
      resolve(greeting);
    } else {
      reject("No person name provided.");
    }
  });
}

// Usage
greetPerson("Alice")
  .then(greeting => {
    console.log(greeting); // Hello, Alice!
  })
  .catch(error => {
    console.error(error);
  });

// Example with no name provided
greetPerson()
  .then(greeting => {
    console.log(greeting);
  })
  .catch(error => {
    console.error(error); // No person name provided.
  });


In this code:

The greetPerson function returns a Promise that takes a personName as a parameter.

Inside the Promise, it checks if a personName is provided. If it is, it resolves the Promise with a greeting message. If not, it rejects the Promise with an error message.

We use the then method to handle the resolved Promise and the catch method to handle any errors.

We provide an example of greeting "Alice" and another example where no name is provided.

When you run this code, it will greet the person if a name is provided and log an error message if no name is provided. This example demonstrates the basic structure of a Promise and how to use the resolve and reject functions to control the Promise's outcome.

Ques 6  Fetch results asynchronously.

Ans    To fetch data asynchronously using JavaScript, you can use the fetch API, which allows you to make HTTP requests and handle responses. Here's an example of how to use fetch to retrieve data asynchronously:

   // Define the URL of the API or resource you want to fetch
const apiUrl = 'https://jsonplaceholder.typicode.com/posts/1';

// Use the fetch function to make an HTTP GET request
fetch(apiUrl)
  .then(response => {
    // Check if the response status code is in the 200-299 range (successful)
    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }
    // Parse the response body as JSON
    return response.json();
  })
  .then(data => {
    // Process and use the fetched data
    console.log('Fetched data:', data);
  })
  .catch(error => {
    // Handle any errors that occurred during the fetch
    console.error('Fetch error:', error);
  });

In this code:

We define the URL of the API or resource you want to fetch. In this example, we are fetching a post from the JSONPlaceholder API.

We use the fetch function to make an HTTP GET request to the specified URL.

The first then block checks if the response status code is in the 200-299 range, which indicates a successful response. If not, it throws an error.

If the response is successful, the second then block parses the response body as JSON, as many APIs return data in JSON format.

Finally, we process and use the fetched data in the second then block. In this example, we simply log the data to the console.

If there are any errors during the fetch, they are caught and handled in the catch block, where we log the error to the console.

This code fetches data asynchronously, making it suitable for use in web applications to retrieve data from APIs or other web resources. You can adapt this example to your specific use case and API endpoint


Ques 7  Multiple requests.

Ans  To make multiple asynchronous requests in JavaScript, you can use techniques like Promise chaining, async/await, or libraries like Axios. I'll provide an example using fetch and Promise chaining to make multiple requests and process the data sequentially.

Let's say you want to fetch data from multiple URLs and process each response. Here's how you can do it:

const urls = [
  'https://jsonplaceholder.typicode.com/posts/1',
  'https://jsonplaceholder.typicode.com/posts/2',
  'https://jsonplaceholder.typicode.com/posts/3',
];

function fetchData(url) {
  return fetch(url)
    .then((response) => {
      if (!response.ok) {
        throw new Error(`HTTP error! Status: ${response.status}`);
      }
      return response.json();
    })
    .then((data) => {
      return data;
    });
}

function processAndLogData(data) {
  console.log('Fetched data:', data);
}

// Fetch data from each URL and process it sequentially
urls.reduce((chain, url) => {
  return chain.then(() => {
    return fetchData(url).then(processAndLogData);
  });
}, Promise.resolve())
  .then(() => {
    console.log('All requests completed.');
  })
  .catch((error) => {
    console.error('Error:', error);
  });


In this code:

urls is an array of URLs you want to fetch data from.

The fetchData function uses fetch to retrieve data from a URL and handle the response as described in the previous example.

The processAndLogData function processes and logs the fetched data.

We use the reduce method to create a Promise chain, where each fetchData and processAndLogData operation is executed sequentially. This ensures that the requests are made and processed in order.

Finally, we add a .then to handle the completion of all requests and a .catch to handle any errors that may occur during the fetch or processing.

This approach allows you to make multiple asynchronous requests and process their data sequentially. You can adjust the urls array and the processing logic as needed for your specific use case.

Ques 8  Get Data from API and Display it on the browser console.

Ans    To get data from an API and display it in the browser console using JavaScript, you can use the fetch API to make the API request. Here's an example of how to do this:

   // Define the URL of the API you want to fetch data from
const apiUrl = 'https://jsonplaceholder.typicode.com/posts/1';

// Use the fetch function to make an HTTP GET request
fetch(apiUrl)
  .then(response => {
    // Check if the response status code is in the 200-299 range (successful)
    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }
    // Parse the response body as JSON
    return response.json();
  })
  .then(data => {
    // Display the fetched data in the browser console
    console.log('Fetched data:', data);
  })
  .catch(error => {
    // Handle any errors that occurred during the fetch
    console.error('Fetch error:', error);
  });

In this code:

Define the URL of the API you want to fetch data from. In this example, we are fetching a post from the JSONPlaceholder API.

Use the fetch function to make an HTTP GET request to the specified URL.

The first then block checks if the response status code is in the 200-299 range, indicating a successful response. If not, it throws an error.

If the response is successful, the second then block parses the response body as JSON, as many APIs return data in JSON format.

Finally, we display the fetched data in the browser console using console.log.

If there are any errors during the fetch, they are caught and handled in the catch block, where we log the error to the console.

When you run this code in a browser, it will fetch data from the specified API and display the response in the browser console. You can adjust the apiUrl to fetch data from different APIs or endpoints as needed.





Ques 9  Error Handling


Ans  
Error handling is an important aspect of JavaScript programming to ensure that your code can gracefully handle unexpected issues. JavaScript provides several mechanisms for error handling, including try...catch, throw, and Promise rejections. Here's how to use these mechanisms for error handling:

1 Try...Catch:

Use try...catch to catch and handle exceptions (runtime errors) that might occur within a specific block of code. Here's an example

try {
  // Code that might throw an error
  const result = someFunction();
} catch (error) {
  // Handle the error
  console.error("An error occurred:", error);
}

2 Throw:

You can use the throw statement to explicitly throw an error or exception. For example:

function divide(a, b) {
  if (b === 0) {
    throw new Error("Division by zero is not allowed.");
  }
  return a / b;
}

3 Promise Rejections:

When working with Promises, you can use .catch() to handle errors that occur during Promise execution:

fetch(apiUrl)
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }
    return response.json();
  })
  .then(data => {
    // Process data
  })
  .catch(error => {
    // Handle fetch or processing errors
    console.error("Error:", error);
  });

4 Error Objects:

JavaScript provides various built-in error objects, such as Error, TypeError, and SyntaxError. You can create custom error objects by extending the Error object:

class CustomError extends Error {
  constructor(message) {
    super(message);
    this.name = "CustomError";
  }
}

try {
  throw new CustomError("This is a custom error.");
} catch (error) {
  console.error(error.name + ": " + error.message);
}


5 Finally:

You can use a finally block with try...catch to specify code that should be executed regardless of whether an error occurred:

try {
  // Code that might throw an error
} catch (error) {
  // Handle the error
} finally {
  // Code that always runs
}

Error handling is essential for robust code, as it helps prevent crashes and allows you to handle errors gracefully by providing feedback or taking alternative actions when something goes wrong.





