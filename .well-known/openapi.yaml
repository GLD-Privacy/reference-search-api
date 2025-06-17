openapi: 3.1.0
info:
  title: Reference Search API
  version: 1.0.0
  description: |
    This API provides a reference search function for GPT Actions,
    limited to trusted sources such as openai.com, cookbook.openai.com,
    docs.stripe.com, react.dev, and shopify.dev.
servers:
  - url: https://gld-privacy.github.io/reference-search-api
paths:
  /search:
    get:
      operationId: searchReferenceMaterials
      summary: Search technical references
      parameters:
        - name: query
          in: query
          required: true
          schema:
            type: string
      responses:
        '200':
          description: OK
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SearchResponse'
components:
  schemas:
    SearchResult:
      type: object
      properties:
        title:
          type: string
        url:
          type: string
          format: uri
        snippet:
          type: string
      required: [title, url]
    SearchResponse:
      type: object
      properties:
        results:
          type: array
          items:
            $ref: '#/components/schemas/SearchResult'
      required: [results]
