# Devaluation API Version 1

#### Description
Calculates a devalued value based on the specified operation name and quantity factor.

#### Endpoint
GET /Devaluation

#### Authentication
Required: Authorization: Bearer <token>

#### Query Parameters
| **Name**          | **Type**  | **Required** | **Description**                                    |
|--------------------|-----------|--------------|--------------------------------------------------|
| `OperationName`    | `string`  | Yes          | The operation name to specify the type of calculation. Possible values: `simple`, `advanced`, `recalculate`. |
| `QuantityFactor`   | `number`  | Yes          | A numeric value used in the devaluation calculation.  |

#### Response
| **Status Code**         | **Description**                |
|--------------------------|-------------------------------|
| `200 OK`                | Calculation successful.        |
| `400 Bad Request`        | Invalid request parameters.    |
| `500 Internal Server Error` | A generic server error occurred. |

#### Example Request and Response: 200 OK
GET /Devaluation?OperationName=simple&QuantityFactor=10

```json
{
"result": "Processed value for operation simple with quantity factor 10"
}
```

#### Example Request and Response: 400 Bad Request
GET /Devaluation?OperationName=&QuantityFactor=-1

```json
{
  "error": "Bad Request",
  "message": "Missing or invalid parameters: OperationName or QuantityFactor."
}
```

#### Example Request and Response: 500 Internal Server Error
Even if the request is valid, this shows when the API Service failed.
GET /Devaluation?OperationName=simple&QuantityFactor=10
```json
{
  "error": "Internal Server Error",
  "message": "An unexpected error occurred on the server."
}
```
