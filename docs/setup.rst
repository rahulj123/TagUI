Download and Setup
*******************

Recommended setup
--------------------------

1. Download TagUI v6.0.0 for:

- `Windows <https://github.com/kelaberetiv/TagUI/releases/download/v5.11.0/TagUI_Windows.zip>`_
- `macOS <https://github.com/kelaberetiv/TagUI/releases/download/v5.11.0/TagUI_macOS.zip>`_
- `Linux <https://github.com/kelaberetiv/TagUI/releases/download/v5.11.0/TagUI_Linux.zip>`_

2. Unzip to ``C:\`` on Windows, or your desktop on macOS, or ``/home/your_userid`` on Linux.

3. `Install Java <https://www.java.com/en/download/>`_ (if not yet installed).

4. `Install Chrome <https://www.google.com/chrome/>`_ (if not yet installed).

5. To make the ``tagui`` command always available:

- For macOS/Linux, run ``ln -sf /your_tagui_path/tagui/src/tagui /usr/local/bin/tagui`` in Terminal.
- For Windows, run ``setx path "%path%;c:\tagui\src"`` in Command Prompt.


Running your first flow
--------------------------

On Windows, run this in Command Prompt::

    tagui c:\tagui\src\samples\1_yahoo chrome

On macOS/Linux, run this in Terminal::

    ./tagui your_tagui_path\tagui\src\samples\1_yahoo chrome

Congratulations, you have run your first TagUI flow!

npm installation
------------------

Alternatively, you can install TagUI via npm::

    npm install tagui


Cutting edge version
--------------------------

To use the latest features and fixes, first download TagUI with the recommended setup above, then `download the cutting edge version <https://github.com/kelaberetiv/TagUI/archive/develop.zip>`_ and overwrite the files in the ``src`` folder.


Troubleshooting
--------------------
- If you see 'MSVCR110.dll is missing' error, `install this from Microsoft website <https://www.microsoft.com/en-us/download/details.aspx?id=30679>`_ (choose vcredist_x86.exe) - this file is required to run the Windows PHP engine packaged with TagUI. Some IT policies restrict TagUI from writing to c:\tagui and working properly, in that case please unzip to user desktop folder.
- For newer macOS versions, if you get a 'dyld: Library not loaded' error, `install OpenSSL in this way <https://github.com/kelaberetiv/TagUI/issues/86>`_. macOS Catalina update has introduced tighter security controls, see solutions for the `PhantomJS <https://github.com/kelaberetiv/TagUI/issues/601>`_ and `Java popups <https://github.com/kelaberetiv/TagUI/issues/598>`_.
- For some flavours of Linux (Ubuntu for example) which do not have PHP pre-installed, google how to install PHP accordingly (eg Ubuntu, apt-get install php). Most Linux distributions would already come with PHP.
- If you Ctrl+C to break a TagUI automation, you can use tagui/src/end_processes command (for macOS/Linux) or end_processes.cmd (for Windows) to kill any dead processes of TagUI integrations (Chrome, SikuliX, Python etc)
