CICD pipeline 
Each stage of the CI/CD pipeline is structured as a logical unit in the delivery process. Each stage acts as a gate that vets a certain aspect of the code. As the code progresses through the pipeline, the assumption is that the quality of the code is higher in the later stages, because more aspects of it continue to be verified. 

Problems uncovered in an early stage stop the code from progressing through the pipeline. Results from the tests are immediately sent to the team, and all further builds and releases are stopped if software does not pass the stage.

  ![image](https://github.com/user-attachments/assets/2eb040f5-6ae1-443b-bb5d-90e8d429be54)

  
CodeCommit: For Source Code Management

CodeBuild: For building and testing our code in a serverless fashion

CodeDeploy: To deploy our code

CodePipeline: To streamline the CI/CD pipeline

Step-1
-Create repo in code commit

![Screenshot (1)](https://github.com/user-attachments/assets/d8be8dcb-412c-4405-a098-fd2cee8011bc)

Create folder on desktop and clone the repo here

-open the repo and paste the java project inside that
-->cd repo-->git add . -->git commit “m” -->git push-->

![Screenshot (3)](https://github.com/user-attachments/assets/ec720ffa-1e26-4ab8-ba59-254a25824ee8)

Step-2
-->search elastic bean stalk in services-->create application-->give app name-->myjavaapp-->give environment namedomain name as myjavaapp(check availability)-->choose platform as tomcat-->choose platform number latest(tomcat) -->
![Screenshot (5)](https://github.com/user-attachments/assets/c4c75c3c-58e1-4299-a0a6-aef67daae9e4)



next-->in service access choose createAnd new service role-->select key pair as linux key pair-->select ec2-to-code deploy under Ec2 instance profile-->next-->select Default vpc-->tick the activated checkbox-->tick all the availability zone-->NEXT-->Under EC2 Security group select Linux security group-->remove the default instance type and select t2.micro-->(Note-->if t2.micro is not available then select t3.micro)-->NEXT-->select enhanced in monitoring
-->under cloudwatch custom matrics-->select ‘instance health’--> under cloudwatch Custom matrices select Application RequestTotal-->next-->submit-->
Step-3
-->Search code pipeline-->Create pipeline-->provide name-->Next-->select AWScodecommit as source-->select repository name and branch name as master

![Screenshot (8)](https://github.com/user-attachments/assets/2a2e571c-9e74-4c0b-93bd-e20ccb6d8b42)

-->Next-->Under build provider AWS code build-->click on create project-->Under new opened window provide the project name-->OS as linux-->Under build spec select use build spec file-->Untick the cloudwatch logs-->continue to code pipeline-->NEXT
-->Under Deploy provide-->select AWS elastic bean stalk-->select application name and environment name

![Screenshot (10)](https://github.com/user-attachments/assets/9e257160-374d-444d-ae48-8fed42ea5c70)

-->next--> create pipeline

![Screenshot (11)](https://github.com/user-attachments/assets/953fb1a9-0de8-43a8-8408-1b0505687a40)
![Screenshot (12)](https://github.com/user-attachments/assets/eafc944f-0c7e-4651-8acf-2fe836f838a7)


-->Now search ec2 under services and copy paste the public IP of instance
-->Edit the index file in the remote repo-->go in repo name/src/main/webapp/index.jsp
 -->select/edit and change something -->provide author name and email address and message-->commit changes--> after success refresh the index page-->now date will be updated-->
![Screenshot (16)](https://github.com/user-attachments/assets/2234c9e1-6c75-401a-8c95-3f6bb8ca7338)








      


