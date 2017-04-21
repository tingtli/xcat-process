
This document is structured based on priority

## P1

* PGS Alpha ==> 2.13.6(Aug 11，2017)

* PGS GA ==> 2.13.9(Dec 22, 2017)

* ~~rcons(For OpenBMC) through ssh~~

* ~~rpower(For OpenBMC)~~

* rspconfig 
    * ip/netmask/gateway(For OpenBMC) ==> 2.13.4(May 19, 2017)
    * vlan/snmp/alert(For OpenBMC) ==> 2.13.5(Jun 30, 2017)
    * useradd/userch/userrm/userls(For OpenBMC) ==> 2.13.5(Jun 30, 2017)

* rinv (For OpenBMC)==> 2.13.4(May 19, 2017)

* rsetboot (For OpenBMC)==> 2.13.4(May 19, 2017)

* hardware discovery include(genesis-base) verification
    * verify whether latest genesis-base can work on WSP server ==> 2.13.4(May 19, 2017)
    * If not, try latest Fedora on WSP server and rebuild genesis-base ==> 2.13.5 (Jun 30, 2017)

* bmcdiscover (For OpenBMC)==> 2.13.4(May 19, 2017)

* rflash (For OpenBMC)==> 2.13.6(Aug 11, 2017)

* rvitals (For OpenBMC)==> 2.13.5(Jun 30, 2017)

* reventlog (For OpenBMC)==> 2.13.5(Jun 30, 2017)

* configure BMC in band(bmcsetup) verification  
It was known that the ipmi command such as user configuration won't be supported on OpenBMC, we shall call RestFul interface.
    * Modify bmcsetup to not run user configuration related function through ipmi-inband ==> 2.13.4
    * Call ``respconfig userXXX`` through RESTful interface to configure user account. ==> 2.13.5

* WSP EUH server E2E verification==> 2.13.5(Jun 30, 2017)  
    * hardware discovery: bmcdiscover, rspconfig, genesis-base + bmcsetup
    * hardware control: rpower, rsetboot
    * PGS diskless/diskful deployment

* GPU: Cuda9 verification==> 2.13.6(Aug 11, 2017)

* P9 ZZ verification ==> 2.13.6(Aug 11, 2017)
Switch to OPAL mode and operated through ipmi, used as MN in CORAL cluster

* switch based discovery==> 2.13.5(Jun 30, 2017) 
    * Mid and Edge switch discovery and configuration
    * SN and CN discovery and deployment
        * SN based on Mid switch
        * CN based on Edge switch

* Mellanox Switch
    * Discovery and Configuration End to End verification ==> 2.13.4(May 19, 2017)
    * IB - OFED  (Check with Jim Still about the release date and version) ==> 2.13.6 (Aug 11, 2017)

* performance enhancement
    * makedhcp,nodeset enhancement ==> 2.13.4(May 19, 2017)
    * makedns, \*def command ==> 2.13.5(Jun 30, 2017)
    * xdsh,updatenode ==> 2.13.5(Jun 30, 2017)
    * hardware control commands: rpower, rsetboot... ==> 2.13.6(Aug 11, 2017)
    * service xcatd start/restart on MN and SN ==> 2.13.5(Jun 30, 2017)?

* A document or design for the whole progress of setup CRL cluster.==> TBD
   * service node poll ==> TBD

## P2

* lsslp -s “OPENBMC”?  ==> TBD

* Cumulus Linux OS
    * Cumulus ZTP (https://github.com/xcat2/xcat-core/issues/2662) ==> TBD 
    * Cumulus Autodiscovery (https://github.com/xcat2/xcat-core/issues/2661) ==> TBD

* iPDU
    * PDU support in rvitals (GitHub comment) ==> TBD
    * iPDU verification on new PDU in Railhawk Frame ==> TBD

* RHV 4.1 (test driven) ==> 2.13.4(May 19, 2017)

* RH7.4 ==> 2.13.6(Aug 11, 2017)
    
* RH8  ==> 2.13.9(Dec 22, 2017)

* enhance xcatprobe to do health check within CORAL cluster==> TBD

## P3

* New xCAT prototype with Python ==> TBD
