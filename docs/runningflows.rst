Usage
====================

Running flows
--------------

Run TagUI in the Command Prompt/Terminal like this: ``tagui my_flow.tag``

Running flows with options
---------------------------

You can use the below options when running ``tagui``. 

For example, ``tagui my_flow.tag headless report`` runs ``my_flow.tag`` without showing the web browser, while storing the flow run result in ``tagui_report.csv``.

headless
    Runs the flow without a visible browser (does not work for visual automation).

report
    Tracks flow run result in ``tagui/src/tagui_report.csv`` and saves html log of automation execution.

my_datatable.csv
    Uses the specified csv file as the datatable. See :ref:`_datatables`.

speed
    Runs a datatable flow, skipping the default 3s delay and restarting of Chrome between datatable iterations.

See :doc:`other deprecated options </dep_options>`.

Running flows as desktop icons
--------------------------------

You can run flows just by double-clicking a file.

On Windows, create a ``.cmd`` or ``.bat`` file with contents like below. 

::

    @echo off
    cd c:\path\to\my\flow
    tagui my_flow.tag

On macOS/Linux, create a ``.sh`` file with contents like below and run ``chmod 700 my_file.sh``.

::

    cd /Users/username/folder
    tagui my_flow.tag

Running flows on a fixed schedule
--------------------------------------

It is often useful to run flows automatically on a fixed schedule: monthly; weekly; daily or even every 5 minutes.

On Windows, `use the Task Scheduler <https://www.digitalcitizen.life/how-create-task-basic-task-wizard>`_.

On macOS/Linux, `use crontab <https://www.ostechnix.com/a-beginners-guide-to-cron-jobs/>`_.


Storing flow run results
-------------------------

When the ``report`` option is used, TagUI will save flow run results to ``tagui/src/tagui_report.csv``. HTML logs will also be generated to store the full execution sequences and outcomes.

=== ==================================== ========================================= ============== ================================================== ======================================================
 #   Automation Flow                       Start Time                                Finish Time   Error Status                                       Log File
--- ------------------------------------ ----------------------------------------- -------------- -------------------------------------------------- ------------------------------------------------------
1   /Users/kensoh/Desktop/download_flow    Sun Apr 07 2019 17:33:58 GMT+0800 (+08)       32.1        SUCCESS                                          /Users/kensoh/Desktop/download_flow_1.html
2   /Users/kensoh/Desktop/upload_flow      NOT STARTED                               NOT FINISHED   [LINE 1] cannot understand step self-destruct     /Users/kensoh/Desktop/upload_flow_2.html
3   /Users/kensoh/Desktop/update_flow      NOT STARTED                               NOT FINISHED   [LINE 1] cannot understand step reboot computer   /Users/kensoh/Desktop/update_flow_3.html
4   /Users/kensoh/Desktop/booking_flow     Sun Apr 07 2019 17:39:00 GMT+0800 (+08)   NOT FINISHED   cannot find confirm_booking                       /Users/kensoh/Desktop/booking_flow_4.html
=== ==================================== ========================================= ============== ================================================== ======================================================

Create log files for debugging
---------------------------------

To do advanced debugging, you can create log files when running flows by creating an empty ``tagui_logging`` file in ``tagui/src/``.

- ``my_flow.tag.log`` stores output of the execution. 
- ``my_flow.tag.js`` is the generated JavaScript file that was run.
- ``my_flow.tag.raw`` is the expanded flow after parsing modules.
