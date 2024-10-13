# URL Shortener Microservice

This is a simple **URL Shortener Microservice** built with Node.js and Express. The service accepts a URL, validates it, and returns a shortened URL. When visiting the shortened URL, the user is redirected to the original URL.

## Project Purpose

This project is part of the [FreeCodeCamp Back End Development and APIs](https://www.freecodecamp.org/learn/back-end-development-and-apis/) curriculum.

## Features

- **Shorten a URL**: You can POST a URL to `/api/shorturl` and receive a JSON response containing the original URL and a short URL.
- **Redirect using Short URL**: Visiting the `/api/shorturl/:shorturl` endpoint will redirect you to the original URL.
- **Invalid URL Handling**: If you provide an invalid URL that does not follow the format `http://www.example.com`, the service will return an error message: `{ "error": "invalid url" }`.

## API Endpoints

- **POST /api/shorturl**

  - Description: Submits a URL to shorten.
  - Request Body: `{ "url": "<your URL>" }`
  - Response Example:

    ```json
    {
      "original_url": "https://www.example.com",
      "short_url": 1
    }
    ```

  - Invalid URL Response Example:

    ```json
    {
      "error": "invalid url"
    }
    ```

- **GET /api/shorturl/:shorturl**

  - Description: Redirects the user to the original URL using the short URL.
  - Example:
    - `/api/shorturl/1` will redirect to `https://www.example.com`.
  - If the `shorturl` does not exist, the response will be:

    ```json
    {
      "error": "No short URL found for the given input"
    }
    ```

---

## Getting Started

### Prerequisites

Ensure that the following software is installed on your machine:

- [Node.js](https://nodejs.org/) (v12.x or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)

### Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Abhishek-d-b/url-shortend-microservice
   ```

2. **Navigate to the project folder**:

   ```bash
   cd url-shortener-microservice
   ```

3. **Install the dependencies**:

   ```bash
   npm install
   ```

4. **Start the server**:

   ```bash
   npm start
   ```

5. **Test the service**: You can use tools like Postman or cURL to test the endpoints.

### Example Usage

- To shorten a URL:

  ```bash
  curl -X POST http://localhost:3000/api/shorturl -d "url=https://www.example.com"
  ```

- To redirect using a short URL:

  ```bash
  curl -X GET http://localhost:3000/api/shorturl/1
  ```
