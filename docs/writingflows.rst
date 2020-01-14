Writing Flows
====================

File extension
------------------

Flows should use the ``.tag`` file extension. 

However, it will still run flows using the legacy ``.tagui``, ``.txt`` or without extensions.

Sample flows
----------------

Learning by example is a great way to pick up TagUI.

There are various flow samples in the ``tagui/src/samples/`` folder showing various features and uses of TagUI.

==================== ==============================================================
 Flow Sample                          Purpose
-------------------- --------------------------------------------------------------
1_yahoo              saves a screenshot of webpage
2_twitter            saves profile information from Twitter
3_github             downloads a file
4_conditions         demonstrates conditions
5_repositories       demonstrates object repositories
6_datatables         demonstrates datatables
7_testing            demonstrates the check step
8_hastebin           uploads flow result to hastebin.com
9_misc               demonstrates popup, frame, dom, js, { and } block
a_facedetect         uses face recognition on profile images
b_visualoutlook      sends an email through Outlook
==================== ==============================================================


Identifiers
--------------

Web elements can be targeted with their XPath::

  xpath example here


Steps
---------
TagUI will wait for an UI element to appear and interacts with it as soon as it appears

TagUI selects provided identifier in this order - xpath, css, id, name, class, title, aria-label, text(), href

For headless and visible Chrome, file downloads can be done using normal webpage interaction or by specifying the URL as a navigation flow step. For Firefox and PhantomJS, the download and receive step can be used. Note that on Windows, snap step requires display magnification to be set at 100% to work properly.

As TagUI default execution context is local, to run javascript on webpage dom (eg document.querySelector) use dom step. Set dom_json variable to pass a variable for use in dom step. Or dom_json = {tmp_number: phone, tmp_text: name} to pass multiple variables for use in dom step (dom_json.tmp_number and dom_json.tmp_text).

Conditions
---------------

