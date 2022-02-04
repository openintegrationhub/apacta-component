# ![LOGO](https://cdn.iconscout.com/icon/free/png-256/jira-282222.png) Apacta OIH Connector

## Description

[![Generic badge](https://cdn.iconscout.com/icon/free/png-256/jira-282222.png)](https://shields.io/)

A generated OIH connector for the Apacta API (version 0.0.1).

Generated from: https://api.apis.guru/v2/specs/apacta.com/0.0.1/swagger.json<br/>
Generated at: 2021-04-26T15:21:35+02:00

## API Description

API for a tool to craftsmen used to register working hours, material usage and quality assurance. <br/>

# Endpoint<br/>

The endpoint `https://app.apacta.com/api/v1` should be used to communicate with the API. API access is only allowed with SSL encrypted connection (https).<br/>

# Authentication<br/>

URL query authentication with an API key is used, so appending `?api_key={api_key}` to the URL where `{api_key}` is found within Apacta settings is used for authentication<br/>

## Authorization

Supported authorization schemes:

- API Key

- API Key
- Uses the user's API token found from within the control panel in "settings" -> "additional settings"

## Actions

### Get list of cities supported in Apacta

_Tags:_ `Cities`

#### Input Parameters

- `zip_code` - _optional_ - Used to search for a city with specific zip code<br/>

### Get details about one city

_Tags:_ `Cities`

#### Input Parameters

- `city_id` - _required_

### Get a list of clocking records

_Tags:_ `ClockingRecords`

#### Input Parameters

- `active` - _optional_ - Used to search for active clocking records<br/>

### Create clocking record for authenticated user

_Tags:_ `ClockingRecords`

### Checkout active clocking record for authenticated user

_Tags:_ `ClockingRecords`

### Delete a clocking record

_Tags:_ `ClockingRecords`

#### Input Parameters

- `clocking_record_id` - _required_

### Details of 1 clocking_record

_Tags:_ `ClockingRecords`

#### Input Parameters

- `clocking_record_id` - _required_

### Edit a clocking record

_Tags:_ `ClockingRecords`

#### Input Parameters

- `clocking_record_id` - _required_

### Get a list of companies

_Tags:_ `Companies`

### Details of 1 company

_Tags:_ `Companies`

#### Input Parameters

- `company_id` - _required_

### Get a list of integration feature settings

_Tags:_ `Companies`

#### Input Parameters

- `company_id` - _required_

### Show details of 1 integration feature setting

_Tags:_ `Companies`

#### Input Parameters

- `company_id` - _required_
- `integration_feature_setting_id` - _required_

### Get list of contact types supported in Apacta

_Tags:_ `ContactTypes`

#### Input Parameters

- `identifier` - _optional_ - Search for specific identifier value<br/>

### Get details about one contact type

_Tags:_ `ContactTypes`

#### Input Parameters

- `contact_type_id` - _required_

### Get a list of contacts

_Tags:_ `Contacts`

#### Input Parameters

- `name` - _optional_ - Used to search for a contact with a specific name<br/>
- `cvr` - _optional_ - Search for values in CVR field<br/>
- `ean` - _optional_ - Search for values in EAN field<br/>
- `erp_id` - _optional_ - Search for values in ERP id field<br/>
- `contact_type` - _optional_ - Used to show only contacts with with one specific `ContactType`<br/>
- `city` - _optional_ - Used to show only contacts with with one specific `City`<br/>

### Add a new contact

_Tags:_ `Contacts`

### Delete a contact

_Tags:_ `Contacts`

#### Input Parameters

- `contact_id` - _required_

### Details of 1 contact

_Tags:_ `Contacts`

#### Input Parameters

- `contact_id` - _required_

### Edit a contact

_Tags:_ `Contacts`

#### Input Parameters

- `contact_id` - _required_

### Get list of currencies supported in Apacta

_Tags:_ `Currencies`

### Get details about one currency

_Tags:_ `Currencies`

#### Input Parameters

- `currency_id` - _required_

### Used to retrieve details about the logged in user's hours

_Tags:_ `EmployeeHours`

#### Input Parameters

- `date_from` - _required_ - Date formatted as Y-m-d (2016-06-28)<br/>
- `date_to` - _required_ - Date formatted as Y-m-d (2016-06-28)<br/>

### Show list of expense files

_Tags:_ `ExpenseFiles`

#### Input Parameters

- `created_by_id` - _optional_
- `expense_id` - _optional_

### Add file to expense

_Tags:_ `ExpenseFiles`

### Delete file

_Tags:_ `ExpenseFiles`

#### Input Parameters

- `expense_file_id` - _required_

### Show file

_Tags:_ `ExpenseFiles`

#### Input Parameters

- `expense_file_id` - _required_

### Edit file

_Tags:_ `ExpenseFiles`

#### Input Parameters

- `expense_file_id` - _required_

### Show list of expense lines

_Tags:_ `ExpenseLines`

#### Input Parameters

- `created_by_id` - _optional_
- `currency_id` - _optional_
- `expense_id` - _optional_

### Add line to expense

_Tags:_ `ExpenseLines`

### Delete expense line

_Tags:_ `ExpenseLines`

#### Input Parameters

- `expense_line_id` - _required_

### Show expense line

_Tags:_ `ExpenseLines`

#### Input Parameters

- `expense_line_id` - _required_

### Edit expense line

_Tags:_ `ExpenseLines`

#### Input Parameters

- `expense_line_id` - _required_

### Show list of expenses

_Tags:_ `Expenses`

#### Input Parameters

- `created_by_id` - _optional_
- `company_id` - _optional_
- `contact_id` - _optional_
- `project_id` - _optional_
- `gt_created` - _optional_ - Created after date<br/>
- `lt_created` - _optional_ - Created before date<br/>

### Add line to expense

_Tags:_ `Expenses`

### Delete expense

_Tags:_ `Expenses`

#### Input Parameters

- `expense_id` - _required_

### Show expense

_Tags:_ `Expenses`

#### Input Parameters

- `expense_id` - _required_

### Edit expense

_Tags:_ `Expenses`

#### Input Parameters

- `expense_id` - _required_

### Show list of all OIOUBL files for the expense

_Tags:_ `Expense OIOUBL files`

#### Input Parameters

- `expense_id` - _required_

### Show OIOUBL file

_Tags:_ `Expense OIOUBL files`

#### Input Parameters

- `expense_id` - _required_
- `file_id` - _required_

### Get list of form field types

_Tags:_ `FormFieldTypes`

#### Input Parameters

- `name` - _optional_ - Used to filter on the `name` of the form_fields<br/>
- `identifier` - _optional_ - Used to filter on the `identifier` of the form_fields<br/>

### Get details about single `FormField`

_Tags:_ `FormFieldTypes`

#### Input Parameters

- `form_field_type_id` - _required_

### Add a new field to a `Form`

_Tags:_ `FormFields`

### Get details about single `FormField`

_Tags:_ `FormFields`

#### Input Parameters

- `form_field_id` - _required_

### Get array of form_templates for your company

_Tags:_ `FormTemplates`

#### Input Parameters

- `name` - _optional_ - Used to filter on the `name` of the form_templates<br/>
- `identifier` - _optional_ - Used to filter on the `identifier` of the form_templates<br/>
- `pdf_template_identifier` - _optional_ - Used to filter on the `pdf_template_identifier` of the form_templates<br/>
- `description` - _optional_ - Used to filter on the `description` of the form_templates<br/>

### View one form template

_Tags:_ `FormTemplates`

#### Input Parameters

- `form_template_id` - _required_

### Retrieve array of forms

_Tags:_ `Forms`

#### Input Parameters

- `extended` - _optional_ - Used to have extended details from the forms from the `Form`'s `FormFields`<br/>
  Possible values: true, false.
- `date_from` - _optional_ - Used in conjunction with `date_to` to only show forms within these dates - format like `2016-28-05`<br/>
- `date_to` - _optional_ - Used in conjunction with `date_from` to only show forms within these dates - format like `2016-28-30`<br/>
- `project_id` - _optional_ - Used to filter on the `project_id` of the forms<br/>
- `created_by_id` - _optional_ - Used to filter on the `created_by_id` of the forms<br/>
- `form_template_id` - _optional_ - Used to filter on the `form_template_id` of the forms<br/>

### Add new form

> Used to add a form into the system<br/>

_Tags:_ `Forms`

### Delete a form

> You can only delete the forms that you've submitted yourself<br/>

_Tags:_ `Forms`

#### Input Parameters

- `form_id` - _required_

### View form

_Tags:_ `Forms`

#### Input Parameters

- `form_id` - _required_

### Edit a form

_Tags:_ `Forms`

#### Input Parameters

- `form_id` - _required_

### View list of invoice lines

_Tags:_ `InvoiceLines`

#### Input Parameters

- `invoice_id` - _optional_
- `product_id` - _optional_
- `user_id` - _optional_
- `name` - _optional_
- `discount_text` - _optional_

### Add invoice

_Tags:_ `InvoiceLines`

### Delete invoice line

_Tags:_ `InvoiceLines`

#### Input Parameters

- `invoice_line_id` - _required_

### View invoice line

_Tags:_ `InvoiceLines`

#### Input Parameters

- `invoice_line_id` - _required_

### Edit invoice line

_Tags:_ `InvoiceLines`

#### Input Parameters

- `invoice_line_id` - _required_

### View list of invoices

_Tags:_ `Invoices`

#### Input Parameters

- `contact_id` - _optional_ - Used to filter on the `contact_id` of the invoices<br/>
- `project_id` - _optional_ - Used to filter on the `project_id` of the invoices<br/>
- `invoice_number` - _optional_ - Used to filter on the `invoice_number` of the invoices<br/>
- `offer_number` - _optional_
- `is_draft` - _optional_
  Possible values: 0, 1.
- `is_offer` - _optional_
  Possible values: 0, 1.
- `is_locked` - _optional_
  Possible values: 0, 1.
- `date_from` - _optional_
- `date_to` - _optional_
- `issued_date` - _optional_

### Add invoice

_Tags:_ `Invoices`

### Delete invoice

_Tags:_ `Invoices`

#### Input Parameters

- `invoice_id` - _required_

### View invoice

_Tags:_ `Invoices`

#### Input Parameters

- `invoice_id` - _required_

### Edit invoice

_Tags:_ `Invoices`

#### Input Parameters

- `invoice_id` - _required_

### View list of mass messages for specific user

_Tags:_ `MassMessagesUsers`

#### Input Parameters

- `is_read` - _optional_ - Used to filter on the `is_read` of the mass messages<br/>

### View mass message

_Tags:_ `MassMessagesUsers`

#### Input Parameters

- `mass_messages_user_id` - _required_

### Edit mass message

_Tags:_ `MassMessagesUsers`

#### Input Parameters

- `mass_messages_user_id` - _required_

### View list of all materials

_Tags:_ `Materials`

#### Input Parameters

- `barcode` - _optional_ - Used to filter on the `barcode` of the materials<br/>
- `name` - _optional_ - Used to filter on the `name` of the materials<br/>
- `project_id` - _optional_ - Used to find materials used in specific project by `project_id`<br/>
- `currently_rented` - _optional_ - Used to find currently rented materials<br/>

### Delete material

_Tags:_ `Materials`

#### Input Parameters

- `material_id` - _required_

### View material

_Tags:_ `Materials`

#### Input Parameters

- `material_id` - _required_

### Edit material

_Tags:_ `Materials`

#### Input Parameters

- `material_id` - _required_

### Show list of rentals for specific material

_Tags:_ `MaterialRentals`

#### Input Parameters

- `material_id` - _required_

### Add material rental

_Tags:_ `MaterialRentals`

#### Input Parameters

- `material_id` - _required_

### Checkout material rental

_Tags:_ `MaterialRentals`

#### Input Parameters

- `material_id` - _required_

### Delete material rental

> Delete rental for material<br/>

_Tags:_ `MaterialRentals`

#### Input Parameters

- `material_id` - _required_
- `material_rental_id` - _required_

### Show rental foor materi

_Tags:_ `MaterialRentals`

#### Input Parameters

- `material_id` - _required_
- `material_rental_id` - _required_

### Add material

_Tags:_ `Materials`

#### Input Parameters

- `material_id` - _required_
- `material_rental_id` - _required_

### Edit material rental

_Tags:_ `MaterialRentals`

#### Input Parameters

- `material_id` - _required_
- `material_rental_id` - _required_

### Get a list of payment term types

_Tags:_ `PaymentTermTypes`

### Details of 1 payment term type

_Tags:_ `PaymentTermTypes`

#### Input Parameters

- `payment_term_type_id` - _required_

### Get a list of payment terms

_Tags:_ `PaymentTerms`

### Details of 1 payment term

_Tags:_ `PaymentTerms`

#### Input Parameters

- `payment_term_id` - _required_

### Check if API is up and API key works

_Tags:_ `Ping`

### List products

_Tags:_ `Products`

#### Input Parameters

- `name` - _optional_ - Used to filter on the `name` of the products<br/>
- `product_number` - _optional_ - Used to filter on the `product_number` of the products<br/>
- `barcode` - _optional_ - Used to filter on the `barcode` of the products<br/>

### Add new product

_Tags:_ `Products`

### Delete a product

_Tags:_ `Products`

#### Input Parameters

- `product_id` - _required_

### View single product

_Tags:_ `Products`

#### Input Parameters

- `product_id` - _required_

### Edit a product

_Tags:_ `Products`

#### Input Parameters

- `product_id` - _required_

### Get list of project statuses

_Tags:_ `ProjectStatuses`

### Get details about one contact type

_Tags:_ `ProjectStatuses`

#### Input Parameters

- `project_status_id` - _required_

### View list of projects

_Tags:_ `Projects`

#### Input Parameters

- `show_all` - _optional_ - Unless this is set to `true` only open projects will be shown<br/>
- `contact_id` - _optional_ - Used to filter on the `contact_id` of the projects<br/>
- `project_status_id` - _optional_ - Used to filter on the `project_status_id` of the projects<br/>
- `project_status_ids` - _optional_ - Used to filter on the `project_status_id` of the projects (match any of the provided values)<br/>
- `name` - _optional_ - Used to search on the `name` of the projects<br/>
- `erp_project_id` - _optional_ - Used to search on the `erp_project_id` of the projects<br/>
- `erp_task_id` - _optional_ - Used to search on the `erp_task_id` of the projects<br/>
- `start_time_gte` - _optional_ - Show projects with start time after than this value<br/>
- `start_time_lte` - _optional_ - Show projects with start time before this value<br/>
- `start_time_eq` - _optional_ - Show only projects with start time on specific date<br/>

### Add a project

_Tags:_ `Projects`

### Delete a project

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### View specific project

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Edit a project

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Show list of files uploaded to project

> Used to show files uploaded to a project from wall post or form<br/>

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Delete file

> Delete file uploaded to a project from wall post or form<br/>

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_
- `file_id` - _required_

### Show file

> Show file uploaded to a project from wall post or form<br/>

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_
- `file_id` - _required_

### Edit file

> Edit file uploaded to a project from wall post or form<br/>

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_
- `file_id` - _required_

### Show list of project files uploaded to project

> Returns files belonging to the project, not uploaded from wall post or form<br/>

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Add project file to projects

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Delete project file

_Tags:_ `Projects`

#### Input Parameters

- `project_file_id` - _required_
- `project_id` - _required_

### Show project file

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_
- `project_file_id` - _required_

### Edit project file

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_
- `project_file_id` - _required_

### Show list of users added to project

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Add user to project

_Tags:_ `Projects`

#### Input Parameters

- `project_id` - _required_

### Delete user from project

_Tags:_ `Projects`

#### Input Parameters

- `user_id` - _required_
- `project_id` - _required_

### View specific user assigned to project

_Tags:_ `Projects`

#### Input Parameters

- `user_id` - _required_
- `project_id` - _required_

### List stock_locations

_Tags:_ `StockLocations`

#### Input Parameters

- `name` - _optional_ - Used to filter on the `name` of the stock_locations<br/>

### Add new stock_locations

_Tags:_ `StockLocations`

### Delete location

_Tags:_ `StockLocations`

#### Input Parameters

- `location_id` - _required_

### View single location

_Tags:_ `StockLocations`

#### Input Parameters

- `location_id` - _required_

### Edit location

_Tags:_ `StockLocations`

#### Input Parameters

- `location_id` - _required_

### List time entries

_Tags:_ `TimeEntries`

#### Input Parameters

- `user_id` - _optional_
- `form_id` - _optional_
- `project_id` - _optional_
- `gt_from_time` - _optional_
- `lt_from_time` - _optional_
- `gt_to_time` - _optional_
- `lt_to_time` - _optional_
- `lt_sum` - _optional_
- `gt_sum` - _optional_

### Add new time entry

_Tags:_ `TimeEntries`

### Delete time entry

_Tags:_ `TimeEntries`

#### Input Parameters

- `time_entry_id` - _required_

### View time entry

_Tags:_ `TimeEntries`

#### Input Parameters

- `time_entry_id` - _required_

### Edit time entry

_Tags:_ `TimeEntries`

#### Input Parameters

- `time_entry_id` - _required_

### List possible time entry intervals

_Tags:_ `TimeEntryIntervals`

### View time entry interval

_Tags:_ `TimeEntryIntervals`

#### Input Parameters

- `time_entry_interval_id` - _required_

### List time entries types

_Tags:_ `TimeEntryTypes`

### Add new time entry type

_Tags:_ `TimeEntryTypes`

### Delete time entry type

_Tags:_ `TimeEntryTypes`

#### Input Parameters

- `time_entry_type_id` - _required_

### View time entry type

_Tags:_ `TimeEntryTypes`

#### Input Parameters

- `time_entry_type_id` - _required_

### Edit time entry type

_Tags:_ `TimeEntryTypes`

#### Input Parameters

- `time_entry_type_id` - _required_

### List possible time entry unit types

_Tags:_ `TimeEntryUnitTypes`

### View time entry unit type

_Tags:_ `TimeEntryUnitTypes`

#### Input Parameters

- `time_entry_unit_type_id` - _required_

### List possible time entry value types

_Tags:_ `TimeEntryValueTypes`

### View time entry value type

_Tags:_ `TimeEntryValueTypes`

#### Input Parameters

- `time_entry_value_type_id` - _required_

### Get list of users in company

_Tags:_ `Users`

#### Input Parameters

- `first_name` - _optional_ - Used to filter on the `first_name` of the users<br/>
- `last_name` - _optional_ - Used to filter on the `last_name` of the users<br/>
- `email` - _optional_ - Used to filter on the `email` of the users<br/>
- `stock_location_id` - _optional_ - Used to filter on the `stock_location_id` of the users<br/>

### Add user to company

_Tags:_ `Users`

### Delete user

_Tags:_ `Users`

#### Input Parameters

- `user_id` - _required_

### View user

_Tags:_ `Users`

#### Input Parameters

- `user_id` - _required_

### Edit user

_Tags:_ `Users`

#### Input Parameters

- `user_id` - _required_

### List vendor products

_Tags:_ `VendorProducts`

#### Input Parameters

- `name` - _optional_ - Used to filter on the `name` of the vendor products<br/>
- `product_number` - _optional_ - Used to filter on the `product_number` of the vendor products<br/>
- `barcode` - _optional_ - Used to filter on the `barcode` of the vendor products<br/>
- `vendor_id` - _optional_ - Used to filter on the `vendor_id` of the vendor products<br/>

### View single vendor product

_Tags:_ `VendorProducts`

#### Input Parameters

- `vendor_product_id` - _required_

### Add wall comment

_Tags:_ `WallComments`

### View wall comment

_Tags:_ `WallComments`

#### Input Parameters

- `wall_comment_id` - _required_

### View list of wall posts

_Tags:_ `WallPosts`

#### Input Parameters

- `project_id` - _required_
- `user_id` - _optional_

### Add a wall post

_Tags:_ `WallPosts`

### View wall post

_Tags:_ `WallPosts`

#### Input Parameters

- `wall_post_id` - _required_

### See wall comments to a wall post

_Tags:_ `WallPosts`

#### Input Parameters

- `wall_post_id` - _required_

## License

: apacta-Component<br/>
<br/>

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.