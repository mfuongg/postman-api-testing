# Postman API Testing Practice

## 1. Introduction

This project demonstrates basic API testing using Postman and JSONPlaceholder, a free fake online REST API for practice.

## 2. Objectives

* Understand HTTP methods: GET, POST, PUT, PATCH, and DELETE.
* Send API requests and inspect JSON responses.
* Verify HTTP status codes and response data.
* Write automated tests in Postman.
* Perform negative testing.
* Document test results using screenshots.

## 3. Testing Environment

* Tool: Postman Web
* API: JSONPlaceholder
* Base URL: https://jsonplaceholder.typicode.com
* Resource: `/posts`

## 4. Test Cases

| Test ID | Method | Endpoint            | Expected Result                    |
| ------- | ------ | ------------------- | ---------------------------------- |
| TC01    | GET    | `/posts/1`          | Retrieve one post                  |
| TC02    | GET    | `/posts?userId=1`   | Retrieve posts for user 1          |
| TC03    | POST   | `/posts`            | Simulate creating a post           |
| TC04    | PUT    | `/posts/1`          | Simulate a full update             |
| TC05    | PATCH  | `/posts/1`          | Simulate a partial update          |
| TC06    | DELETE | `/posts/1`          | Simulate deleting a post           |
| TC07    | GET    | `/posts/9999`       | Verify response for a missing post |
| TC08    | GET    | `/invalid-endpoint` | Verify invalid endpoint behavior   |

## 5. Automated Testing

Postman test scripts were used to verify HTTP status codes and response data for selected requests.

## 6. Test Results

* Total test cases: 8
* Passed: [Enter the actual number]
* Failed: [Enter the actual number]

The test results were recorded based on the actual responses received in Postman.

## 7. Screenshots

The `screenshots/` folder contains screenshots of the six main API requests and the negative testing cases, including their response results.

## 8. Limitations

JSONPlaceholder is a simulated REST API. Successful POST, PUT, PATCH, or DELETE responses do not necessarily mean that changes are permanently stored in a database.

## 9. Conclusion

This practice helped me understand HTTP methods, API responses, automated assertions, and negative testing using Postman.
