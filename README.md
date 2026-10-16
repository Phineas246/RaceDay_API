# POE_RaceDay_API

## 1. Project Overview

POE_RaceDay_API is a Web API project that I developed using C# and ASP.NET Core. The main purpose of this project is to provide a backend system for handling race day information and managing different processes related to race day activities.

The API uses controllers to receive requests, process information, and return responses to users or other applications. I also included JWT (JSON Web Token) authentication to help protect certain endpoints and make sure that only authenticated users can access restricted parts of the system.

This project also focuses on making the reliability of the application through unit testing and using GitHub Actions to automate the build and testing process.

## 2. Technologies Used

The following technologies and tools are used in this project:

- **C#:** The main programming language used to develop the API.
- **ASP.NET Core Web API:** Used to build the backend and handle HTTP requests.
- **.NET:** Provides the framework needed to build and run the application.
- **JWT Authentication:** Helps secure endpoints by checking whether users have valid authentication tokens.
- **RESTful API:** Used to structure how the application handles requests and responses.
- **Unit Testing:** Helps check that different parts of the application work as expected.
- **GitHub Actions:** Used to automate make and testing the project whenever changes are made.

## 3. Project Features

The API is designed to handle different tasks related to race day management.

Some of the main features include:

- Handling HTTP requests using API controllers.
- Managing and processing race day-related information.
- Checking incoming requests to make sure the information provided is valid.
- Using JWT authentication to protect endpoints that require users to be authenticated.
- Returning appropriate HTTP responses when requests are successful or when errors occur.
- Using unit tests to check that the controllers behave correctly.
- Using GitHub Actions to automatically build and test the project.

The exact functionality of the API depends on what has been implemented in the controllers.

## 4. Requirements

Before running the project, make sure you have the following installed on your computer:

- A compatible version of the .NET SDK.
- Visual Studio or Visual Studio Code.
- Git for cloning and managing the repository.
- A GitHub account if you want to upload the project or use GitHub Actions.

These tools will allow you to open, build, run, and test the project.

## 5. How to Set Up and Run the Project

Follow the steps below to get the project running on your computer.

### Step 1: Clone the Repository

First, open a terminal or command prompt and clone the project from GitHub.

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Replace the placeholder with the actual URL of your GitHub repository.

Once the repository has been cloned, navigate to the project folder:

```bash
cd POE_RaceDay_API
```

### Step 2: Restore Dependencies

Before running the application, restore the packages that the project needs.

Run:

```bash
dotnet restore
```

This command downloads and restores any required NuGet packages.

### Step 3: Build the Project

After restoring the dependencies, build the project to check whether everything compiles correctly.

```bash
dotnet build
```

If the build is successful, the project is ready to run.

If there are errors, check the messages displayed in the terminal to see what needs to be fixed.

### Step 4: Run the API

To start the API, run:

```bash
dotnet run
```

Once the application starts, the terminal will display the local address where the API is running.

You can use this address to send requests to the API and test its functionality.

## 6. JWT Authentication

One of the security features used in this project is JWT authentication.

JWT authentication is used to make sure that users have permission to access protected endpoints.

When a user successfully authenticates, the system can provide a token that is included in future requests.

To access a protected endpoint:

1. Obtain a valid JWT token through the authentication functionality provided by the API.
2. Copy the generated token.
3. Open your API testing tool.
4. Add the token to the Authorization header.
5. Send the request to the protected endpoint.

The Authorization header should look like this:

```http
Authorization: Bearer YOUR_JWT_TOKEN
```

If the token is missing, invalid, or expired, the API may reject the request.

It is also important to keep sensitive information, such as JWT secret keys, passwords, and database connection details, out of the GitHub repository.

## 7. Testing the API

After running the application, the next step is to test whether the API works correctly.

Tools such as Swagger UI or Postman can be used to send requests to the API, depending on what has been configured in the project.

When testing the API, it is important to check different situations instead of only testing successful requests.

For example, testing should include:

- Sending valid requests and checking the responses.
- Sending requests with missing or incorrect information.
- Checking that the API returns the correct HTTP status codes.
- Testing endpoints that require authentication.
- Checking what happens when an invalid JWT token is used.
- Making sure the API handles errors correctly.

The available endpoints can be found by looking at the controllers in the project.

Testing these different scenarios helps identify problems and makes the API more reliable.

## 8. Unit Testing

Unit testing is another important part of this project.

The purpose of unit testing is to check whether individual parts of the application work correctly without having to test the entire system at once.

For this project, the unit tests should focus mainly on the four API controllers and the relevant authentication behaviour.

Some of the areas that should be tested include:

- Whether controllers return the expected results when valid information is provided.
- Whether invalid requests are handled correctly.
- Whether the correct HTTP status codes are returned.
- Whether errors are handled properly.
- Whether authentication-related behaviour works as expected.

