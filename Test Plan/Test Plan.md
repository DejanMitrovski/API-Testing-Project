API Test Plan – Restful Booker

Project Name: Restful Booker API Testing
Application Under Test (AUT): Restful Booker API Documentation
Base URL: https://restful-booker.herokuapp.com
Version: 1.0
Prepared by: Dejan Mitrovski
Date: June 2026

1. Introduction

1.1 Purpose

The purpose of this test plan is to verify the functionality, reliability, and basic security of the Restful Booker API. The API provides CRUD (Create, Read, Update, Delete) operations for hotel booking management and includes an authentication mechanism.

This project is intended as a personal QA portfolio project to demonstrate practical knowledge of:

API testing with Postman.
HTTP methods and status codes.
Positive and negative testing.
Test case design.
Response validation.

1.2 Scope
In Scope
The following endpoints will be tested:

Endpoint	Method	Description
/ping	GET	API health check
/auth	POST	Generate authentication token
/booking	GET	Retrieve booking IDs
/booking	POST	Create a new booking
/booking/{id}	GET	Retrieve booking details
/booking/{id}	PUT	Update an existing booking
/booking/{id}	PATCH	Partially update a booking
/booking/{id}	DELETE	Delete a booking

Testing will include:

-Functional testing.
-Positive and negative scenarios.
-Request/response validation.
-HTTP status code validation.
-Authentication and authorization checks.
-Boundary and invalid input validation.
-Basic performance observations (response time).

Out of Scope

-UI testing (API only).
-Database validation.
-Load or stress testing.
-Penetration/security testing beyond basic authorization checks.
-Automation with external frameworks (e.g., RestAssured, Playwright).

2. Objectives

The main objectives of testing are:

-Verify that all documented endpoints behave as expected.
-Ensure API responses return correct HTTP status codes.
-Validate response body structure and required fields.
-Verify authentication requirements for protected endpoints.
-Confirm CRUD operations function correctly.
-Identify defects and inconsistencies in API behavior.
-Demonstrate practical API testing skills using Postman.

3. Test Strategy
3.1 Test Levels
Testing will be conducted at the API integration level using HTTP requests and response validation.

3.2 Test Types

Test Type	                            Description

Functional Testing - Verify endpoint functionality according to documentation.
Positive Testing - Validate expected behavior using valid inputs.
Negative Testing - Send invalid or missing data and verify error handling.
Authentication Testing - Verify access control using valid and invalid credentials.
Data Validation - Verify response body fields, data types, and values.
Boundary Testing - Test edge cases such as empty fields and invalid IDs.
Regression Testing - Re-run tests after changes to ensure existing functionality remains stable.

4. Test Environment

Component	Details
API URL: https://restful-booker.herokuapp.com
Tool: Postman
Version Control: GitHub
Reporting: Postman Collection Runner, Markdown Bug Reports
Operating System: Windows 10
Network: Internet connection

Postman Environment Variables

Variable	Description

baseUrl - API base URL
token - Authentication token
bookingId - Dynamically stored booking ID

5. Entry and Exit Criteria

Entry Criteria
API is available and reachable.
API documentation is accessible.
Postman environment is configured.
Required authentication credentials are available.

Exit Criteria
All planned test cases have been executed.
Critical and high-severity defects have been documented.
Test execution results are recorded.
Test summary report has been completed.

6. Test Deliverables

The following artifacts will be produced:

- Test Plan (TestPlan.md)
- Postman Collection (RestfulBooker.postman_collection.json)
- Postman Environment (QA_Environment.json)‎
- Test Cases (TestCases.xlsx or TestCases.md)
- Collection Runner execution report/screenshot
- GitHub repository containing all project files‫‍

7. Features to be Tested

7.1 Health Check (GET /ping)

-Verify API availability.
-Validate response status code 
-Measure response time.

7.2 Authentication (POST /auth)

-Generate token with valid credentials.
-Verify invalid credentials are rejected.
-Validate token field exists in response.

7.3 Booking Retrieval (GET /booking)

-Retrieve all booking IDs.
-Filter bookings by first name and last name.
-Filter bookings by check-in/check-out dates.
-Verify behavior with invalid query parameters.

7.4 Get Booking by ID (GET /booking/{id})

-Retrieve existing booking.
-Request non-existing booking ID.
-Request invalid booking ID format.

7.5 Create Booking (POST /booking)

-Create booking with valid payload.
-Create booking with missing required fields.
-Create booking with invalid data types.
-Validate returned booking ID and response body.

7.6 Update Booking (PUT /booking/{id})

-Update existing booking with valid token.
-Attempt update without authentication.
-Attempt update using invalid booking ID.
-Validate updated data persists.
7.7 Partial Update (PATCH /booking/{id})

-Update a subset of booking fields.
-Verify unchanged fields remain intact.
-Validate authorization requirements.

7.8 Delete Booking (DELETE /booking/{id})

-Delete booking with valid authorization.
-Attempt deletion without token.
-Attempt deletion of non-existing booking.

8. Risks and Assumptions

Risks
The API resets its data approximately every 10 minutes, which may affect test repeatability.
Public API availability may occasionally be unstable.
Existing test data may change during execution.

Assumptions
API documentation accurately reflects expected behavior.
Default credentials (admin/password123) remain valid for authentication.
The test environment remains accessible throughout testing.


10. Success Criteria

The API testing project will be considered successfully completed when:

All planned endpoints have been tested.
At least 20–30 test cases have been executed.
Postman assertions validate status codes and response content.
Authentication and CRUD workflows are covered.
All artifacts are uploaded to a public GitHub repository for portfolio purposes.

Tools and Technologies Used
API Testing Tool: Postman
Version Control: GitHub
Documentation: Markdown / Microsoft Excel
Test Reporting: Postman Collection Runner
API Type: REST API
Data Format: JSON
