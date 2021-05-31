# <p align="center" width="100%"> <img src="./logo.png" width="250" height="250"> </p> 
# <p align="center" width="100%"> Apacta OIH Connector </p>

## Description

A generated OIH connector for the Apacta API (version 0.0.1).

Generated from: https://api.apis.guru/v2/specs/apacta.com/0.0.1/swagger.json<br/>
Generated at: 2021-05-31T11:11:07+02:00

## API Description

API for a tool to craftsmen used to register working hours, material usage and quality assurance.    <br/>
# Endpoint<br/>
The endpoint `https://app.apacta.com/api/v1` should be used to communicate with the API. API access is only allowed with SSL encrypted connection (https).<br/>
# Authentication<br/>
URL query authentication with an API key is used, so appending `?api_key={api_key}` to the URL where `{api_key}` is found within Apacta settings is used for authentication<br/>
# Pagination<br/>
If the endpoint returns a `pagination` object it means the endpoint supports pagination - currently it's only possible to change pages with `?page={page_number}` but implementing custom page sizes are on the road map.<br/>
<br/>
<br/>
# Search/filter<br/>
Is experimental but implemented in some cases - see the individual endpoints' docs for further explanation.<br/>
# Ordering<br/>
Is currently experimental, but on some endpoints it's implemented on URL querys so eg. to order Invoices by `invoice_number` appending `?sort=Invoices.invoice_number&direction=desc` would sort the list descending by the value of `invoice_number`.<br/>
# Associations<br/>
Is currently implemented on an experimental basis where you can append eg. `?include=Contacts,Projects`  to the `/api/v1/invoices/` endpoint to embed `Contact` and `Project` objects directly.<br/>
# Project Files<br/>
Currently project files can be retrieved from two endpoints. `/projects/{project_id}/files` handles files uploaded from wall posts or forms. `/projects/{project_id}/project_files` allows uploading and showing files, not belonging to specific form or wall post.<br/>
# Errors/Exceptions<br/>
## 422 (Validation)<br/>
Write something about how the `errors` object contains keys with the properties that failes validation like:<br/>
``<br/>
  {<br/>
      "success": false,<br/>
      "data": {<br/>
          "code": 422,<br/>
          "url": "/api/v1/contacts?api_key=5523be3b-30ef-425d-8203-04df7caaa93a",<br/>
          "message": "A validation error occurred",<br/>
          "errorCount": 1,<br/>
          "errors": {<br/>
              "contact_types": [ ## Property name that failed validation<br/>
                  "Contacts must have at least one contact type" ## Message with further explanation<br/>
              ]<br/>
          }<br/>
      }<br/>
  }<br/>
``<br/>

## Code examples<br/>
Running examples of how to retrieve the 5 most recent forms registered and embed the details of the User that made the form, and eventual products contained in the form<br/>
### Swift<br/>
<br/>
  <br/>
<br/>

### Java<br/>
#### OkHttp<br/>
``<br/>
  OkHttpClient client = new OkHttpClient();<br/>
  <br/>
  Request request = new Request.Builder()<br/>
    .url("https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5")<br/>
    .get()<br/>
    .addHeader("x-auth-token", "{INSERT_YOUR_TOKEN}")<br/>
    .addHeader("accept", "application/json")<br/>
    .build();<br/>
  <br/>
  Response response = client.newCall(request).execute();<br/>
``<br/>

#### Unirest<br/>
  <br/>
  HttpResponse<String> response = Unirest.get("https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5")<br/>
    .header("x-auth-token", "{INSERT_YOUR_TOKEN}")<br/>
    .header("accept", "application/json")<br/>
    .asString();<br/>
  <br/>

### Javascript<br/>
#### Native<br/>
``<br/>
  var data = null;<br/>
  <br/>
  var xhr = new XMLHttpRequest();<br/>
  xhr.withCredentials = true;<br/>
  <br/>
  xhr.addEventListener("readystatechange", function () {<br/>
    if (this.readyState === 4) {<br/>
      console.log(this.responseText);<br/>
    }<br/>
  });<br/>
  <br/>
  xhr.open("GET", "https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5");<br/>
  xhr.setRequestHeader("x-auth-token", "{INSERT_YOUR_TOKEN}");<br/>
  xhr.setRequestHeader("accept", "application/json");<br/>
  <br/>
  xhr.send(data);<br/>
  <br/>

#### jQuery<br/>
 `` <br/>
  var settings = {<br/>
    "async": true,<br/>
    "crossDomain": true,<br/>
    "url": "https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5",<br/>
    "method": "GET",<br/>
    "headers": {<br/>
      "x-auth-token": "{INSERT_YOUR_TOKEN}",<br/>
      "accept": "application/json",<br/>
    }<br/>
  }<br/>
  <br/>
  $.ajax(settings).done(function (response) {<br/>
    console.log(response);<br/>
  });<br/>
