# Rdocs #


Class   SpreadsheetExamples
In:     SpreadsheetExamples.rb

Parent: Object
Contains all the methods listed in the "Using Ruby with the Google Data API's article"
Performs authentication via ClientLogin, feed retrieval, post and batch update requests.

## Methods ##
  * authenticate
  * batch\_update
  * create\_datastructure\_from\_xml
  * get\_feed
  * get\_my\_spreadsheets
  * get\_version\_string
  * get\_worksheet
  * post
  * set\_header\_content\_type\_to\_xml

## Constants ##
  * SPREADSHEET\_FEED     = 'http://spreadsheets.google.com/feeds/spreadsheets/private/full'
  * CONTENT\_TYPE\_FORM    = 'application/x-www-form-urlencoded'
  * CONTENT\_TYPE\_ATOMXML = 'application/atom+xml'

## Attributes ##
headers R

## Public Instance methods ##
```
authenticate(email, password)* Authenticate with ClientLogin
Args:
  email: string
  password: string

batch_update(batch_data, cellfeed_uri)
Perform a batch update using the cellsfeed of a specific spreadsheet
Args:
  batch_data: array of hashes of data to post
              sample hash: +batch_id+: string (i.e. "A")
                           +cell_id+: string (i.e. "R1C1")
                           +data+: string (i.e. "My data")
Returns:
  Net::HTTPResponse

create_datastructure_from_xml(xml)
Parse xml into a datastructure using xmlsimple
Args:
  xml: string
Returns:
  A hash containing the xml data provided in the argument

get_feed(uri)
Perform a GET request to a given uri
Args:
  uri: string
Returns:
  Net::HTTPResponse

get_my_spreadsheets()
Get spreadsheet feed for currently authenticated user

get_version_string(uri)
Obtain the version string for a specific cell
Args:
  uri: string
Returns:
  A string containing the version string

get_worksheet(spreadsheet_key)
Get the worksheets feed for a given spreadsheet
Args:
  spreadsheet_key: string
Returns:
  Net::HTTPResponse: The worksheet feed

post(uri, data)
Post data to a specific uri
Args:
  uri: string
  data: string (typically xml)
Returns:
  Net::HTTPResponse

set_header_content_type_to_xml()
Set "Content-Type" header to "application/atom+xml"
```