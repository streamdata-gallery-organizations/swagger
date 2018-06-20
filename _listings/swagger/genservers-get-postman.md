{
  "info": {
    "name": "Swagger Generator Gets languages supported by the server generator",
    "_postman_id": "13942718-0e0a-49d2-8340-5878ca48be0d",
    "description": "Gets languages supported by the server generator.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Generate",
      "item": [
        {
          "id": "62e24e8e-9d85-4b55-af50-27f4311bb35b",
          "name": "serverOptions",
          "request": {
            "url": "http://generator.swagger.io/api/gen/servers",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Gets languages supported by the server generator."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "282a8be5-3555-4b78-a96d-af075d64cef4"
            }
          ]
        }
      ]
    }
  ]
}