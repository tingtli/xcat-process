
After getting daily regression report from ``xCAT Jenkins Mail Bot`` every day,  can find 2 tables in the top of the mail to describe the over all results of last day regression and the failed cases for each project. 

Hover the mouse on the project for a while in these tables, can get project basic information. The project name is drawn red line underneath.

.. image:: https://github.com/xcat2/xcat-process/blob/master/pics/1.jpg

.. image:: https://github.com/xcat2/xcat-process/blob/master/pics/2.jpg


Mount ``10.0.0.122:/gpfs/cnfs01/data/xcat/jk/log`` on any directory in your own c910 server, then can access daily ragression detailed logs under this directory. ::

    mount 10.0.0.122:/gpfs/cnfs01/data/xcat/jk/log <your path>
    
Find the logs of specific project depending on project name under ``your path``. Take project ``rhels7.3-ppc64le-2.13.3-58`` shown in the first table above for example,  its logs were saved under ``/<your path>/rhels7.3-ppc64le-2.13.3/58``.


The files under ``/<your path>/rhels7.3-ppc64le-2.13.3/58`` are looked like below:

.. image:: https://github.com/xcat2/xcat-process/blob/master/pics/3.jpg

The important logs are:

+-----------------------------+--------------------------------------------------------------------------------------------------------+
|         Log Name            |                                    Description                                                         |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|rhels7.3-ppc64le-2.13.3-58   |The xcatjktst log for project rhels7.3-ppc64le-2.13.3-58.This log  is belong to automation framework.   |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|new_xcattest_installation.log|The log of xcattest installation in test cluster.                                                       |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|Xcattest.log.*               |There always are 2 xcattest.log                                                                         |
+                             +--------------------------------------------------------------------------------------------------------+
|                             |The first one includes the log of xcat installation. I.e. the log of case "install_xCAT_on_rhels_sles"  |
+                             +--------------------------------------------------------------------------------------------------------+
|                             |The second one includes the running log of all rest cases, including both successful and failed cases   |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|Failedcases.*                |There always are 2 failedcases log                                                                      |
+                             +--------------------------------------------------------------------------------------------------------+
|                             |The first one includes all failed cases in the first xcattest.log                                       |
+                             +--------------------------------------------------------------------------------------------------------+
|                             |The second one includes all failed cases in the second xcattest.log                                     |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|messages                     |The "/var/log/message" file pulled back from test cluster                                               |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|cluster.log                  |The "/var/log/xcat/cluster.log" file pulled back from test cluster.                                     |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|computes.log                 |The "/var/log/xcat/computes.log" file pulled back from test cluster.                                    |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|commands.log                 |The "/var/log/xcat/commands.log" file pulled back from test cluster.                                    |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|access_log                   |The "/var/log/httpd/access_log" file pulled back from test cluster.                                     |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|console_log/*                |The "/var/log/consoles" directory pulled back from test cluster,  (maybe failed to catch such log)      |
+-----------------------------+--------------------------------------------------------------------------------------------------------+

Other important files are:

+-----------------------------+--------------------------------------------------------------------------------------------------------+
|         Log Name            |                                    Description                                                         |
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|cluster.conf                 |The config file of xcattest used by this project.                                                       | 
+-----------------------------+--------------------------------------------------------------------------------------------------------+
|rhels7.3_ppc64le.bundle      |The bundle file used by this project.                                                                   |
+-----------------------------+--------------------------------------------------------------------------------------------------------+


How to debug for one specific failed case. Take case ``bmcdiscover_check_paswd`` shown in the second table above for example. Find all running process of case ``bmcdiscover_check_paswd`` in ``xcattest.log.20170415133104``. It looks like below(location the case by searching case name): 

.. image:: https://github.com/xcat2/xcat-process/blob/master/pics/4.jpg

Find out the failed reason by going through the case running log. 

**One tip:There is a timestamp behind every command, If need to find more information among** ``/var/log/message``, ``/var/log/xcat/cluster.log`` **and so on, this timestamp is useful to locate related logs.**
