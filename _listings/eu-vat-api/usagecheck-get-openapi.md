---
swagger: "2.0"
x-collection-name: EU VAT API
x-complete: 0
info:
  title: EU VAT API Check api requests remaining on current subscription plan
  description: Check api requests remaining on current subscription plan.
  version: "1"
host: vatapi.com
basePath: /v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /country-code-check:
    get:
      summary: Retrieve a countries VAT rates by its 2 digit country code
      description: Retrieve a countries vat rates by its 2 digit country code.
      operationId: country_code_check
      x-api-path-slug: countrycodecheck-get
      parameters:
      - in: query
        name: code
        description: The 2 digit country code
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - Countries
      - VAT
      - Rates
      - By
      - Its
      - "2"
      - Digit
      - Country
      - Code
  /currency-conversion:
    get:
      summary: Convert a currency
      description: Convert a currency.
      operationId: currency_conversion
      x-api-path-slug: currencyconversion-get
      parameters:
      - in: query
        name: amount
        description: Optional, an amount you are wanting to convert
      - in: query
        name: currency_from
        description: The currency code you are converting from
      - in: query
        name: currency_to
        description: The currency code you are converting to
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Convert
      - Currency
  /invoice:
    post:
      summary: Create a VAT invoice
      description: Create a vat invoice.
      operationId: create_invoice
      x-api-path-slug: invoice-post
      parameters:
      - in: body
        name: body
        description: Enter invoice data as JSON
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - VAT
      - Invoice
  /invoice/{id}:
    delete:
      summary: Delete an invoice
      description: Delete an invoice.
      operationId: invoice_delete
      x-api-path-slug: invoiceid-delete
      parameters:
      - in: path
        name: id
        description: Enter an invoice id
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Invoice
    get:
      summary: Retrieve an invoice
      description: Retrieve an invoice.
      operationId: get_invoice
      x-api-path-slug: invoiceid-get
      parameters:
      - in: path
        name: id
        description: Enter the invoice id
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - Invoice
    put:
      summary: Update an existing invoice
      description: Update an existing invoice.
      operationId: invoice_update
      x-api-path-slug: invoiceid-put
      parameters:
      - in: body
        name: body
        description: Enter invoice data as JSON
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Enter an invoice id
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Existing
      - Invoice
  /ip-check:
    get:
      summary: Retrieve a countries VAT rates from an IP address
      description: Retrieve a countries vat rates from an ip address.
      operationId: ip_check
      x-api-path-slug: ipcheck-get
      parameters:
      - in: query
        name: address
        description: The IP address to search against
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - Countries
      - VAT
      - Rates
      - From
      - IP
      - Address
  /usage-check:
    get:
      summary: Check api requests remaining on current subscription plan
      description: Check api requests remaining on current subscription plan.
      operationId: api_usage
      x-api-path-slug: usagecheck-get
      parameters:
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Check
      - Api
      - Requests
      - Remaining
      - "On"
      - Current
      - Subscription
      - Plan
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