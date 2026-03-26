# iValidate - Email Validator

iValidate is a simple web application that allows users to validate email addresses. It checks whether an email is deliverable, properly formatted, and provides additional metadata about the email address out of the box. 


Live-website link: https://tangerine-marzipan-4adde7.netlify.app/
## Features

- **Real-time Email Validation**: Check if an email address actually exists.
- **Detailed Results**: Provides information such as:
  - Format validity (e.g., missing `@` or domain)
  - Disposable email check (e.g., temporary emails)
  - MX records existence
  - SMTP check
- **Clean Interface**: A modern, easy-to-use user interface.

## How It Works

The project uses Vanilla JavaScript and the Fetch API to make requests to the [emailvalidation.io](https://emailvalidation.io/) API. 

1. The user enters an email address in the input field and clicks **Submit**.
2. An asynchronous JavaScript function intercepts the form submission, prevents the default page reload, and sends a GET request to the `emailvalidation.io` endpoint.
3. While fetching, a loading SVG is displayed.
4. The API responds with a JSON object containing the validation metrics.
5. The JavaScript code dynamically generates HTML to display only the properties from the API response that contain values.

## File Structure

- `index.html`: The main markup file containing the structure of the web page, header, input form, and the container for results.
- `css/style.css`: Contains all the styling to make the webpage look appealing.
- `js/index.js`: Contains the core logic for capturing user input, sending HTTP requests to the validation API, and rendering the results back into the HTML DOM.
- `img/`: Contains the SVG icons used in the application (like the logo and the loading spinner).

## How to Run locally

Since this project consists entirely of static files (HTML, CSS, JS), you do not need any complex server setup to run it.

1. Clone or download the repository to your local machine.
2. Navigate to the project folder.
3. Open `index.html` directly in your favorite web browser.
*(Alternatively, you can use an extension like **Live Server** in VS Code for a better development experience).*

## API Key Setup

**Note:** The application currently relies on a specific API key embedded in `js/index.js` for `emailvalidation.io`. If the API key expires or goes out of quota, the application will not be able to fetch results. 

To use your own API key:
1. Sign up at [emailvalidation.io](https://emailvalidation.io/) to get a free API key.
2. Open `js/index.js`.
3. Replace the `key` variable with your new API key:
   ```javascript
   let key = "YOUR_API_KEY_HERE"
   ```

## Technologies Used

- **HTML5**
- **CSS3**
- **JavaScript (ES6+)**: Async/Await, Fetch API, DOM Manipulation
