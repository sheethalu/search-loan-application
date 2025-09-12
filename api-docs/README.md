# Overview & Getting Started

## Purpose
This API lets a loan officer search existing loan applications using simple filters (acknowledgment number, reference number, application ID, loan status, year).

**Base URL:** `https://loan-app-mock.free.beeceptor.com`

## What you need
- A tool to make HTTP requests (Postman).
- For this mock, **no authentication** is required.

## Authentication
This mock API does **not** require auth.

> **Note:**  
> In a real system you would typically include:  
> - `Authorization: Bearer <token>` header for protected endpoints.  
> - Token obtained via OAuth2 client credentials or an SSO flow.  

## Filters (Business Rules)
- **Acknowledgment Number**: 1–15 alphanumeric (case-insensitive). Anything else → *Invalid Acknowledgment Number*.  
- **Reference Number**: 1–15 alphanumeric. Anything else → *Invalid Reference Number*.  
- **Application Id**: 1–15 alphanumeric. Anything else → *Invalid Application ID*.  
- **Loan Status**: one of `Approved`, `Rejected`.  
- **Application Year**: **(Required)** Allowed: `2023`, `2024`, `2025`. Default UI value: `2025`.  

## Quick Start

### 1. Fetch dropdowns for UI population:

**Request**

GET https://loan-app-mock.free.beeceptor.com/dropdowns/filters

**Response (200 OK)**

```json
{
  "loanStatus": ["Approved", "Rejected"],
  "applicationYear": ["2023", "2024", "2025"]
}

```
### 2. Search applications (year required): 

**Request**  

POST https://loan-app-mock.free.beeceptor.com/applications/search  
Content-Type: application/json

```json

{
  "applicationYear": "2025"
}

```

**Response**

```json
[
  {
    "applicationId": "APP123",
    "customerName": "Alice Smith",
    "loanType": "Personal Loan",
    "status": "Rejected",
    "amount": 50000,
    "submittedBy": "Agent02",
    "submissionDate": "2025-03-01",
    "branchCode": "BR456"
  }
]

```

**UI Expectations**

Year is auto-selected to current year (2025).

Three text inputs (Acknowledgment Number, Reference Number, Application Id).

Two dropdowns (Loan Status, Application Year).

Search results table fields:

Application ID, Customer Name, Loan Type, Status, Amount, Submitted By, Submission Date, Branch Code.





