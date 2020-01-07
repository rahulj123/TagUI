How It Works
================


Architecture diagram
-------------------------
![TagUI Flowchart](https://raw.githubusercontent.com/kelaberetiv/TagUI/master/src/media/flowchart.png)

Description of files
-------------------------

Core Files|Purpose
:---------|:------
tagui|main runner for TagUI automation
tagui.cmd|main runner for Windows platform
tagui_config.txt|web browser settings used for automation
tagui_parse.php|to interpret natural language into code
tagui_header.js|template for CasperJS / integrations code
tagui_footer.js|template for CasperJS / integrations code
test/positive_test|TagUI's interpretation positive test cases
test/positive_test.signature|.js signature for positive test cases

| Multi-Language      | Purpose                                   |
| :------------------ | :---------------------------------------- |
| translate.php       | translation engine for native languages   |
| translate.log       | translation in English reference language |
| languages/build     | script to self-build language definitions |
| languages/build.csv | default languages to be self-built        |

| Chrome Integration | Purpose                                   |
| :----------------- | :---------------------------------------- |
| tagui_chrome.php   | PHP thread for Chrome integration         |
| tagui_chrome.log   | log for Chrome websocket transactions     |
| tagui_chrome.in    | interface in-file for Chrome integration  |
| tagui_chrome.out   | interface out-file for Chrome integration |

| SikuliX Integration | Purpose                                    |
| :------------------ | :----------------------------------------- |
| tagui.py            | interface for SikuliX visual automation    |
| tagui.log           | log for SikuliX Python transactions        |
| tagui_windows.log   | same as above but for Windows              |
| tagui_sikuli.in     | interface in-file for SikuliX integration  |
| tagui_sikuli.out    | interface out-file for SikuliX integration |
| tagui_sikuli.txt    | Tesseract OCR integration interface file   |

| Python Integration   | Purpose                                   |
| :------------------- | :---------------------------------------- |
| tagui_py.py          | interface for Python integration          |
| tagui_py.log         | log for Python platform transactions      |
| tagui_py_windows.log | same as above but for Windows             |
| tagui_py.in          | interface in-file for Python integration  |
| tagui_py.out         | interface out-file for Python integration |
| tagui_py.txt         | integration file for storing output       |

| R Integration       | Purpose                              |
| :------------------ | :----------------------------------- |
| tagui_r.R           | interface for R integration          |
| tagui_r.log         | log for R platform transactions      |
| tagui_r_windows.log | same as above but for Windows        |
| tagui_r.in          | interface in-file for R integration  |
| tagui_r.out         | interface out-file for R integration |
| tagui_r.txt         | integration file for storing output  |

| API Service        | Purpose                                   |
| :----------------- | :---------------------------------------- |
| tagui_crontab      | to run service request batch from crontab |
| tagui_runner.php   | retrieving service requests from queue    |
| tagui_service.php  | receiving service requests into queue     |
| tagui_service.log  | log to track service requests history     |
| tagui_service.in   | log to track incoming service requests    |
| tagui_service.out  | log to track processed service requests   |
| tagui_service.act  | service request batch ready to execute    |
| tagui_service.run  | service request batch currently running   |
| tagui_service.done | service request batch finished running    |

| CLI Assistant    | Purpose                                |
| :--------------- | :------------------------------------- |
| erina            | natural language command line helper   |
| erina.cmd        | same as above but for Windows platform |
| tagui_helper.php | command line natural language parser   |
| tagui_helper     | generated normal TagUI command to run  |
| tagui_helper.cmd | same as above but for Windows platform |

| Miscellaneous Files | Purpose                                      |
| :------------------ | :------------------------------------------- |
| end_processes       | kill all processes of TagUI and integrations |
| end_processes.cmd   | same as above but for Windows platform       |
| tagui_datatable.csv | temporary datatable internal representation  |
| transpose.php       | transpose conventional datatable csv file    |
| tagui_report.php    | to track run results and keep html logs      |
| tagui_report.csv    | run results tracked using report option      |
| sleep.php           | allow adding execution pause on Windows      |

| User-defined Files | Purpose                                       |
| :----------------- | :-------------------------------------------- |
| tagui_local.csv    | local repository (put in same folder as flow) |
| tagui_global.csv   | global repository (put in tagui/src folder)   |
| tagui_local.js     | local functions (put in same folder as flow)  |
| tagui_global.js    | global functions (put in tagui/src folder)    |