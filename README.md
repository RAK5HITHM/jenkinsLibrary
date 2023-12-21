**This is a Jenkins Shared Libraries**

**What is Jenkins Shared Libraries?**

 Jenkins Shared Libraries allow you to write reusable code that can be shared across multiple Jenkins pipelines. This helps in maintaining consistent functionality and reducing duplication of code. Shared Libraries are particularly useful when you have common functionalities, custom steps, or complex logic that you want to reuse across various pipelines.

**Features of Jenkins Shared Libraries**

 1.Reusable Code<br>
 2.Organization and Structuring<br>
 3.Custom Steps and Functions<br>
 4.Version Contro<br>
 5.Centralized Maintenance<br>
 6.Secure Access Control<br>
 7.Parameterized Functions<br>
 8.Documentation and Usage Guidelines<br>
 9.Integration with Pipeline DSL<br>

 **Basic structure of Jenkins Shared Libraries**
 
  MySharedLibrary/             # Root directory of the Shared Library
  vars/                      # Directory containing Groovy files defining custom steps or functions
    myFunction.groovy        # Example Groovy file defining a custom function
  src/                       # (Optional) Directory for additional source code or utility classes
  resources/                 # (Optional) Directory for non-Groovy resources
  README.md                  # Documentation or usage guidelines for the Shared Library
  vars/                      # Directory containing Groovy files defining custom steps or functions
    myFunction.groovy        # Example Groovy file defining a custom function
  src/                       # (Optional) Directory for additional source code or utility classes
  resources/                 # (Optional) Directory for non-Groovy resources
  Jenkinsfile                # (Optional) Jenkinsfile for Pipeline Unit testing

**How to configure Jenkins Controller to access/integrate shared libraries**

 1.Open Jenkins and navigate to the Jenkins dashboard.<br>
 2.Click on Manage Jenkins on the left-hand side.<br>
 3.Select Configure System.<br>
 4.Scroll down to the Global Pipeline Libraries section.<br>
 5.Add the Shared Library<br>
 6.Always remember the name given to the shared library.<br>

**How to use the shared library in the pipeline**

 @Library('MySharedLibrary') _  #MySharedLibrary is the name given to the shared library in the Global Pipeline Libraries section.

pipeline {
    agent any
    
    stages {
        stage('Example') {
            steps {
                // Call a function from the Shared Library
                myFunction() // Assuming 'myFunction.groovy' is in the library
            }
        }
    }
}


