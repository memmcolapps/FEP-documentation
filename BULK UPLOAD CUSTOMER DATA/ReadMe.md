# New MomasPay - Bulk Customer Data Upload Guide

This document provides instructions on how to bulk upload customer data into the New MomasPay system using CSV files.

## CSV File Format

The CSV file must follow this specific structure:

### Header Row

The first row of the CSV file must contain these exact headers:
```csv
accountno, meterno, tariffid, firstname, lastname, address, state, phone, email
```

### Field Descriptions and Constraints

| Header     | Description                  | Data Type | Constraints |
|------------|------------------------------|-----------|-------------|
| accountno  | Customer Account Number      | Text      | Required    |
| meterno    | Meter Number                | Text      | Required |
| tariffid   | Tariff Classification ID    | Integer   | Required    |
| firstname  | Customer First Name         | Text      | Required    |
| lastname   | Customer Last Name          | Text      | Required    |
| address    | Customer Address            | Text      | Required    |
| state      | State of Residence          | Text      | Required    |
| phone      | Phone Number                | Text      | Required    |
| email      | Email Address               | Text      | Required, Must be unique |

## Important Considerations

* **Email Uniqueness:**
  * Each email address must be unique in the system
  * Duplicate email addresses will cause upload failure

* **Account Number:**
  * Should be in the format provided by your organization
  * Special characters are allowed

* **Meter Number:**
  * Must be exactly 8 digits
  * Should be a valid meter number in the system

* **Tariff ID:**
  * Must be a valid tariff ID from the system
  * Typically ranges from 1-10 depending on customer classification

## Sample Data Format

```csv
accountno      , meterno , tariffid, firstname, lastname, address        , state, phone   , email
0192 Naf Valley, 12345678,        3, John     , Doe     , 123 Main St  , Lagos, 12345678, john.doe@email.com
```

## Data Validation

Before uploading:
1. Ensure all required fields are filled
2. Verify email addresses are unique
3. Validate tariff IDs exist in the system

CURRENTLY MAINTAINED BY MOSHOOD ALIMI
