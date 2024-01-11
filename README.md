# HTTP Event

## Overview

This library, named `http-event`, simplifies the process of handling HTTP events in the browser by providing a declarative approach to bind HTML elements with HTTP requests. It leverages the native Fetch API to perform HTTP requests and includes various options for customization.

## Installation

Include the `http-event.js` file in your project:

```html
<script src="https://cdn.jsdelivr.net/gh/lullaby6/http-event/cdn.min.js" defer></script>
```

## Usage

To use the library, follow these steps:

1. **Include the Script:**
   Include the `http-event.js` script in your HTML file.

2. **Declare HTML Elements:**
   Add the `he-event` attribute to HTML elements that should trigger HTTP events. Specify the type of event using the `he-event` attribute.

   ```html
   <button he-event="click" he-url="/api/data" he-method="GET">Load Data</button>
   <form he-event="submit" he-url="/api/submit" he-method="POST">
       <!-- Form fields go here -->
   </form>
   ```

3. **Configure Attributes:**
   Customize the HTTP request by adding attributes to the HTML elements.

   - `he-url`: Specifies the URL for the HTTP request.
   - `he-method`: Specifies the HTTP method (default is GET).
   - `he-authentication`: Adds an authentication header.
   - `he-authorization`: Adds an authorization header.
   - `he-headers`: Provides additional headers in JSON format.
   - `he-headers-storage`: Retrieves headers from local storage.

   Example:

   ```html
   <button he-event="click" he-url="/api/data" he-method="GET" he-authentication="Bearer token">Load Data</button>
   ```

4. **Handle Responses:**
   Customize the handling of the HTTP response using various attributes.

   - `he-json`: Parses the response as JSON.
   - `he-log`: Logs the response data to the console.
   - `he-storage`: Stores the response data in local storage.
   - `he-run`: Executes a script after receiving the response.

   Example:

   ```html
   <div he-event="click" he-url="/api/data" he-method="GET" he-json he-log he-run="console.log('Response received!')">Load Data</div>
   ```

5. **Update UI: Specify Swap Method (`he-swap`)**

    The `he-swap` attribute defines how the response data should be swapped or inserted into the target element. Choose one of the following options:

    - `innerHTML`: Replace the inner HTML content of the target element with the response data.
    - `outerHTML`: Replace the entire outer HTML content of the target element with the response data.
    - `value`: Set the value of the target element (useful for form elements like input).
    - `innerText`: Set the inner text content of the target element with the response data.
    - `textContent`: Set the text content of the target element with the response data.
    - `afterbegin`, `beforeend`, `beforebegin`, `afterend`: Insert the response data at a specific position relative to the target element.
    - `remove`: Remove the target element.

    Choose the appropriate `he-swap` option based on the desired behavior for updating the UI with the HTTP response data.

6. **Redirect (Optional):**
   Optionally, redirect to a different URL after receiving the response.

   ```html
   <form he-event="submit" he-url="/api/submit" he-method="POST" he-redirect="/success">Submit Form</form>
   ```

## Why `http-event`?

The `http-event` library simplifies the integration of HTTP requests in the browser by providing a declarative and easy-to-use approach. It minimizes the boilerplate code needed to handle HTTP events, making it suitable for projects where simplicity and efficiency are crucial.