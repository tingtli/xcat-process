
After getting daily regression report from ``xCAT Jenkins Mail Bot`` every day,  can find 2 tables in the top of the mail to describe the over all results of last day regression and the failed cases for each project. 

Hover the mouse on the project for a while in these tables, can get project basic information. The project name is drawn red line underneath.



Mount ``10.0.0.122:/gpfs/cnfs01/data/xcat/jk/log`` on any directory in your own server, then can access daily ragression detailed logs under this directory. ::

    mount 10.0.0.122:/gpfs/cnfs01/data/xcat/jk/log <your path>
    
Find the logs of specific project depending on project name under ``your path``. Take project ``rhels7.3-ppc64le-2.13.3-58`` shown above for example,  its logs were saved under ``/<your path>/rhels7.3-ppc64le-2.13.3/58``.


The files under ``/<your path>/rhels7.3-ppc64le-2.13.3/58`` are looked like below:

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