``<br/>

#### NodeJS (Request)<br/>
``<br/>
  var request = require("request");<br/>
<br/>
  var options = { method: 'GET',<br/>
    url: 'https://app.apacta.com/api/v1/forms',<br/>
    qs: <br/>
     { extended: 'true',<br/>
       sort: 'Forms.created',<br/>
       direction: 'DESC',<br/>
       include: 'Products,CreatedBy',<br/>
       limit: '5' },<br/>
    headers: <br/>
     { accept: 'application/json',<br/>
       'x-auth-token': '{INSERT_YOUR_TOKEN}' } };<br/>
  <br/>
  request(options, function (error, response, body) {<br/>
    if (error) throw new Error(error);<br/>
  <br/>
    console.log(body);<br/>
  });<br/>
<br/>
  <br/>

### Python 3<br/>
  <br/>
  import http.client<br/>
  <br/>
  conn = http.client.HTTPSConnection("app.apacta.com")<br/>
  <br/>
  payload = ""<br/>
  <br/>
  headers = {<br/>
      'x-auth-token': "{INSERT_YOUR_TOKEN}",<br/>
      'accept': "application/json",<br/>
      }<br/>
  <br/>
  conn.request("GET", "/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5", payload, headers)<br/>
  <br/>
  res = conn.getresponse()<br/>
  data = res.read()<br/>
  <br/>
  print(data.decode("utf-8"))<br/>
``<br/>

### C#<br/>
#### RestSharp<br/>
``<br/>
  var client = new RestClient("https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5");<br/>
  var request = new RestRequest(Method.GET);<br/>
  request.AddHeader("accept", "application/json");<br/>
  request.AddHeader("x-auth-token", "{INSERT_YOUR_TOKEN}");<br/>
  IRestResponse response = client.Execute(request);    <br/>
``<br/>

### Ruby<br/>
``<br/>
  require 'uri'<br/>
  require 'net/http'<br/>
  <br/>
  url = URI("https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5")<br/>
  <br/>
  http = Net::HTTP.new(url.host, url.port)<br/>
  http.use_ssl = true<br/>
  http.verify_mode = OpenSSL::SSL::VERIFY_NONE<br/>
  <br/>
  request = Net::HTTP::Get.new(url)<br/>
  request["x-auth-token"] = '{INSERT_YOUR_TOKEN}'<br/>
  request["accept"] = 'application/json'<br/>
  <br/>
  response = http.request(request)<br/>
  puts response.read_body<br/>
``<br/>

### PHP (HttpRequest)<br/>
``<br/>
  <?php<br/>
<br/>
  $request = new HttpRequest();<br/>
  $request->setUrl('https://app.apacta.com/api/v1/forms');<br/>
  $request->setMethod(HTTP_METH_GET);<br/>
  <br/>
  $request->setQueryData(array(<br/>
    'extended' => 'true',<br/>
    'sort' => 'Forms.created',<br/>
    'direction' => 'DESC',<br/>
    'include' => 'Products,CreatedBy',<br/>
    'limit' => '5'<br/>
  ));<br/>
  <br/>
  $request->setHeaders(array(<br/>
    'accept' => 'application/json',<br/>
    'x-auth-token' => '{INSERT_YOUR_TOKEN}'<br/>
  ));<br/>
  <br/>
  try {<br/>
    $response = $request->send();<br/>
  <br/>
    echo $response->getBody();<br/>
  } catch (HttpException $ex) {<br/>
    echo $ex;<br/>
  }<br/>
``<br/>

### Shell (cURL)<br/>
``<br/>
<br/>
  $ curl --request GET --url 'https://app.apacta.com/api/v1/forms?extended=true&sort=Forms.created&direction=DESC&include=Products%2CCreatedBy&limit=5' --header 'accept: application/json' --header 'x-auth-token: {INSERT_YOUR_TOKEN}'<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
  <br/>
``<br/>

## Authorization

Supported authorization schemes:
- API Key

- API Key
 - Uses the user's API token found from within the control panel in "settings" -> "additional settings"

## Actions

### Get details about one city

*Tags:* `Cities`

#### Input Parameters
* `city_id` - _required_

### Create clocking record for authenticated user

*Tags:* `ClockingRecords`

### Checkout active clocking record for authenticated user

*Tags:* `ClockingRecords`

### Delete a clocking record

*Tags:* `ClockingRecords`

#### Input Parameters
* `clocking_record_id` - _required_

### Details of 1 clocking_record

