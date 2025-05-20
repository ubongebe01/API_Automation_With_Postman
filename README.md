# API_Automation_With_Postman
This project automates key API test cases for Restful Booker using Postman.
It covers token generation, booking creation, updating, deletion, and a range of positive and negative test cases.
# Tools Used
Postman (for API automation)
Newman (optional, for CLI execution)
RESTful Booker API (Public API)
# Project Structure
├── Authentication/
│   └── POST GetToken:Success
├── Booking_Flow/
    ├── POST CreateBooking:Success
    ├── POST CreateBooking:to be deleted
    ├── POST CreateBooking:invalid_inputdata
    ├── POST CreateBooking:input_Range_Mismatch
    ├── POST CreateBooking:empty_input_data
    ├── PUT UpdateBooking:Success
    ├── PUT UpdateBooking:no auth
    └── DELETE DeleteBooking
Each request validates different combinations of:
Valid/invalid payloads
Authorization handling
Response body and status code assertions
# Test Scenarios Covered
| Endpoint          | Scenario Description                        |
| ----------------- | ------------------------------------------- |
| `POST /auth`      | Generate a valid token                      |
| `POST /booking`   | Valid booking, invalid data, missing fields |
| `PUT /booking`    | Update booking with and without token       |
| `DELETE /booking` | Delete booking with token                   |

# How to Use This Collection
Step 1: Download & Import
Download the Postman Collection JSON (or import the .postman_collection.json file).
Open Postman > File > Import.
Select the collection file or drag and drop it.
Step 2: Set Environment
Create or select an environment with the following variables:
| Variable    | Initial Value                          |
| ----------- | -------------------------------------- |
| `baseUrl`   | `https://restful-booker.herokuapp.com` |
| `token`     | *(blank; set dynamically)*             |
| `bookingId` | *(blank; set dynamically)*             |
Please note that the token and bookingId will be set automatically during test execution.

Step 3: Run with Collection Runner
Click on the collection name → “Run”.
Choose the environment.
Hit Start Run to execute all requests sequentially.
# Optional: Run via Newman CLI
Do the below:
1. Install Newman using: npm install -g newman
2. Run tests using: newman run API_Automation_Postman_Test.postman_collection.json -e environment.json
# Assertions & Validation
Each request contains test scripts to validate:
a) HTTP status codes
b) Response structure
c) Error messages for invalid inputs
d) Token presence and dynamic variable updates





