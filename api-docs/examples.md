## Example 1: Fetch Dropdowns

**Request**

GET https://loan-app-mock.free.beeceptor.com/dropdowns/filters

**Response (200 OK)**

```json

{
    "loanStatus": [
        "Approved",
        "Rejected"
    ],
    "applicationYear": [
        2023,
        2024,
        2025
    ]
}
```
## Example 2: Search Loan Application by Year (default value)

POST https://loan-app-mock.free.beeceptor.com/applications/search  

**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
[
    {
        "applicationId": "APPID2025XYZ001",
        "customerName": "John Doe",
        "loanType": "Home Loan",
        "status": "Approved",
        "amount": 500000,
        "submittedBy": "AgentA",
        "submissionDate": "2025-06-15",
        "branchCode": "BR001"
    },
    {
        "applicationId": "APPID2025XYZ002",
        "customerName": "Jane Smith",
        "loanType": "Car Loan",
        "status": "Rejected",
        "amount": 250000,
        "submittedBy": "AgentB",
        "submissionDate": "2025-05-20",
        "branchCode": "BR002"
    }
]
```

## Example 3: Search Loan Application by Invalid Acknowledgement Number

### 3.1: special characters
**Request**

```json
{
  "acknowledgmentNumber": "%&$**%%^$()!:'><",
  "referenceNumber": "",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Acknowledgment Number"
}
```
### 3.2: small case & upper case alphabets only
**Request**

```json
{
  "acknowledgmentNumber": "asdthYTIJHFDSEQ",
  "referenceNumber": "",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Acknowledgment Number"
}
```

### 3.3: numeric values only
**Request**

```json
{
  "acknowledgmentNumber": "456738292892019",
  "referenceNumber": "",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
{
  "error": "Invalid Acknowledgment Number"
}
```

### 3.4: value more than 15 character
**Request**

```json
{
  "acknowledgmentNumber": "4567382928ACK3489999XYZAAWQE92019",
  "referenceNumber": "",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Acknowledgment Number"
}
```
### 3.5: value less than 15 character

**Request**

```json
{
  "acknowledgmentNumber": "ACK3489999X",
  "referenceNumber": "",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
{
  "error": "Invalid Acknowledgment Number"
}
```

## Example 4: Search Loan Application by Invalid Reference Number

### 4.1: special characters
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "%&$**%%^$()!:'><",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Reference Number"
}
```
### 4.2: small case & upper case alphabets only
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "asdthYTIJHFDSEQ",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Reference Number"
}
```

### 4.3: numeric values only
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "456738292892019",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
{
  "error": "Invalid Reference Number"
}
```

### 4.4: value more than 15 character
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "4567382928ACK3489999XYZAAWQE92019",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Reference Number"
}
```
### 4.5: value less than 15 character

**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "ACK3489999X",
  "applicationId": "",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
{
  "error": "Invalid Reference Number"
}
```

## Example 5: Search Loan Application by Invalid Application ID

### 5.1: special characters
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "",
  "applicationId": "%&$**%%^$()!:'><",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Application ID"
}
```
### 5.2: small case & upper case alphabets only
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "",
  "applicationId": "asdthYTIJHFDSEQ",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Application ID"
}
```

### 5.3: numeric values only
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "",
  "applicationId": "456738292892019",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
{
  "error": "Invalid Application ID"
}
```

### 5.4: value more than 15 character
**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "",
  "applicationId": "4567382928ACK3489999XYZAAWQE92019",
  "loanStatus": "",
  "applicationYear": 2025
}
```
**Response**

```json
{
  "error": "Invalid Application ID"
}
```
### 5.5: value less than 15 character

**Request**

```json
{
  "acknowledgmentNumber": "",
  "referenceNumber": "",
  "applicationId": "ACK3489999X",
  "loanStatus": "",
  "applicationYear": 2025
}
```

**Response**

```json
{
  "error": "Invalid Application ID"
}
```

