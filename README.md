# nutrition-data

The USDA provides [a database of nutritional data][1], which is useful for food related
software.  It is structured as a zip of flat files and a PDF that describes the format.

This is a quick and dirty python script that converts that zip file to a sqlite
database.  To avoid hard-coding schemas, I try to parse the schema from the `pdftotext`
output of the documentation.

To run this you will need the `requests` and `sqlite3` python modules and the 
`pdftotext` executable.

The resulting database uses text fields for `NDB_NO`, per the specification in the
PDF file. If you don't need an exact match for the upstream identifiers, which
have leading zeros, you could convert these fields to integers.


[1]: http://www.ars.usda.gov/Services/docs.htm?docid=8964

