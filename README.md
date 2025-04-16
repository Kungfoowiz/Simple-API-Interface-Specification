# Devaluation API Version 1

#### Description
Calculates a Devalued value based on the specified Operation Name and Quantity Factor.

#### Endpoint
GET /Devaluation

#### Authentication
Required: Authorization: Bearer <token>

#### Query Parameters
| Name             | Type    | Required | Description  |
|------------------|---------|----------|--------------|
| OperationName    | string  | Yes      | The Operation Name to specify the type of calculation. Possible values: Simple, Advanced, Recalculate. |
| QuantityFactor   | number  | Yes      | A numeric value used in the Devaluation Calculation. |

#### Responses
| Status Code                 | Description            |
|-----------------------------|------------------------|
| `200 OK`                    | Devaluation Calculation successful. |
| `400 Bad Request`           | Invalid request parameters. |
| `500 Internal Server Error` | API Service error. |

#### Example Request and Response: 200 OK
GET /Devaluation?OperationName=Simple&QuantityFactor=10
{
"message": "Successfully calculated the Devaluation.",
"devaluation": "100"
}

#### Example Request and Response: 400 Bad Request
GET /Devaluation?OperationName=&QuantityFactor=-1  
{
"error": "Bad Request",
"message": "Missing or invalid parameters: OperationName or QuantityFactor."
}

#### Example Request and Response: 500 Internal Server Error
Even if the request is valid, this shows when the API Service failed.  
You can find the error details in the log file using the Error ID.  

GET /Devaluation?OperationName=simple&QuantityFactor=10  
{
"error": "API Service Error",
"message": "Error ID: 8e6d57e2-4e8d-47c7-bf02-36f06da7c93b"
}
