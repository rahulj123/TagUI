Step reference
===================

The steps you can use in TagUI are listed here.

Basic Step|Parameters (separator in bold)|Purpose
:---------|:-----------------------------|:------
http(s)://|just enter full url of webpage (\`variable\` for variable)|go to specified webpage
click|element to click|click on an element
rclick|element to right-click|right-click on an element
dclick|element to double-click|double-click on an element
hover|element to hover|move cursor to element
type|element ***as*** text ([enter] = enter, [clear] = clear field)|enter element as text
select|element to select ***as*** option value ([clear] = clear selection)|choose dropdown option
read|element to read (page = webpage) ***to*** variable name|fetch element text to variable
show|element to read (page = webpage, ie raw html) |print element text to output
save|element (page = webpage) ***to*** optional filename|save element text to file
snap|element (page = webpage) ***to*** optional filename|save screenshot to file
snap (pdf)|page ***to*** filename.pdf (headless Chrome / PhantomJS)|save webpage to basic pdf
load|filename ***to*** variable name|load file content to variable
echo|text (in quotation marks) and variables|print text/variables to output
dump|text (in quotation marks) and variables ***to*** optional filename|save text/variables to file
write|text (in quotation marks) and variables ***to*** optional filename|append text/variables to file
variable_name| = value (for text, put in quotes, use + to concat)|define variable variable_name
// (on new line)|user comments (ignored during execution)|add user comments
ask|question or instruction for user (reply stored in ask_result)|ask user for input
live|try steps or code interactively for Chrome / visual automation|enter live mode ([Firefox not yet](https://github.com/laurentj/slimerjs/issues/639))

Pro Step|Parameters (separator in bold)|Purpose
:-------|:-----------------------------|:------
tagui|relative or absolute filename (see MODULES section)|run another tagui flow
keyboard|keystrokes and modifiers (using visual automation)|send keystrokes to screen
mouse|down or up (using sikuli visual automation)|send mouse event to screen
table|element (XPath selector only) ***to*** optional filename.csv|save basic html table to csv
wait|optional time in seconds (default is 5 seconds)|explicitly wait for some time
check|condition **&#124;** text (in quotes) if true **&#124;** text (in quotes) if false|check condition and print result
upload|element (CSS selector only) ***as*** filename to upload|upload file to website
download|url to download ***to*** filename to save|download from url to file
receive|url keyword to watch ***to*** filename to save|receive resource to file
frame|frame name **&#124;** subframe name if any|next step or block in frame/subframe
popup|url keyword of new tab window to look for|next step or block in new tab window
{ and }|use { to start block and } to end block (on new line)|define block of steps and code
api|full url (including parameters) of api call|call api & save response to api_result
run|OS shell command including parameters|run OS command & save to run_result
dom|javascript code for document object model|run code in dom & save to dom_result
js|javascript statements (skip auto-detection)|treat as JS code explicitly
r|R statements for big data and machine learning|run R statements & save to r_result
py|python code for big data and machine learning|run python code & save to py_result
vision|custom visual automation commands|run custom sikuli commands
timeout|time in seconds before step errors out|change auto-wait timeout
