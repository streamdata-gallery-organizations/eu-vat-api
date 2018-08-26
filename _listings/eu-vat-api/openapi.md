---
swagger: "2.0"
x-collection-name: EU VAT API
x-complete: 1
info:
  title: VAT API
  description: a-developer-friendly-api-to-help-your-business-achieve-vat-compliance
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
  /vat-number-check:
    get:
      summary: Validate a VAT number
      description: Validate a vat number.
      operationId: vat_number_validate
      x-api-path-slug: vatnumbercheck-get
      parameters:
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      - in: query
        name: vatid
        description: The VAT number to validate
      responses:
        200:
          description: OK
      tags:
      - Validate
      - VAT
      - Number
  /vat-price:
    get:
      summary: Convert a price to or from VAT price.
      description: Convert a price to or from vat price..
      operationId: convert_price
      x-api-path-slug: vatprice-get
      parameters:
      - in: query
        name: code
        description: The 2 digit country code
      - in: query
        name: country_rate
        description: The VAT rate to get the price for
      - in: query
        name: price
        description: The price you want converting
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      - in: query
        name: type
        description: Optional, if the price is including VAT set the type to incl
      responses:
        200:
          description: OK
      tags:
      - Convert
      - Price
      - To
      - From
      - VAT
      - Price
  /vat-rates:
    get:
      summary: Retrieve all current EU VAT rates
      description: Retrieve all current eu vat rates.
      operationId: vat_rates
      x-api-path-slug: vatrates-get
      parameters:
      - in: header
        name: Response-Type
        description: The default response type is application/json if you would like
          to receive an XML response then set this to XML
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - ""
      - Current
      - EU
      - VAT
      - Rates
---