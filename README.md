
# Solution diagram
![alt text](https://aws-jccastro-bucket.s3.amazonaws.com/Solution_Diagram+(1).jpg)

## Solution steps

- I used docker hub as a container repository for the builds that Jenkins create.
- I created a new repository with the project that you gave me and made some changes, for example, the alpine image isn't working with the original version, I updated it to alpine 3.11.11.
- I created a cloudformation file to deploy all the solutions.
- Once the cloudformation been deployed, check the output section on AWS Cloudformation Service and check the public IP of the instance to access Jenkins, it will run on a docker container and its initial config is in an S3 bucket and the admin console is will be accessed through port 8080 as the diagram indicate.
- After that, exist a job called timeoff-management that will build a solution and deploy the application in a container that will be accessed through port 80.
- Every 5 minutes Jenkins will check the github repository to validate if exist any change with the code, if this is correct, automatically a build will start and put on production the new version.
- All the builds will save in the Docker Hub repository.