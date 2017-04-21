
* Must include "description/attribute" sections. 

  * ``description``: introduce the purpose of current case,  which scenario this cases is valid.  For example, For "all xcat verision", ">2.13.3", "<=2.12.3", ">2.10.1 and <=2.12.4".  If need specific hardware configuration, for example specific hardware device or specific network setting. 

  * ``attribute``: All the attribute needed to be configured in xcattest config file. If there are more than one attributes, using semicolon to separate. There is a simple description for each attribute. For example: $$a-description;$$b-description;$$c-description

* Must clean up all the bogus information and recover all original environment configuration before case exit.

* Must do unit test before pulling request. If it will be a daily regression test case, it must be tested in automation development environment before pulling request. 

* Case name must be unique. (There were cases had the same name but with multiple implementation in the history, will refine this part cases in the future.)

* The rule of case naming

  * The case for command  ::
  
    <cmd>_<option>_<purpose_digest>
    
    ``cmd`` means the commands which the case belongs to
    
    ``option`` means which option we tested
    
    ``purpose_digest`` using simple word to highlight the test purpose
    
                   
  * The case for process  ::
  
    <process key word>_<purpose_digest>
              
              
* If need to handle multiple platform in one case, make the code clearly.

