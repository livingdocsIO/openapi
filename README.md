# OpenAPI Spec
OpenAPI (Swagger) spec for Livingdocs Public API

This file makes it easy to test and share our API enpoints.

## Supported environments
- service (edit.livingdocs.io)
- localhost

## How to use it (for now)
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
Keep the same structure as our documentation [docs](https://docs.livingdocs.io/reference-docs/public-api/)
Many API endpoints are still missing. Please mark the category as completed when all its endpoints are registered in the spec.
- Project             ✅
- Composition API     ✅
- Publications (WIP)
- Search              ✅
- Document Lists      ✅
- Document Categories ✅
- Media Library
- Imports
- Sitemaps
- Menus
- Routing
- Add Delivery Status ✅
- Health              ✅


## TODOs and future ideas
- add all the api endpoints from our docs
- share the OpenAPI spec file on edit.livingdocs/api/openapi.json
- embedd the Swagger UI in our docs
- support to extend downstream with downstream declaration
- generate the spec by the server
