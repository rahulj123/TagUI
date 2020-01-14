Introduction
--------------

Write flows (scripts) in simple TagUI language and automate your web, mouse and keyboard interactions on the desktop.

TagUI is free to use and open-source. It's easy to setup and use and works on Windows, macOS and Linux.

In TagUI language, you use *steps* like ``click`` and ``type`` and interact with *identifiers*.

Here's what a simple TagUI flow looks like:

.. code-block:: none

    https://www.typeform.com

    click login
    type username as user@gmail.com
    type password as 12345678
    click btnlogin

    download https://admin.typeform.com/xxx to report.csv