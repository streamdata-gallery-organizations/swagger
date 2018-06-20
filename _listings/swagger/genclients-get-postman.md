{
  "info": {
    "name": "Swagger Generator Gets languages supported by the client generator",
    "_postman_id": "8a4bbfc1-2898-4827-9f27-c686448dce8c",
    "description": "Gets languages supported by the client generator.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Generate",
      "item": [
        {
          "id": "6de5ad62-1638-46ee-9b82-577433f9ac7c",
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
              "id": "08fdded1-a0e8-4a8b-98a4-03bc7ba380cd"
            }
          ]
        }
      ]
    }
  ]
}