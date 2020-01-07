TagUI Chrome Extension
--------------------------

The TagUI Chrome extension records steps such as page navigation, clicking of web elements and entering information and outputs them as steps so you can save them as a flow.

After installing the Chrome extension, to start recording automation flows
  1. Go to the website URL you want to start the automation at
  2. Click the TagUI icon, followed by Start button
  3. Carry out the steps you want to automate
  4. Click the TagUI icon, followed by Stop button
  5. Click Export button to view generated TagUI script

While recording the steps, you can right-click to bring up a menu for steps such as showing the element identifier. The recording isn't foolproof (for example, the underlying recording engine cannot capture frames, popup windows or tab key input). It's meant to simplify flow creation with some edits, instead of typing everything manually. [See this video](https://www.youtube.com/watch?v=bFvsc4a8hWQ) for an example of recording a sequence of steps, editing for adjustments and playing back the automation.

`Download it from Chrome Web Store <https://chrome.google.com/webstore/detail/tagui-web-automation/egdllmehgfgjebhlkjmcnhiocfcidnjk/>`_.

TagUI Writer, Screenshoter & Editor
----------------------------------------

TagUI Writer is a Windows app created by Arnaud Degardin / [@adegard](https://github.com/adegard) which makes it easy to write TagUI scripts. By pressing Ctrl + Left-click, a popup menu will appear with the list of TagUI steps for you to paste into your text editor. Arnaud also created a ScreenShoter app which makes it easy to capture snapshots for TagUI visual automation. Lastly, TagUI Editor allows you to edit and run TagUI scripts via AutoHotKey. To download, [click here](https://github.com/adegard/tagui_scripts).

![TagUI Editor](https://raw.githubusercontent.com/adegard/tagui_scripts/master/TagUI_Editor.gif)

TagUI For Python
--------------------
TagUI for Python is a Python package created by TagUI's creator Ken Soh / [@kensoh](https://github.com/kensoh). It brings the digital process automation capabilities of TagUI directly to the Python environment through a simple, expressive and powerful API. To install, `pip install tagui`. For its Python API and architecture, refer to the [project homepage](https://github.com/tebelorg/TagUI-Python). At merely ~1k lines of code, the package is built on TagUI and its architecture is based on integration with TagUI's live mode.
