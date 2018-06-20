{
  "info": {
    "name": "Swagger Generator Returns options for a client library",
    "_postman_id": "55a91599-9779-489a-ba52-bb24643aeaf6",
    "description": "Returns options for a client library.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Generate",
      "item": [
        {
          "id": "a6445877-a8c1-470a-b79d-d3f4acccf0e1",
          "name": "clientOptions",
          "request": {
            "url": "http://generator.swagger.io/api/gen/clients",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Gets languages supported by the client generator."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "1d32d9d4-8d74-49c9-8935-e2310906f81c"
            }
          ]
        },
        {
          "id": "30af65d7-3817-47b7-97c4-d58c6b814e1a",
          "name": "getClientOptions",
          "request": {
            "url": {
              "protocol": "http",
              "host": "generator.swagger.io",
              "path": [
                "api",
                "gen/clients/:language"
              ],
              "variable": [
                {
                  "id": "language",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Returns options for a client library."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "42b26886-6432-4d86-96d7-c604b0fd6a18"
            }
          ]
        }
      ]
    }
  ]
}