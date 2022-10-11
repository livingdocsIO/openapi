# OpenAPI Spec
OpenAPI (Swagger) spec for Livingdocs Public API

This file makes it easy to test and share our API enpoints.

## Supported environments
- service (edit.livingdocs.io)
- localhost

## How to use it
The OpenAPI spec is hosted by Github pages at: 

https://livingdocsio.github.io/openapi/livingdocs-openapi.json 

This can be imported in Insomnia or Postman to have a full suite of API enpoints to test.

TODO add insomnia screenshot

Alternatively the same can be done with online tools. You just need to paste the OpenAPI spec url in one of the following tools.

[Swagger UI](https://petstore.swagger.io/)

[Swagger Editor](https://editor.swagger.io/)

[RapidDocWeb](https://rapidocweb.com/examples/example1.html)


### Some other tools

[OpenAPI Tools](https://openapi.tools/) list of useful tools related to OpenAPI

[ApiTree](https://www.apitree.com/) hosted API documentation based on OpenAPI

[OpenDocumenter](https://ouropencode.github.io/OpenDocumenter/):
for creating a documentation from OpenAPI spec

## How to develop
Import the livingdocs-openapi.json file into insomnia as a design document, here you can test the APIs and add new endpoints.
For authenticated requests you need an API token from your Livingdocs project.

Alternatively you can do everything in VS Code using the [OpenAPI (Swagger) Extension](https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi).

### Example endpoint
```yaml
  /channels/{channelHandle}:
      get:
        security:
        - bearerAuth: [public-api:read]
        parameters:
        - name: channelHandle
          in: path
          description: Optional channelHandle. Will return first channel of a project if none is passed.
          required: true
          schema:
            type: string
            example: ""
        tags:
          - Project
        summary: details and configuration of this project.
        operationId: getChannel
        responses:
          "200":
           description: ok
```
## How to contribute
Keep the same structure as our documentation [docs](https://docs.livingdocs.io/reference-docs/public-api/).
Many API endpoints are still missing. Please mark the category as completed when all its endpoints are registered in the spec.
- Project             ✅
- Composition API     ✅
- Publications        ✅    
- Search              ✅
- Document Lists      ✅
- Document Categories ✅
- Media Library       ✅
- Imports             ✅
- Sitemaps            ✅
- Menus               ✅
- Routing             ✅
- Add Delivery Status ✅
- Health              ✅


## TODOs and future ideas
- add all the api endpoints from our docs ✅
- share the OpenAPI spec file on edit.livingdocs/api/openapi.json
- embedd the Swagger UI in our docs
- support to extend downstream with downstream declaration
- generate the spec by the server
