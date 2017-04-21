
This document is structured based on priority

## P1

* PGS Alpha ==> 2.13.6

* PGS GA ==> 2.13.9

* ~~rcons(For OpenBMC) through ssh~~

* ~~rpower(For OpenBMC)~~

* rspconfig 
    * ip/netmask/gateway/vlan/snmp/alert(For OpenBMC) ==> 2.13.4 
    * useradd/userch/userrm/userls(For OpenBMC) ==> 2.13.5

* rinv (For OpenBMC)==> 2.13.4

* rsetboot (For OpenBMC)==> 2.13.4

* hardware discovery include(genesis-base) verification ==> 2.13.4/2.13.5  
Need to verify whether latest genesis-base can work on WSP server, if not, will be high priority issue.

* bmcdiscovery (For OpenBMC)==> 2.13.4

* rflash (For OpenBMC)==> 2.13.6    

* rvitals (For OpenBMC)==> 2.13.5 

* reventlog (For OpenBMC)==> 2.13.5

* configure BMC in band(bmcsetup) verification  
It was known that the ipmi command such as user configuration won't be supported on OpenBMC, we shall call RestFul interface.
    * Modify bmcsetup to not run user configuration related function through ipmi-inband ==> 2.13.4
    * Call ``respconfig userXXX`` through RESTful interface to configure user account. ==> 2.13.5

* P9 ZZ verification ==> 2.13.6  
Switch to OPAL mode and operated through ipmi, used as MN in CORAL cluster

* switch based discovery  
    * Mid and Edge switch discovery and configuration ==> 2.13.5
    * SN and CN discovery and deployment
        * SN based on Mid switch ==> 2.13.5
        * CN based on Edge switch ==> 2.13.5

* Mellanox Switch
    * Discovery and Configuration End to End verification ==> 2.13.4
    * IB - OFED  (Check with Jim Still about the release date and version) ==> 2.13.6 

* performance enhancement
    * makedhcp,nodeset enhancement ==> 2.13.4
    * makedns, \*def command ==> 2.13.5
    * xdsh,updatenode ==> 2.13.5
    * hardware control commands: rpower, rsetboot... ==> 2.13.6
    * service xcatd start/restart on MN and SN ==> 2.13.5?

* A document or design for the whole progress of setup CRL cluster. ==> 2.13.4-2.13.6

## P2

* lsslp -s “OPENBMC”?  ==> TBD

* Cumulus Linux OS
    * Cumulus ZTP (https://github.com/xcat2/xcat-core/issues/2662) ==> TBD 
    * Cumulus Autodiscovery (https://github.com/xcat2/xcat-core/issues/2661) ==> TBD

* GPU: Cuda9 verification==> 2.13.6

* iPDU
    * PDU support in rvitals (GitHub comment) ==> TBD
    * iPDU verification on new PDU in Railhawk Frame ==> TBD

* RHV 4.1 (test driven) ==> 2.13.4

* RH7.4 ==> 2.13.6
    
* RH8  ==> 2.13.9

* enhance xcatprobe to do health check within CORAL cluster?

## P3

* New xCAT prototype with Python ==> TBD