*Tags:* `ClockingRecords`

#### Input Parameters
* `clocking_record_id` - _required_

### Edit a clocking record

*Tags:* `ClockingRecords`

#### Input Parameters
* `clocking_record_id` - _required_

### Details of 1 company

*Tags:* `Companies`

#### Input Parameters
* `company_id` - _required_

### Show details of 1 integration feature setting

*Tags:* `Companies`

#### Input Parameters
* `company_id` - _required_
* `integration_feature_setting_id` - _required_

### Get details about one contact type

*Tags:* `ContactTypes`

#### Input Parameters
* `contact_type_id` - _required_

### Add a new contact

*Tags:* `Contacts`

### Delete a contact

*Tags:* `Contacts`

#### Input Parameters
* `contact_id` - _required_

### Details of 1 contact

*Tags:* `Contacts`

#### Input Parameters
* `contact_id` - _required_

### Edit a contact

*Tags:* `Contacts`

#### Input Parameters
* `contact_id` - _required_

### Get details about one currency

*Tags:* `Currencies`

#### Input Parameters
* `currency_id` - _required_

### Add file to expense

*Tags:* `ExpenseFiles`

### Delete file

*Tags:* `ExpenseFiles`

#### Input Parameters
* `expense_file_id` - _required_

### Show file

*Tags:* `ExpenseFiles`

#### Input Parameters
* `expense_file_id` - _required_

### Edit file

*Tags:* `ExpenseFiles`

#### Input Parameters
* `expense_file_id` - _required_

### Add line to expense

*Tags:* `ExpenseLines`

### Delete expense line

*Tags:* `ExpenseLines`

#### Input Parameters
* `expense_line_id` - _required_

### Show expense line

*Tags:* `ExpenseLines`

#### Input Parameters
* `expense_line_id` - _required_

### Edit expense line

*Tags:* `ExpenseLines`

#### Input Parameters
* `expense_line_id` - _required_

### Add line to expense

*Tags:* `Expenses`

### Delete expense

*Tags:* `Expenses`

#### Input Parameters
* `expense_id` - _required_

### Show expense

*Tags:* `Expenses`

#### Input Parameters
* `expense_id` - _required_

### Edit expense

*Tags:* `Expenses`

#### Input Parameters
* `expense_id` - _required_

### Show OIOUBL file

*Tags:* `Expense OIOUBL files`

#### Input Parameters
* `expense_id` - _required_
* `file_id` - _required_

### Get details about single `FormField`

*Tags:* `FormFieldTypes`

#### Input Parameters
* `form_field_type_id` - _required_

### Add a new field to a `Form`

*Tags:* `FormFields`

### Get details about single `FormField`

*Tags:* `FormFields`

#### Input Parameters
* `form_field_id` - _required_

### View one form template

*Tags:* `FormTemplates`

#### Input Parameters
* `form_template_id` - _required_

### Add new form
> Used to add a form into the system<br/>

*Tags:* `Forms`

### Delete a form
> You can only delete the forms that you've submitted yourself<br/>

*Tags:* `Forms`

#### Input Parameters
* `form_id` - _required_

### View form

*Tags:* `Forms`

#### Input Parameters
* `form_id` - _required_

### Edit a form

*Tags:* `Forms`

#### Input Parameters
* `form_id` - _required_

### Add invoice

*Tags:* `InvoiceLines`

### Delete invoice line

*Tags:* `InvoiceLines`

#### Input Parameters
* `invoice_line_id` - _required_

### View invoice line

*Tags:* `InvoiceLines`

#### Input Parameters
* `invoice_line_id` - _required_

### Edit invoice line

*Tags:* `InvoiceLines`

#### Input Parameters
* `invoice_line_id` - _required_

### Add invoice

*Tags:* `Invoices`

### Delete invoice

*Tags:* `Invoices`

#### Input Parameters
* `invoice_id` - _required_

### View invoice

*Tags:* `Invoices`

#### Input Parameters
* `invoice_id` - _required_

### Edit invoice

*Tags:* `Invoices`

#### Input Parameters
* `invoice_id` - _required_

### View mass message

*Tags:* `MassMessagesUsers`

#### Input Parameters
* `mass_messages_user_id` - _required_

### Edit mass message

*Tags:* `MassMessagesUsers`

#### Input Parameters
* `mass_messages_user_id` - _required_

### Delete material

*Tags:* `Materials`

#### Input Parameters
* `material_id` - _required_

### View material

*Tags:* `Materials`

#### Input Parameters
* `material_id` - _required_

### Edit material

*Tags:* `Materials`

#### Input Parameters
* `material_id` - _required_

### Add material rental

*Tags:* `MaterialRentals`

