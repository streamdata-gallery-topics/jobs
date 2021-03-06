swagger: "2.0"
x-collection-name: AWS Device Farm
x-complete: 1
info:
  title: AWS Device Farm API
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=GetJob:
    get:
      summary: Get Job
      description: Gets information about a job.
      operationId: getJob
      x-api-path-slug: actiongetjob-get
      parameters:
      - in: query
        name: arn
        description: The jobs ARN
        type: string
      responses:
        200:
          description: OK
      tags:
      - Jobs
  /?Action=ListJobs:
    get:
      summary: List Jobs
      description: Gets information about jobs.
      operationId: listJobs
      x-api-path-slug: actionlistjobs-get
      parameters:
      - in: query
        name: arn
        description: The jobs ARNs
        type: string
      - in: query
        name: nextToken
        description: An identifier that was returned from the previous call to this
          operation, which can be used to return the next set of items in the list
        type: string
      responses:
        200:
          description: OK
      tags:
      - Jobs