# service

This is a simple template for echo service

### Prepare deployment bucket

```bash
aws s3 mb s3://basicappdeployment --region=eu-west-1
```

### Local development

**Invoking function locally through local API Gateway**

```bash
sam local start-api
```

If the previous command ran successfully you should now be able to hit the following local endpoint to invoke your function `http://localhost:3000/echo`

## Packaging and deployment

To build application:

```bash
sam build
```

To deploy your application for the first time, run the following in your shell:

```bash
sam deploy --guided
```
Or when there is ready configuration:

```bash
sam deploy --profile default --config-env dev --no-fail-on-empty-changeset
```

## Example endpoint query

Response will be saved into **echo** file in the same dir where command was executed

```bash
curl -LO -X POST \
  --url https://br7y9uju95.execute-api.eu-west-1.amazonaws.com/Prod/echo \
  --header 'Content-Type: application/json' \
  --data '{"woo": "hoo"}'
```