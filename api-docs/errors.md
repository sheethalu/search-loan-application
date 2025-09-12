Errors
Errors are returned using standard HTTP error code syntax. Depending on the status code, the response body may be in JSON or plaintext.

Search API uses conventional HTTP response codes to indicate the success or failure of an API request along with clear error messages. In general: Codes in the 2xx range indicate success. Codes in the 4xx range indicate an error that failed given the information provided (e.g., a required parameter was omitted).

HTTP Status Code Summary

### 200 OK (Success)

200	OK	Everything worked as expected.

```json
{
        "applicationId": "APPID2025XYZ001",
        "customerName": "John Doe",
        "loanType": "Home Loan",
        "status": "Approved",
        "amount": 500000,
        "submittedBy": "AgentA",
        "submissionDate": "2025-06-15",
        "branchCode": "BR001"
    }

```

### 400 Bad Request  

400	Bad Request	The request was unacceptable, often due to missing a required parameter.
Invalid input fields.

```json
{
  "error": "Invalid Acknowledgment Number"
}

{
  "error": "Invalid Reference Number"
}

{
  "error": "Invalid Application ID"
}

{
  "error": "Application Year is required"
}
```

### 402	Request Failed  

The parameters were valid but the request failed.

```json
{
    "error": "Something went wrong, please try again after sometime"
}
```

### 404	Not Found  

The requested resource doesn’t exist.

```json
{
  "error": "No applications found"
}
```