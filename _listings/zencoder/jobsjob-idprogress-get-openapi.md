---
swagger: "2.0"
x-collection-name: Zencoder
x-complete: 0
info:
  title: Zencoder API Job Progress
  version: v2
  description: 'The return will contain one or more of the following keys: state,
    input, outputs, and progress.'
host: app.zencoder.com
basePath: /api/v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /jobs:
    get:
      summary: List Jobs
      description: A list of jobs can be obtained by sending an HTTP GET request.
      operationId: getJobs
      x-api-path-slug: jobs-get
      parameters:
      - in: query
        name: api_key
        description: The API Key
      responses:
        200:
          description: OK
      tags:
      - Jobs
    post:
      summary: Create a Job
      description: Encoding jobs are created by sending an HTTP POST request.
      operationId: postJobs
      x-api-path-slug: jobs-post
      parameters:
      - in: query
        name: api_key
        description: The API key
      - in: query
        name: Encoding Settings
        description: '(see: https://app'
      - in: query
        name: input
        description: A valid URL to a media file (HTTP/HTTPS, FTP/FTPS, SFTP, GCS,
          CF or S3), with or without authentication
      responses:
        200:
          description: OK
      tags:
      - Jobs
  /jobs/{job_id}:
    get:
      summary: Get Job Details
      description: Get Job Details
      operationId: getJobsJob
      x-api-path-slug: jobsjob-id-get
      parameters:
      - in: query
        name: api_key
        description: The API Key
      - in: query
        name: Get Job Details
        description: The Job id
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Job
      - Id
  /jobs/{job_id}/cancel:
    put:
      summary: Cancel a Job
      description: If you wish to cancel a job that has not yet finished processing
        you may send a request.
      operationId: putJobsJobCancel
      x-api-path-slug: jobsjob-idcancel-put
      parameters:
      - in: query
        name: api_key
        description: The API Key
      - in: query
        name: job_id
        description: The job id
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Job
      - Id
      - Cancel
  /jobs/{job_id}/finish:
    put:
      summary: Finish a LIve Job
      description: Finishes the input on a Live streaming job.
      operationId: putJobsJobFinish
      x-api-path-slug: jobsjob-idfinish-put
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Job
      - Id
      - Finish
  /jobs/{job_id}/progress:
    get:
      summary: Job Progress
      description: 'The return will contain one or more of the following keys: state,
        input, outputs, and progress.'
      operationId: getJobsJobProgress
      x-api-path-slug: jobsjob-idprogress-get
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Job
      - Id
      - Progress
  /jobs/{job_id}/resubmit:
    put:
      summary: Resubmit a Job
      description: If a job has failed processing you may request that it be attempted
        again.
      operationId: putJobsJobResubmit
      x-api-path-slug: jobsjob-idresubmit-put
      parameters:
      - in: query
        name: api_key
        description: The API Key
      - in: query
        name: job_id
        description: The job id
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Job
      - Id
      - Resubmit
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