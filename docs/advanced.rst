Advanced flows
===================

This section covers advanced features of TagUI which may require knowledge of other programming languages.

Running other flows within a flow
-----------------------------------

A flow can run another flow, like this::

  tagui login_crm.tag

Variables in the parent flow are accessible child flow. 

Writing Python within flows
--------------------------------

You can write Python code in TagUI. 

Python needs to be `installed separately <https://www.python.org/downloads/>`_.

The ``py`` step can be used to run commands in Python.

You can pass string values back to TagUI with `print()`. The ``stdout`` will be stored in the ``py_result`` variable in TagUI.

A basic example::

  py a=1
  py b=2
  py c=a+b
  py print(c)
  echo py_result

You can also use ``py begin`` and ``py finish`` before and after a Python code block::

  py begin
  a=1
  b=2
  c=a+b
  print(c)
  py finish
  echo py_result

You can pass a variable to Python like this::

  phone = 1234567
  py 'phone = ' + phone
  py print(phone)
  echo py_result