#### Input Parameters
* `material_id` - _required_

### Checkout material rental

*Tags:* `MaterialRentals`

#### Input Parameters
* `material_id` - _required_

### Delete material rental
> Delete rental for material<br/>

*Tags:* `MaterialRentals`

#### Input Parameters
* `material_id` - _required_
* `material_rental_id` - _required_

### Add material

*Tags:* `Materials`

#### Input Parameters
* `material_id` - _required_
* `material_rental_id` - _required_

### Edit material rental

*Tags:* `MaterialRentals`

#### Input Parameters
* `material_id` - _required_
* `material_rental_id` - _required_

### Details of 1 payment term type

*Tags:* `PaymentTermTypes`

#### Input Parameters
* `payment_term_type_id` - _required_

### Details of 1 payment term

*Tags:* `PaymentTerms`

#### Input Parameters
* `payment_term_id` - _required_

### Add new product

*Tags:* `Products`

### Delete a product

*Tags:* `Products`

#### Input Parameters
* `product_id` - _required_

### View single product

*Tags:* `Products`

#### Input Parameters
* `product_id` - _required_

### Edit a product

*Tags:* `Products`

#### Input Parameters
* `product_id` - _required_

### Get details about one contact type

*Tags:* `ProjectStatuses`

#### Input Parameters
* `project_status_id` - _required_

### Add a project

*Tags:* `Projects`

### Delete a project

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_

### View specific project

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_

### Edit a project

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_

### Delete file
> Delete file uploaded to a project from wall post or form<br/>

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_
* `file_id` - _required_

### Edit file
> Edit file uploaded to a project from wall post or form<br/>

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_
* `file_id` - _required_

### Add project file to projects

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_

### Delete project file

*Tags:* `Projects`

#### Input Parameters
* `project_file_id` - _required_
* `project_id` - _required_

### Edit project file

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_
* `project_file_id` - _required_

### Add user to project

*Tags:* `Projects`

#### Input Parameters
* `project_id` - _required_

### Delete user from project

*Tags:* `Projects`

#### Input Parameters
* `user_id` - _required_
* `project_id` - _required_

### View specific user assigned to project

*Tags:* `Projects`

#### Input Parameters
* `user_id` - _required_
* `project_id` - _required_

### Add new stock_locations

*Tags:* `StockLocations`

### Delete location

*Tags:* `StockLocations`

#### Input Parameters
* `location_id` - _required_

### View single location

*Tags:* `StockLocations`

#### Input Parameters
* `location_id` - _required_

### Edit location

*Tags:* `StockLocations`

#### Input Parameters
* `location_id` - _required_

### Add new time entry

*Tags:* `TimeEntries`

### Delete time entry

*Tags:* `TimeEntries`

#### Input Parameters
* `time_entry_id` - _required_

### View time entry

*Tags:* `TimeEntries`

#### Input Parameters
* `time_entry_id` - _required_

### Edit time entry

*Tags:* `TimeEntries`

#### Input Parameters
* `time_entry_id` - _required_

### View time entry interval

*Tags:* `TimeEntryIntervals`

#### Input Parameters
* `time_entry_interval_id` - _required_

### Add new time entry type

*Tags:* `TimeEntryTypes`

### Delete time entry type

*Tags:* `TimeEntryTypes`

#### Input Parameters
* `time_entry_type_id` - _required_

### View time entry type

*Tags:* `TimeEntryTypes`

#### Input Parameters
* `time_entry_type_id` - _required_

### Edit time entry type

*Tags:* `TimeEntryTypes`

#### Input Parameters
* `time_entry_type_id` - _required_

### View time entry unit type

*Tags:* `TimeEntryUnitTypes`

#### Input Parameters
* `time_entry_unit_type_id` - _required_

### View time entry value type

*Tags:* `TimeEntryValueTypes`

#### Input Parameters
* `time_entry_value_type_id` - _required_

### Add user to company

*Tags:* `Users`

### Delete user

*Tags:* `Users`

#### Input Parameters
* `user_id` - _required_

### View user

*Tags:* `Users`

#### Input Parameters
* `user_id` - _required_

### Edit user

*Tags:* `Users`

#### Input Parameters
* `user_id` - _required_

### View single vendor product

*Tags:* `VendorProducts`

#### Input Parameters
* `vendor_product_id` - _required_

### Add wall comment

*Tags:* `WallComments`

### View wall comment

*Tags:* `WallComments`

#### Input Parameters
* `wall_comment_id` - _required_

### Add a wall post

*Tags:* `WallPosts`

### View wall post

*Tags:* `WallPosts`

#### Input Parameters
* `wall_post_id` - _required_

## License

: apacta<br/>
                    <br/>

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
