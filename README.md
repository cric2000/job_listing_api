# Job Listing Application Backend

This is the api for a job listing application.

## Overview

+ MVC

+ API Endpoints
  + POST
  + GET
  + PUT
  + DELETE

**Sign Up**
- **Description:** Register a new user.
- **Endpoint:** `/api/signup`
- **Method:** POST
- **Request Body (JSON):**
  - `email` (required): User's email address.
  - `password` (required): User's password.
  - `firstName` (required): User's first name.
  - `lastName` (required): User's last name.
  - `role` (optional): User role (0 for regular user, 1 for admin, defaults to 0 if not specified).
 
**Sign In**
- **Description:** For log in.
- **URL:** `/api/signin`
- **Method:** POST
- **Request Body (JSON):**
  - `email` (required): User's email address.
  - `password` (required): User's password.
 
**Log Out**
- **Description:** Log out of the current session.
- **URL:** `/api/logout`
- **Method:** GET

**Get All Jobs**
- **Description:** Get a list of all available job listings.
- **URL:** `/api/jobs/show/?pageNumber=2&keyword=&cat=&location=`
- **Method:** GET
- **Query Parameters:**
  - `pageNumber` (optional): The page number for pagination.
  - `keyword` (optional): Keyword for job searching.
  - `cat` (optional): Job category filter.
  - `location` (optional): Job location filter.

**Create Job**
- **Description:** Create a new job listing.
- **URL:** `/api/job/create`
- **Method:** POST
- **Authentication Required:** Yes (User Authentication)
- **Authorization Required:** Yes (Admin Authorization)
- **Request Body (JSON):**
  - `title` (required): Title of the job.
  - `description` (required): Description of the job.
  - `salary` (required): Salary offered for the job.
  - `location` (required): Location of the job.
  - `jobType` (required): Type of the job.

### Middleware

**isAuthenticated**
- **Description:** Check if the user is authenticated.
- **Function:** `isAuthenticated`
- **Authorization Required:** Yes
- **Response:**
  - Status Code: 401 (Unauthorized) if not authenticated.

**isAdmin**
- **Description:** Check if the user is an admin.
- **Function:** `isAdmin`
- **Authorization Required:** Yes
- **Response:**
  - Status Code: 401 (Unauthorized) if the user is not an admin.

**Note:** To create a job, the user must be authenticated, and to be an admin user, the `role` in the user's profile must be set to 1.

In addition to those, various API endpoints are utilized for tasks such as creating job categories and locations, updating and deleting data, displaying the admin dashboard, presenting the user dashboard, retrieving user job history, and obtaining a list of users.

## Getting Started

Follow these steps to get the project up and running on your local machine.

### Clone the Project

```sh
git clone https://github.com/cric2000/job_listing_api
```

### Install Dependencies

Navigate to the project directory and install the required dependencies using npm:

```sh
npm install
```
### Make .env file

Create a .env file similar to .env.example in the root of your project

### Start the Application

After installing the dependencies, start the application with the following command:

```sh
npm start
```
The application can be accessed by default at http://localhost:9000 or at the port specified in the .env configuration file that you choose.
