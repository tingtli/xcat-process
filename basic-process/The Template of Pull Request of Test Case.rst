* The title of new pull request ::

    Add/Refine test case for issue <issue number> : <issue digest>
   
  or ::

        Add/Refine test case for feature <pull request number> : <feature digest>
    
    
* The content of post box ::

    Add/Refine N cases in this pull request.
    This/These case(s) is/are added/refined for issue#xxxx / feature#xxxx.

    [Case index]
    Case Name: xxxxx
    description: introduce the purpose of current case,  which scenario this cases is valid.  For example, For "all xcat verision", ">2.13.3", "<=2.12.3", ">2.10.1 and <=2.12.4".  If need specific hardware configuration, for example specific hardware device or specific network setting. 
    attribute:  All the attribute needed to be configured in xcattest config file. If there are more than one attributes, using semicolon to separate. There is a simple description for each attribute. For example: $$a-description;$$b-description;$$c-description

  An example: ::
 
      Refine 2 cases in this pull request
      These 2 cases are refined for issue #1234

      [case 1]
      Case Name: rpower_stat
      description: Try to verify the rpower command with stat option. Valid for all xcat version.
      attribute: $$CN-The operation object of rpower command.

      [case 2]
      Case Name: rpower_off
      description: Try to verify the rpower command with off option. Valid for all xcat version.
      attribute: $$CN-The operation object of rpower command.


**[Note]**:
**After pull request being merged, must add a comment both in the original issue/feature and the work tracking issue to highlight this issue/feature/task was added test case by this pull request #xxxx.**



