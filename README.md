<img src="https://raw.githubusercontent.com/kelaberetiv/TagUI/new_logo/src/media/tagui_logo.png" height="111" align="right">

# TagUI

**TagUI is a command-line tool for digital process automation (RPA).**

### [Download TagUI v6.0.0 here.](https://tagui.readthedocs.io/en/readthedocs_page/setup.html)

Write flows (scripts) in simple TagUI language and automate your web, mouse and keyboard interactions on the desktop.

TagUI is free to use and open-source. It's easy to setup and use and works on Windows, macOS and Linux.

In TagUI language, you use _steps_ like `click` and `type` and interact with _identifiers_.

Here's what a simple TagUI flow looks like:

.. code-block:: none

    https://www.typeform.com

    click login
    type username as user@gmail.com
    type password as 12345678
    click btnlogin

    download https://admin.typeform.com/xxx to report.csv
