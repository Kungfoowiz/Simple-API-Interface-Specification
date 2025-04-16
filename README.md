# Devaluation API Version 1

## Description
Calculates a devalued value based on the specified operation name and quantity factor.

## Endpoint
`GET /Devaluation?OperationName=simple&QuantityFactor=10`
- **Example Request**:
GET /Devaluation?OperationName=exampleOperation&QuantityFactor=10 Authorization: Bearer <token>

## Authentication
Required: Authorization: Bearer <token>

## Query Parameters
| **Name**          | **Type**  | **Required** | **Description**                                    |
|--------------------|-----------|--------------|--------------------------------------------------|
| `OperationName`    | `string`  | Yes          | The operation name to specify the type of calculation. Possible values: `simple`, `advanced`, `recalculate`. |
| `QuantityFactor`   | `number`  | Yes          | A numeric value used in the devaluation calculation.  |

## Response
| **Status Code**         | **Description**                |
|--------------------------|-------------------------------|
| `200 OK`                | Calculation successful.        |
| `400 Bad Request`        | Invalid request parameters.    |
| `500 Internal Server Error` | A generic server error occurred. |

### Example Response: 200 OK
```json
{
"result": "Processed value for operation simple with quantity factor 10"
}


### Example Response: 200 OK
```json
{
"result": "Processed value for operation exampleOperation with quantity factor 10"
}

### Example Response: 400 Bad Request
```json
{
  "error": "Bad Request",
  "message": "Missing or invalid parameters: OperationName or QuantityFactor."
}


### Example Response: 500 Internal Server Error
```json
{
  "error": "Internal Server Error",
  "message": "An unexpected error occurred on the server."
}

