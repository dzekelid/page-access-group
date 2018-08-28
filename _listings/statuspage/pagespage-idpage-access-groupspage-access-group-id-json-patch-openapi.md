---
swagger: "2.0"
x-collection-name: StatusPage
x-complete: 0
info:
  title: StatusPage.io Change information for a group
  version: 1.0.0
  description: Change information for a group
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /pages/[page_id]/components/[component_id].json:
    patch:
      summary: Update a component
      description: Update a component
      operationId: update-a-component
      x-api-path-slug: pagespage-idcomponentscomponent-id-json-patch
      parameters:
      - in: query
        name: component[description]
        description: The description of the component
        type: string
      - in: query
        name: component[name]
        description: The name of the component
        type: string
      - in: query
        name: component[status]
        description: The status, one of operational|degraded_performance|partial_outage|major_outage
        type: string
      responses:
        200:
          description: OK
      tags:
      - Page Access Group
  /pages/[page_id]/page_access_groups.json:
    get:
      summary: Retrieve a list of groups
      description: Retrieve a list of groups
      operationId: retrieve-a-list-of-groups
      x-api-path-slug: pagespage-idpage-access-groups-json-get
      responses:
        200:
          description: OK
      tags:
      - Page Access Group
    post:
      summary: Create a group that will define what and who can view elements of your
        status page
      description: Create a group that will define what and who can view elements
        of your status page
      operationId: create-a-group-that-will-define-what-and-who-can-view-elements-of-your-status-page
      x-api-path-slug: pagespage-idpage-access-groups-json-post
      parameters:
      - in: query
        name: page_access_group[component_ids][]
        description: Array of component ids that the created group will be able to
          view
        type: string
      - in: query
        name: page_access_group[external_identifier]
        description: A unique string that can be used to associate this group with
          an external group (optional)
        type: string
      - in: query
        name: page_access_group[metric_ids][]
        description: Array of metric ids that the created group will be able to view
        type: string
      - in: query
        name: page_access_group[name]
        description: The name the group (required)
        type: string
      - in: query
        name: page_access_group[page_access_user_ids][]
        description: Array of Page Access User ids that the created group contain
        type: string
      responses:
        200:
          description: OK
      tags:
      - Page Access Group
  /pages/[page_id]/page_access_groups/[page_access_group_id].json:
    patch:
      summary: Change information for a group
      description: Change information for a group
      operationId: change-information-for-a-group
      x-api-path-slug: pagespage-idpage-access-groupspage-access-group-id-json-patch
      parameters:
      - in: query
        name: page_access_group[component_ids][]
        description: Array of component ids that the created group will be able to
          view
        type: string
      - in: query
        name: page_access_group[external_identifier]
        description: A unique string that can be used to associate this group with
          an external group (optional)
        type: string
      - in: query
        name: page_access_group[metric_ids][]
        description: Array of metric ids that the created group will be able to view
        type: string
      - in: query
        name: page_access_group[name]
        description: The name the group (required)
        type: string
      - in: query
        name: page_access_group[page_access_user_ids][]
        description: Array of Page Access User ids that the created group contain
        type: string
      responses:
        200:
          description: OK
      tags:
      - Page Access Group
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