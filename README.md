# Devaluation API Version 1

#### Description
Calculates a Devaluation based on the specified Operation Name and Quantity Factor.

---

## Example Request and Response: 200 OK
GET /Devaluation?OperationName=Simple&QuantityFactor=10

{  
"message": "Devaluation Successful",  
"result": "100"  
}

## Example Request and Response: 400 Bad Request
GET /Devaluation?OperationName=&QuantityFactor=-1

{  
"message": "Bad Request",  
"result": "Missing or invalid parameters."  
}

## Example Request and Response: 500 API Service Error
Even if the request is valid, this shows when the API Service failed.  
You can find the error details in the log file using the Error ID.  

GET /Devaluation?OperationName=Simple&QuantityFactor=10  
{  
"message": "API Service Error",  
"result": "8e6d57e2-4e8d-47c7-bf02-36f06da7c93b"  
}

---

#### Endpoint
GET /Devaluation

#### Authentication
Required: Authorization: Bearer <token>

#### Query Parameters
| Name             | Type    | Required | Description  |
|------------------|---------|----------|--------------|
| OperationName    | String  | Yes      | The Operation Name to specify the type of calculation. Possible values: Simple, Advanced, Recalculate. |
| QuantityFactor   | Integer | Yes      | A numeric value used in the Devaluation Calculation. |
