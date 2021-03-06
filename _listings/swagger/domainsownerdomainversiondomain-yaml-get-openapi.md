---
swagger: "2.0"
x-collection-name: Swagger
x-complete: 0
info:
  title: Swagger Hub Registry Retrieves the definition for the specified domain and
    version in YAML format
  description: Retrieves the definition for the specified domain and version in yaml
    format.
  contact:
    name: SwaggerHub
    url: http://swaggerhub.com
    email: info@swaggerhub.com
  version: 1.0.45
host: api.swaggerhub.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /apis:
    get:
      summary: Retrieves a list of currently defined APIs in APIs.json format.
      description: Retrieves a list of currently defined apis in apis.json format..
      operationId: searchApis
      x-api-path-slug: apis-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: query
        name: page
        description: page to return
      - in: query
        name: query
        description: free text query to match
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      - in: query
        name: state
        description: matches against published state of the spec* UNPUBLISHED - spec
          is a draft, a work in progress* PUBLISHED - spec is a stable version ready
          for consuming from client applications* ANY - either PUBLISHED or UNPUBLISHED
      - in: query
        name: tag
        description: matches against tags associated with an API
      responses:
        200:
          description: OK
      tags:
      - APIs
  /apis/{owner}:
    get:
      summary: Retrieves an APIs.json listing of all APIs defined for this owner
      description: Retrieves an apis.json listing of all apis defined for this owner.
      operationId: getOwnerApis
      x-api-path-slug: apisowner-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: page
        description: page to return
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
  /apis/{owner}/{api}:
    delete:
      summary: Deletes the specified API
      description: Deletes the specified api.
      operationId: deleteApi
      x-api-path-slug: apisownerapi-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
    get:
      summary: Retrieves an APIs.json listing for all API versions for this owner
        and API
      description: Retrieves an apis.json listing for all api versions for this owner
        and api.
      operationId: getApiVersions
      x-api-path-slug: apisownerapi-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
    post:
      summary: Saves the provided Swagger definition
      description: Saves the provided swagger definition.
      operationId: saveDefinition
      x-api-path-slug: apisownerapi-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: definition
        description: the Swagger definition of this API
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: version
        description: api version
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
  /apis/{owner}/{api}/.collaboration:
    delete:
      summary: Deletes API's collaboration
      description: Deletes api's collaboration.
      operationId: deleteCollaboration
      x-api-path-slug: apisownerapi-collaboration-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Collaboration
    get:
      summary: Gets API's collaboration
      description: Gets api's collaboration.
      operationId: getCollaboration
      x-api-path-slug: apisownerapi-collaboration-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: expandTeams
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Collaboration
    put:
      summary: Updates API's collaboration
      description: Updates api's collaboration.
      operationId: updateCollaboration
      x-api-path-slug: apisownerapi-collaboration-put
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Collaboration
  /apis/{owner}/{api}/{version}:
    delete:
      summary: Deletes a particular version of the specified API
      description: Deletes a particular version of the specified api.
      operationId: deleteApiVersion
      x-api-path-slug: apisownerapiversion-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
    get:
      summary: Retrieves the Swagger definition for the specified API and version
      description: Retrieves the swagger definition for the specified api and version.
      operationId: getDefinition
      x-api-path-slug: apisownerapiversion-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
  /apis/{owner}/{api}/{version}/swagger.json:
    get:
      summary: Retrieves the Swagger definition for the specified API and version
        in JSON format
      description: Retrieves the swagger definition for the specified api and version
        in json format.
      operationId: getJsonDefinition
      x-api-path-slug: apisownerapiversionswagger-json-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - Swagger
      - Json
  /apis/{owner}/{api}/{version}/swagger.yaml:
    get:
      summary: Retrieves the Swagger definition for the specified API and version
        in YAML format
      description: Retrieves the swagger definition for the specified api and version
        in yaml format.
      operationId: getYamlDefinition
      x-api-path-slug: apisownerapiversionswagger-yaml-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - Swagger
      - Yaml
  /domains:
    get:
      summary: Retrieves a list of currently defined domains in APIs.json format
      description: Retrieves a list of currently defined domains in apis.json format.
      operationId: searchDomains
      x-api-path-slug: domains-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: query
        name: page
        description: page to return
      - in: query
        name: query
        description: free text query to match
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      - in: query
        name: state
        description: matches against published state of the spec* UNPUBLISHED - spec
          is a draft, a work in progress* PUBLISHED - spec is a stable version ready
          for consuming from client applications* ANY - either PUBLISHED or UNPUBLISHED
      - in: query
        name: tag
        description: matches against tags associated with a domain
      responses:
        200:
          description: OK
      tags:
      - Domains
  /domains/{owner}:
    get:
      summary: Retrieves an APIs.json listing of all domains defined for this owner
      description: Retrieves an apis.json listing of all domains defined for this
        owner.
      operationId: getOwnerDomains
      x-api-path-slug: domainsowner-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: page
        description: page to return
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
  /domains/{owner}/{domain}:
    delete:
      summary: Deletes the specified domain
      description: Deletes the specified domain.
      operationId: deleteDomain
      x-api-path-slug: domainsownerdomain-delete
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
    get:
      summary: Retrieves an APIs.json listing for all domain versions for this owner
        and domain
      description: Retrieves an apis.json listing for all domain versions for this
        owner and domain.
      operationId: getDomainVersions
      x-api-path-slug: domainsownerdomain-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
    post:
      summary: Saves the provided Swagger definition of a domain
      description: Saves the provided swagger definition of a domain.
      operationId: saveDomainDefinition
      x-api-path-slug: domainsownerdomain-post
      parameters:
      - in: body
        name: definition
        description: the Swagger definition of this Domain
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: version
        description: domain version
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
  /domains/{owner}/{domain}/{version}:
    delete:
      summary: Deletes a particular version of the specified domain
      description: Deletes a particular version of the specified domain.
      operationId: deleteDomainVersion
      x-api-path-slug: domainsownerdomainversion-delete
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
    get:
      summary: Retrieves the Swagger definition for the specified domain and version
      description: Retrieves the swagger definition for the specified domain and version.
      operationId: getDomainDefinition
      x-api-path-slug: domainsownerdomainversion-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
  /domains/{owner}/{domain}/{version}/domain.json:
    get:
      summary: Retrieves the definition for the specified domain and version in JSON
        format
      description: Retrieves the definition for the specified domain and version in
        json format.
      operationId: getDomainJsonDefinition
      x-api-path-slug: domainsownerdomainversiondomain-json-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - Domain
      - Json
  /domains/{owner}/{domain}/{version}/domain.yaml:
    get:
      summary: Retrieves the definition for the specified domain and version in YAML
        format
      description: Retrieves the definition for the specified domain and version in
        yaml format.
      operationId: getDomainYamlDefinition
      x-api-path-slug: domainsownerdomainversiondomain-yaml-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - Domain
      - Yaml
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---