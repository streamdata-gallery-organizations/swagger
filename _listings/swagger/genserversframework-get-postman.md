{
  "info": {
    "name": "Swagger Generator Returns options for a server framework",
    "_postman_id": "93fdbb59-a609-44a7-95b3-1db2a35f4052",
    "description": "Returns options for a server framework.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Generate",
      "item": [
        {
          "id": "8041f526-f3dd-4c9a-9816-41ca1703f65c",
          "name": "getServerOptions",
          "request": {
            "url": {
              "protocol": "http",
              "host": "generator.swagger.io",
              "path": [
                "api",
                "gen/servers/:framework"
              ],
              "variable": [
                {
                  "id": "framework",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Returns options for a server framework."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "413fef7d-ae10-4511-bd89-d83af09c0a25"
            }
          ]
        }
      ]
    }
  ]
}