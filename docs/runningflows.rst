Usage
====================

Running flows with options
---------------------------

You can use the below options when running ``tagui``. 

For example, ``tagui my_flow.tag headless report`` runs ``my_flow.tag`` without showing the web browser, while storing the flow run result in ``tagui_report.csv``.

headless
    Runs the flow without a visible browser (does not work for visual automation).

report
    Tracks flow run result in ``tagui/src/tagui_report.csv`` and saves html log of automation execution.

my_datatable.csv
    Uses the specified csv file as the datatable for batch automation of many records.

speed
    Runs a datatable flow, skipping the default 3s delay and restarting of Chrome between datatable iterations.

See :doc:`other deprecated options </dep_options>`.

Running flows as desktop icons
--------------------------------

To do that on Windows, create a .cmd or .bat file with contents like the following, which goes to the directory where you want to run the automation, and run tagui command on the file with your specified options. Double-clicking the .cmd or .bat file will start automation.

::

    @echo off
    c:
    cd c:\folder
    tagui filename quiet speed chrome

To do that on macOS / Linux, create a file with contents like the following, which goes to the directory where you want to run the automation, and run tagui command on the file with your specified options. You will need to use the command chmod 700 on the file to give it execute permissions, so that it can be run by double-clicking on it.

::

    cd /Users/username/folder
    tagui filename quiet speed chrome

Create log files for debugging
---------------------------------

To create log files create an empty file `tagui_logging` in tagui/src folder.

After each automation run, a .log file will be created to store output of the execution, a .js file is the generated JavaScript file, a .raw is the expanded flow after reading in any module sub-scripts that are called in that flow.


Running flows on a fixed schedule
--------------------------------------

To schedule an automation flow with crontab (for macOS/Linux), for example at 8am daily

::

    0 8 * * * /full_path/tagui/src/tagui flow_filename option(s)

For Windows, use Task Scheduler (search schedule from Start Menu) or something like [Z-Cron](https://www.z-cron.com)

Sample flows
----------------

TagUI includes the following automation flow samples ([tagui/src/samples folder](https://github.com/kelaberetiv/TagUI/tree/master/src/samples))

=============== ==============================================================
 Flow Sample                          Purpose
--------------- --------------------------------------------------------------
1_yahoo         searches github on Yahoo and captures screenshot of results
2_twitter       goes to a Twitter page and saves some profile information
3_github        goes to a GitHub page and downloads the repository file
4_conditions    goes through examples of using conditions in natural language
5_repositories  shows using repositories on Russian social media site VK.com
6_datatables    set of flows uses datatables to retrieve and act on GitHub info
7_testing       shows how to use check step assertions for CI/CD integration
8_hastebin      used by upload option to upload flow result to hastebin.com
9_misc          shows how to use steps popup, frame, dom, js, { and } block
a_facedetect    uses face recognition to detect profile images on webpages
b_visualoutlook uses visual recognition for desktop MS Outlook email sending
c_chineseflow   run flow in other languages (first, change src/tagui_config.txt)
=============== ==============================================================


Storing run results
-----------------------

- when the ``report`` option is used, TagUI will save run results to tagui/src/tagui_report.csv
- this can be useful for audit, personal tracking or measuring time savings
- html logs will also be generated to store the full execution sequences and outcomes

\#|AUTOMATION FLOW|START TIME|FINISH TIME|ERROR STATUS|LOG FILE
:-|:--------------|:---------|:----------|:-----------|:-------
1 | /Users/kensoh/Desktop/download_flow | Sun Apr 07 2019 17:33:58 GMT+0800 (+08) | 32.1 | SUCCESS | /Users/kensoh/Desktop/download_flow_1.html
2 | /Users/kensoh/Desktop/upload_flow | NOT STARTED | NOT FINISHED | [LINE 1] cannot understand step self-destruct | /Users/kensoh/Desktop/upload_flow_2.html
3 | /Users/kensoh/Desktop/update_flow | NOT STARTED | NOT FINISHED | [LINE 1] cannot understand step reboot computer | /Users/kensoh/Desktop/update_flow_3.html
4 | /Users/kensoh/Desktop/booking_flow | Sun Apr 07 2019 17:39:00 GMT+0800 (+08) | NOT FINISHED | cannot find confirm_booking | /Users/kensoh/Desktop/booking_flow_4.html