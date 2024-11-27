# Web Application using Servlets

## Overview
This project demonstrates a simple web application that utilizes Java Servlets to handle HTTP requests, perform database operations, and implement redirections. The application features user login validation with both Oracle and MySQL databases.

## Project Components
1. **DemoServlet**: Demonstrates servlet lifecycle methods (`init()`, `service()`, `destroy()`) with request counting.
2. **ErrServlet**: Displays an error message for invalid users.
3. **LoginServlet**: Validates user credentials with an Oracle database and displays validation results.
4. **MySqlServlet**: Validates user credentials with a MySQL database and displays data from `emp101` table.
5. **SendRedirect**: Handles login validation and redirects users to success or error pages based on credentials.
6. **WelServlet**: Displays a welcome message after successful login.
7. **HTML Forms**: Provides an HTML form for users to input login credentials.

## Technologies Used
- **Java Servlet API**: Handles HTTP requests and responses.
- **JDBC**: Database connectivity with Oracle and MySQL.
- **HTML**: Form for collecting user input.

## How It Works
1. The user visits `login.html`, where they enter their name and password.
2. The form sends a request to `LoginServlet`.
3. The servlet checks the credentials against the Oracle (or MySQL) database.
4. If valid, the user is redirected to `WelServlet`; if invalid, they are redirected to `ErrServlet`.
5. The `SendRedirect` servlet manages the redirection based on user validation.

## Database Interaction
- **Oracle Database**: `LoginServlet` connects to an Oracle database to validate user credentials.
- **MySQL Database**: `MySqlServlet` connects to a MySQL database and queries the `emp101` table for credentials.

## How to Run the Project
1. Set up a Java servlet container (e.g., Apache Tomcat).
2. Ensure that Oracle or MySQL is installed and configured with a table `emp101` that has columns for `name` and `pass`.
3. Deploy the servlets into the servlet container.
4. Access `login.html` via a browser and input your login credentials.

## Security Considerations
- **SQL Injection**: The current implementation uses direct user input in SQL queries, which is vulnerable to SQL injection. It is recommended to use prepared statements.
- **Password Handling**: Storing plain-text passwords is insecure. Use hashed passwords for better security.

## Improvements
- **Connection Pooling**: Use connection pooling for better performance instead of opening new database connections for every request.
- **Error Handling**: Customize error handling and show user-friendly error pages.

## License
MIT License