- Write text in quotation marks (either " or ' works) to differentiate text from variable names
- { and } block is required after for loop (while is deprecated - no auto-wait, hangs CasperJS)
- Use for loop to repeat blocks of steps (nested loops, conditions, break, continue supported)

.. code-block:: none

  if day equals to "Friday"
  if menu contains "fruits"
  if A more than B and C not equals to D
  for n from 1 to 4
  for n from 1 to infinity
  while cupcakes equal to 12
  contain
  not contain
  equal to
  not equal to
  more than
  more than or equal to
  less than
  less than or equal to
  and
  or

Use { and } step to define step/code blocks for powerful repetitive automation with for loop. The usual break and continue commands can be used on next line after an if condition, to break out of the immediate loop or continue to the next iteration. To loop 'indefinitely' use `for n from 1 to infinity`, where infinity is a pre-defined variable at 1024.

When using contain / equal, you can write with or without s behind. You can use if present('element') to check if the element exists, before doing the step on next line. Other useful functions include visible('element'), count('element'), url(), title(), text(), timer(), which can be used in conditions and steps such as check or echo.

Helper functions
------------------

- Below are helper functions which can be used in your steps or code like a variable
- You can define your own JS functions in tagui_local.js / tagui_global.js ([see eg](https://github.com/kelaberetiv/TagUI/issues/236#issuecomment-403188526))
- TagUI will look for a local function file tagui_local.js in the same folder of flow
- TagUI will also look for a global function file tagui_global.js in tagui/src folder
- Local definitions take precedence over global definitions (same for repositories)

================== =======================================================================
Function           Purpose
------------------ -----------------------------------------------------------------------
csv_row(row_array) return formatted string for writing to csv file, eg using write step
present('element') return true or false whether element identifier specified is present
visible('element') return true or false whether element identifier specified is visible
count('element')   return number of elements matching element identifier specified
clipboard('text')  put text to clipboard (eg to paste text quickly with keyboard step)
clipboard()        return clipboard text (eg to access text copied with keyboard step)
url()              return page url of current web page
title()            return page title of current web page
text()             return text content of current web page
timer()            return time elapsed in sec between calls
mouse_xy()         return (x,y) coordinates as string, for eg '(200,400)'
mouse_x()          return x coordinate as integer number, for eg 200
mouse_y()          return y coordinate as integer number, for eg 200
================== =======================================================================

csv_row() is useful for organising lots of data gathered during automation to be written into csv output file -

``csv_row()`` is useful for saving results to a csv file::

  read name_element to name
  read price_element to price
  read details_element to details
  item_info = [name, price, details]
  write csv_row(item_info) to product_list.csv


``clipboard()`` is useful for accessing text on the clipboard::

  dclick pdf_document.png
  wait 3 seconds
  keyboard [ctrl]a
  keyboard [ctrl]c
  text_contents = clipboard()


``mouse_xy()``, ``mouse_x()``, ``mouse_y()`` require visual automation and can be used to interact with UI (user-interface) elements on the screen by specifying their (x,y) coordinates, for eg below clicking to the right of an UI element by 200 pixels::

  hover element.png
  echo mouse_xy()
  x = mouse_x() + 200
  y = mouse_y()
  click (`x`,`y`)


Object repositories
------------------------

Object repositories are csv files, which can store variables for use in flows.

Each flow has a **local object repository** and all flows share the **global object repository**. The local object repository is the ``tagui_local.csv`` in the same folder as the flow. The global object repository is the ``tagui_global.csv`` in the ``tagui/src/`` folder.

An object repository could look like this:

============== =================================
object         definition
-------------- ---------------------------------
email          user-email-textbox
create account btn btn--green btn-xl signup-btn
============== =================================

Within the flow, TagUI can use the variables ``email``, ``create account``, ``type email`` and it will be replaced directly by the definition before it is run.

If ``user-email-textbox`` was the identifier for some web text input, then you could use the following in your flow::

  type ``email`` as my_email@email.com

.. _datatables:

Datatables
------------

Datatables are csv files, which can be used to run your flows multiple times with different inputs.

A datatable (``trade_data.csv``) could look like this:

= ============ ============= ======== ====== ====== =========
# trade        username      password pair   size   direction
- ------------ ------------- -------- ------ ------ ---------
1 Trade USDSGD test_account  12345678 USDSGD 10000  BUY
2 Trade USDSGD test_account  12345678 USDJPY 1000   SELL
3 Trade EURUSD test_account  12345678 EURUSD 100000 BUY
= ============ ============= ======== ====== ====== =========

To use it, you would run your flow with ``tagui my_flow.tag trade_data.csv``

TagUI will run ``my_flow.tag`` once for each row in the datatable (except the header).

Within the flow, TagUI can use the variables ``trade``, ``username``, ``password``, etc as if they were in the local object repository and the values will be from that run's row.

You can run the flow with the ``speed`` option like this: ``tagui my_flow.tag trade_data.csv speed`` to remove the delay between runs.


Visual automation
------------------------------------

TagUI can click on given screen coordinates or saved images.

This is particularly useful for interacting with desktop programs.

Applicable steps are click, hover, type, select, read, show, save, snap, keyboard, mouse. 

To use visual automation, simply specify an image (in .png or .bmp format) to visually look for in place of the element identifier. Relative paths are supported for image filenames (eg pc.png, images/button.bmp). Note that the element that corresponds to the image must be visible on the screen for visual automation to succeed. If it's blocked by another window for example, the automation will be unable to find the element.

Alternatively, you can specify the (x,y) coordinates of the element that you want to interact with.

To type onto the screen instead of a particular element, use `keyboard text` or `keyboard [modifiers]text` ([examples](https://github.com/kelaberetiv/TagUI/issues/370)). To do a snapshot or an OCR of the whole screen, use `page.png` or `page.bmp` as the element identifier for steps snap / read. The usual helper functions visible() / present() can also be used to check whether an image is visible on the screen.

Transparency (0% opacity) is supported in .png images, for eg using an image of an UI element with transparent background to enable clicking on an UI element that appears on different backgrounds on different occasions.

Another example is an image of the window or frame (PDF viewer, MS Word, textbox etc) with the center content of the image set as transparent. This allows using read, show, save, snap steps to perform OCR and save snapshots for application windows, containers, frames, textboxes with varying content. 

Also for these steps, (x1,y1)-(x2,y2) can be used as the identifier to define the region of interest on the screen to perform OCR or capture snapshot.


**Troubleshooting**

- On Windows, set display magnification to the recommended %, if it doesn't work then 100%.

- On macOS, if the image cannot be found, may be due to `how the image was captured <https://github.com/kelaberetiv/TagUI/issues/240#issuecomment-405030276>`_.

- On Linux, requires installing and setting up dependencies by [following this guide](https://sikulix-2014.readthedocs.io/en/latest/newslinux.html#version-1-1-4-special-for-linux-people)
