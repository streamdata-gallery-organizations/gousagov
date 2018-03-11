---
swagger: "2.0"
info:
  title: Go.USA.gov API
  description: The Go.USA.gov API can Shorten a URL. Preview the destination of a
    short URL. Get the number of clicks on a short URL. Export short URLs from an
    account.
  termsOfService: http://www.usa.gov/About/developer-resources/terms-of-service.shtml
  version: 1.0.0
host: go.usa.gov
basePath: /api/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  clicks.json:
    get:
      summary: URL Clicks
      description: Get the Number of Clicks on a Short URL
      operationId: urlClicks
      parameters:
      - in: query
        name: shortUrl
        description: ' The encoded shortened URL'
        type: string
        format: string
      responses:
        200:
          description: A successful response
          schema:
            type: array
            items:
              $ref: '#/definitions/URL'
      tags:
      - url
definitions:
  URL:
    properties:
      shortUrl:
        description: the short url
        type: string
      longUrl:
        description: the long url
        type: string
      dateCreated:
        description: the date created
        type: string
      URLtitle:
        description: the title of the url
        type: string
      URLdescription:
        description: the description of the url
        type: string
      URLkeywords:
        description: the keywords for the url
        type: string
      user_clicks:
        description: the number of clicks on url
        type: string
      notes:
        description: the notes for the url
        type: string
x-collection-name: Go.USA.Gov
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