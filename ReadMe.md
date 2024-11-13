# Frequently Solved Problems (FSP)

This document contains a list of frequently encountered problems and their solutions.

---

## Problem Title

### Description

Brief description of the problem.

### Symptoms

- Symptom 1
- Symptom 2
- Symptom 3

### Root Cause

Explanation of what causes this problem.

### Solution

Step-by-step guide to solve the problem:

1. Step 1
2. Step 2
3. Step 3

### Prevention

Tips to prevent this problem from occurring in the future.

---

## Example: Connection Timeout Error

### Description

Users experience connection timeout errors when trying to access the application database.

### Symptoms

- Application throws a "Connection Timeout" error
- Database queries take an unusually long time to execute
- Intermittent connection drops

### Root Cause

The connection pool is exhausted due to connections not being properly closed after use.

### Solution

1. Identify and fix connection leaks:
   - Review code for unclosed database connections
   - Implement proper connection closing in finally blocks
2. Increase the connection pool size temporarily:
   - In the database configuration file, set `max_connections = 200`
3. Restart the application server
4. Monitor connection usage to ensure the problem is resolved

### Prevention

- Implement connection pooling best practices
- Use try-with-resources for automatic connection closing
- Set up alerts for connection pool usage reaching 80% capacity

## MQTT Service

### Description
This is the Event-driven service that enables real time communication to devices or clients.
This service serves two major application which are smarte and MICA mobile aaplication.

### Symptoms
Unable to start the service.

### Root Cause, 
1. Port 1883 may not be open or maybe used by other service.
2. Database connection failed.
### Solution, prevention
visit: https://github.com/memmcolapps/mqtt-service-app.git

## Node web service

### Description
This backend service is built with node, and serve as servic for momaspay applicaion. 
This service manage some section in momaspay application however some of this section depend on java endpoint (paymentwebserviceV5) to complete it process. such as when user what performa the following task
1. Initiating paystack payment (depend on java endpoint).
2. Verify paystack payment (depend on java endpoint).
3. Initiating remita payment.
4. Verify remita payment.
5. Reprint token (depend on java endpoint).
6. Sent Otp to email.
7. Sent customer token to email.

### Symptoms
1. Unable to vend on momaspay (paystack connection timeout)

### Root Cause, 
1. Node service not started
2. If node service is running, then then java service stop running or freeze
### Solution, prevention
Start node service

visit: https://github.com/memmcolapps/node_paymentwebservice_v5.git

---

## Error Generating Token

### Description

This error occurs when a request is sent to fetch a token after payment validation, but the system is unable to dispense the token.

### Symptoms

- Application throws a "Connection Timed Out" error.
- Users receive the message "Error Generating Token..."
- Inability to dispense token.

### Root Cause

The token generation service is down due to power or network failure on the destination server.

### Solution

1. Even if power is restored after a power failure, the service may not automatically start unless a system administrator logs into the server, which initiates the service.
2. Users should check with the ICT department to ensure the network is up and stable.
3. If both conditions have been met but the token is still not dispensed, restart the server.

### Prevention

- Ensure a constant power supply.
- Maintain network uptime within a 95%-99% range.
- Configure the service as a Windows service to auto-start on system startup, eliminating the need for manual login by the system administrator.

---
## Add another problem title
[Follow the same structure as above]

---
