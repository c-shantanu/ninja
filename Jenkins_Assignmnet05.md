"Assignment 5:
Topics Covered:  (User Authentication, User Authorization)

 Assignment on Authentication and Authorization
  Their is an organization which has 3 teams
  
            - Developer
            - Devops
            - Testing
            
 First you need to create 9 dummy jenkins jobs.Each job will print their jobname, build number.
   For Developer create 3 dummy jobs.In developer view
   
           job1:- dev-1
           job2:- dev-2
           job3:- dev-3
  For Testing create 3 dummy jobs. In testing view
  
           job1:- test-1
           job2:- test-2
           job3:- test-3
           
 For Devops create 3 dummy jobs. In devops view
 
           job1:- devops-1
           job2:- devops-2
           job3:- devops-3
                
        
 ** To create a 9 dummy jobs i used DSL Script  **
 
 job('test-01') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('test-02') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('test-03') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('devops-01') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('devops-02') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('devops-03') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('dev-01') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('dev-02') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}
job('dev-03') {
  steps {
    shell('echo -e "$JOB_NAME is running... \n Buid No.- $BUILD_NUMBER"')
  }
}


  ![image](https://github.com/parsugit/ansible_practice/assets/132131379/b325783f-7a0d-43d3-9dab-9e56e4a3da27)
  
  ![Screenshot 2023-10-26 at 11 21 20 PM](https://github.com/c-shantanu/ninja/assets/52127255/4932b027-ac8f-4529-9bcb-8f6375398e18)




 Users in each team: 
 developer: [ They can see only dev jobs, can build it, see workspace and configure it ]
 
      - developer-1 
      - developer-2 
                
  ![image](https://github.com/parsugit/ansible_practice/assets/132131379/c4fcc947-7430-4cff-8f79-e244c0f04f4c)
  

 testing: [ They can see all test jobs ,can build it, see workspace and can configure it, | They can also view dev jobs ]
 
          - testing-1 
          - testing-2 
                
   ![image](https://github.com/parsugit/ansible_practice/assets/132131379/8a79a786-e95f-4176-becd-7a67d170ccb3)

  devops:  [ They can see all devops jobs ,can build it, see workspace and can configure it, | They can also view dev and test jobs  ]
  
          - devops-1 
          - devops-2
                
  ![image](https://github.com/parsugit/ansible_practice/assets/132131379/61fd9681-e389-4dc1-b8b6-c40f42627f00)

  admin
  
         -  admin-1 [ It will have full access ]
                
  ![image](https://github.com/parsugit/ansible_practice/assets/132131379/14183c6c-0e68-4001-867c-5fd9f31fd222)

  See what Authorization strategy suits it and implement it.
  Also go through all authorization strategy
  Legacy mode
  Project Based
  Matrix Based
  Role-Based
        
  ![image](https://github.com/parsugit/ansible_practice/assets/132131379/a751ac93-1b1a-4881-96dd-a93c64fe1add)

  Point 2:-
  Enable SSO with Google"