To run the unit tests, open a terminal in the solution directory and enter:

```bash
dotnet test
```

This command runs the tests included in the solution.

If the tests pass, it means that the tested functionality is behaving as expected.

If any tests fail, the results can help identify which parts of the code need attention.

The test project must be included in the solution, and the required testing packages must be installed.

## 9. GitHub Actions (CI/CD)

I also use GitHub Actions as part of the project's Continuous Integration and Continuous Delivery (CI/CD) process.

GitHub Actions helps automate tasks that would otherwise need to be done manually.

For example, instead of having to build and test the project every time changes are made, a GitHub Actions workflow can automatically perform these steps.

The workflow file should be stored in the following folder:

```text
.github/workflows/
```

The workflow can be configured to run whenever code is pushed to GitHub or when a pull request is created.

### How the Workflow Works

A typical workflow follows these steps:

1. **Checkout the repository:** GitHub Actions downloads the latest version of the project code.
2. **Set up .NET:** The workflow installs the .NET SDK version required by the project.
3. **Restore dependencies:** The required NuGet packages are restored.
4. **Build the project:** The application is compiled to check for errors.
5. **Run unit tests:** The automated tests are executed to check whether the tested functionality works correctly.
6. **Display the results:** GitHub Actions shows whether the workflow completed successfully or failed.

This process makes it easier to identify errors whenever changes are made to the project.

It also helps make sure that new changes do not break functionality that was previously working.

The workflow needs to use the correct .NET version and reference the correct solution or test project.

## 10. Project Structure

The project follows a typical ASP.NET Core Web API structure.

An example of how the files and folders may be organised is shown below:

```text
POE_RaceDay_API/
│
├── Controllers/
│
├── Properties/
│
├── Program.cs
│
├── appsettings.json
│
├── POE_RaceDay_API.csproj
│
├── Tests/
│
├── .github/
│   └── workflows/
│       └── dotnet.yml
│
└── README.md
```

### Explanation of the Main Files and Folders

**Controllers**

This folder contains the API controllers. These controllers handle incoming HTTP requests and return responses.

**Program.cs**

This file contains the main application setup and configuration. It is where services and middleware are configured.

**appsettings.json**

This file stores application settings and configuration values.

**POE_RaceDay_API.csproj**

This is the project file. It contains information about the project, including the target framework and package dependencies.

**Tests**

This folder represents where the unit tests may be stored. The actual tests may also be kept in a separate test project.

**.github/workflows**

This folder contains the GitHub Actions workflow files used to automate building and testing.

**README.md**

This file provides information about the project and explains how to set it up, run it, and test it.

The actual folder structure may be slightly different depending on how the project has been organised.

## 11. Troubleshooting

Sometimes problems can occur when setting up or running the project. Below are some common issues and ways to resolve them.

### The Project Does Not Build

If the project fails to build, first check whether the correct .NET SDK is installed.

You can also try restoring the dependencies again:

```bash
dotnet restore
```

After that, run:

```bash
dotnet build
```

If the problem continues, check the error messages in the terminal to identify what is causing the issue.

### Unit Tests Are Not Running

If the unit tests do not run, check that the test project exists and is included in the solution.

Also make sure that all the required testing packages have been installed.

You can try running:

```bash
dotnet test
```

If a test fails, read the test results to understand what went wrong.

### JWT Authentication Is Not Working

If authentication fails, there are a few things to check.

First, make sure the JWT configuration is correct.

Next, check whether the token being used is valid and has not expired.

Also confirm that the request contains the correct Authorization header:

```http
Authorization: Bearer YOUR_JWT_TOKEN
```

Finally, check whether the endpoint is configured to use the expected authentication scheme.

### GitHub Actions Workflow Fails

If a GitHub Actions workflow fails, open the repository on GitHub and navigate to the **Actions** tab.

Select the failed workflow run and review the logs.

The logs will show which step failed, such as restoring dependencies, building the project, or running the tests.

Once the problem has been identified, make the necessary changes and run the workflow again.

## 12. Conclusion

Developing POE_RaceDay_API has helped me gain a better understanding of how backend applications work using C# and ASP.NET Core Web API.

Through this project, I have been able to work with API controllers, HTTP requests and responses, JWT authentication, and unit testing.

I have also gained experience with GitHub Actions and how automated workflows can be used to build and test an application whenever changes are made.

One of the main things I have learned is that developing an API is not only about making endpoints work. It is also important to think about security, testing, error handling, and maintaining the project as it grows.

There is still room to improve the project by adding more tests, improving security, and expanding the functionality of the API.

Overall, this project has given me practical experience in backend development and helped me understand how different technologies can work together to create a more reliable application.
