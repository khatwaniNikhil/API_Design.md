# API Rapid Design Tool
https://microapis.io/mock

```
{
  "openapi": "3.0.3",
  "info": {
    "title": "Cache API",
    "description": "API that allows you to CRUD to cache",
    "version": "1.0.0"
  },
  "paths": {
    "/cache/{cached_key}": {
      "parameters": [
        {
          "in": "path",
          "name": "cached_key",
          "required": true,
          "schema": {
            "type": "string"
          },
          "example": "blog-id"
        }
      ],
      "get": {
        "summary": "Lookup object from cache",
        "responses": {
          "200": {
            "description": "successfull lookup",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CachedObject"
                }
              }
            }
          }
        }
      },
      "post": {
        "summary": "Add entry to cache",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CachedObject"
              }
            }
          }
        },
        "responses": {
          "201": {
            "description": "A JSON representation of the created task",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/CachedObject"
                }
              }
            }
          }
        }
      }
    }
  },
  "components": {
    "schemas": {
      "CachedObject": {
        "type": "object",
        "required": [
         "key", 
	 "value"
        ],
        "additionalProperties": false,
        "properties": {
          "created": {
            "type": "string"
          },
	  "key" :{
            "type": "object"
          },
          "value": {
            "type": "object"
          }
        }
      }
    }
  }
}
```
