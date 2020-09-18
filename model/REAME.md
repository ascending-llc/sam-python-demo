## URL

The Post Order Api is`https://n80igrmu92.execute-api.us-east-1.amazonaws.com/Prod/v1/sourceSystems/123/orders/123`

The Post Orders Api is`https://n80igrmu92.execute-api.us-east-1.amazonaws.com/Prod/v1/sourceSystems/123/orders`

## Payload example

Post Order payload is `payload-Order.yaml`
Post Orders payload is `payload-Orders.yaml`

## Test Command line (Postman Recommended)

```bash
curl -vX POST https://n80igrmu92.execute-api.us-east-1.amazonaws.com/Prod/v1/sourceSystems/123/orders/123 -d @payload-Order.json --header "Content-Type: application/json"
```