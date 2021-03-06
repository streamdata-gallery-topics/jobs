swagger: "2.0"
x-collection-name: Auth0
x-complete: 1
info:
  title: Auth0 Users API
  version: v1
host: login.auth0.com
basePath: /users
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /jobs/users-imports:
    post:
      summary: Post Jobs Users Imports
      description: Post jobs users imports.
      operationId: postJobsUsersImports
      x-api-path-slug: jobsusersimports-post
      parameters:
      - in: form
        name: connection_name
        description: The name of the connection to which users will be added
      - in: form
        name: users
        description: A file containing the users to import
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Immports
  /jobs/{job_id}:
    get:
      summary: Get Jobs Job
      description: Get jobs job.
      operationId: getJobsJob
      x-api-path-slug: jobsjob-id-get
      parameters:
      - in: path
        name: job_id
        description: The id of the job
      responses:
        200:
          description: OK
      tags:
      - Jobs
  /api/v2/jobs/users-imports:
    post:
      summary: Jobs Users Imports
      description: jobs users imports.
      operationId: post_users-imports
      x-api-path-slug: apiv2jobsusersimports-post
      parameters:
      - in: form
        name: connection_name
        description: The name of the connection to which users will be added
      - in: form
        name: users
        description: A file containing the users to import
      responses:
        200:
          description: OK
      tags:
      - Jobs
      - Users
      - Imports
  /api/v2/jobs/{job_id}:
    get:
      summary: Jobs Job
      description: jobs job.
      operationId: get_jobs_by_job_id
      x-api-path-slug: apiv2jobsjob-id-get
      parameters:
      - in: path
        name: job_id
        description: The id of the job
      responses:
        200:
          description: OK
      tags:
      - Jobs