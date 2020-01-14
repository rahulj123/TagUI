Download and Setup
*******************

Recommended setup for Windows
-------------------------------

1. `Download TagUI v6.0.0 for Windows <https://github.com/kelaberetiv/TagUI/releases/download/v5.11.0/TagUI_Windows.zip>`_.

2. Unzip the contents to ``C:\``.

3. `Install OpenJDK for Windows <https://corretto.aws/downloads/latest/amazon-corretto-8-x64-windows-jdk.msi>`_).

4. `Install Chrome <https://www.google.com/chrome/>`_ (if not yet installed).

5. Run ``setx path "%path%;c:\tagui\src"`` in Command Prompt.

**Troubleshooting**

- If you see 'MSVCR110.dll is missing' error, `install Visual C++ Redistributable <https://www.microsoft.com/en-us/download/details.aspx?id=30679>`_ (choose vcredist_x86.exe).

- If you cannot unzip to ``C:\``, unzip to your desktop.


Recommended setup for macOS/Linux
-----------------------------------
1. Download TagUI v6.0.0 (`macOS <https://github.com/kelaberetiv/TagUI/releases/download/v5.11.0/TagUI_macOS.zip>`_, `Linux <https://github.com/kelaberetiv/TagUI/releases/download/v5.11.0/TagUI_Linux.zip>`_).

2. Unzip the contents to your desktop on macOS, or ``/home/your_userid`` on Linux.

3. Install OpenJDK (`macOS <https://corretto.aws/downloads/latest/amazon-corretto-8-x64-macos-jdk.pkg>`_, `Linux <https://corretto.aws/downloads/latest/amazon-corretto-8-x64-linux-jdk.tar.gz>`_).

4. `Install Chrome <https://www.google.com/chrome/>`_ (if not yet installed).

5. Run ``ln -sf /your_tagui_path/tagui/src/tagui /usr/local/bin/tagui`` in Terminal.

**Troubleshooting**

- For newer macOS versions, if you get a ``dyld: Library not loaded`` error, `install OpenSSL in this way <https://github.com/kelaberetiv/TagUI/issues/86>`_. macOS Catalina update has introduced tighter security controls, see solutions for the `PhantomJS <https://github.com/kelaberetiv/TagUI/issues/601>`_ and `Java popups <https://github.com/kelaberetiv/TagUI/issues/598>`_.

- Linux distributions which do not have PHP pre-installed (eg. Ubuntu) must install PHP separately.

Running your first flow
--------------------------

On Windows, run this in Command Prompt::

    tagui c:\tagui\src\samples\1_yahoo chrome

On macOS/Linux, run this in Terminal::

    ./tagui your_tagui_path\tagui\src\samples\1_yahoo chrome

Congratulations, you have run your first TagUI flow!


Cutting edge version
--------------------------

To use the latest features and fixes, first download TagUI with the recommended setup above, then `download the cutting edge version <https://github.com/kelaberetiv/TagUI/archive/develop.zip>`_ and overwrite the files in the ``tagui/src/`` folder.