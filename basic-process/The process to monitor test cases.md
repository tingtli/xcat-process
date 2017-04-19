In order to improve our code quality and coverage of our automation test, we need to add or refine our test cases accordingly either for defects or for features.

To monitor the adding/refining test cases tasks:

* An task issue need to be created by the defect owner(always who fix this defect) to trace the adding/refining test cases tasks for a defect.

* As for implementing/refining/enhancing features, the FVT shall check with developer to make sure whether we need to add or refine test cases for the feature.
  
  * If not, don't need to create a test case task. 
  
  * If yes, the developer or me shall create a task issue to add or refine test cases for the specified feature. And this test case **shall be high priority** and **finished at the same sprint** with the feature.

* The task issue shall be put in `Backlog` pipeline and have `component:test` label set.

* The task shall be assigned `sprint1 or sprint2` lable, specific `Milestone` and `Estimate point` in sprint plan meeting. The `Estimate point` will be 1 by default.

* The title of the task shall like **add/refine test cases for issue xxxx: \<the digest of the issue xxx\>** or **add/refine test cases for feature xxxx**. 
    
* After applying a pull request, the creator of the pull request **shall add a comment** like `This task is finished with pull request xxx` in the task issue.
    
* The added test cased **must** be able to run with xcattest.
    
* For the pull request of adding/refining test cases for a defect, 

    pls **note** that:
 
    * the original defect number shall be referenced in its description.
      
    * The **issue number** in the **title and description** of the pull request **shall be** the original defect number that the test case is adding or refining for.
       **Shall Not be** the task issue number. 

    * Once the pull request is merged, the task issue can be move to close status. And for the original issue, if it had `test:testcase_requested` label marked, the label shall be replaced with `test:testcase_added`.
