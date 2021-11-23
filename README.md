# terraformForReact
Approach taken:
  -- Using Dockerfile, create the image for a container that can define the standard environment and also expose port 3000 as per the question need
  -- Using Amazon ECS, achieve the orchestration of the containers that are formed with above dockerfile
  -- Keep the track of container images and tags using Amazon ECS
  -- Achive the standerdization, scalability, tracking and resusability (Infrastructure as Code) using Terraform


This to be considered before the implementation:
  -- The user must have an AWS account with appropriate IAM policies attached
  -- If need terraform state files to be collaborated then a backend like S3 would also be needed (my code has skipped that part however)
  -- Need appropriate node package to be installed and added into the PATH variable
  -- Need docker to be installed
  -- Need terraform isntalled and also configured as per AWS CLI

Summary of the workflow:
  -- Step 1 - Git Clone the Application Repository.
  -- Step 2 - Write the dockerfile for the React based web application
  -- Step 3 - In order to push the built container imags, create repository on AWS ECR and then perform the push (docker push)
  -- Step 4 - In order to provide a platoform where the application can run, for the ECS cluster
  -- Step 5 - Once the cluster is fomed, the next step is to create the ECS task that can act as an execution unit
  -- Step 6 - After the creation of ECS task, the next logical step would be to form the ECS service
  -- Step 7 - At last, for even distribution of load and also keep resiliance agianst unexpected traffic surge, make the use of Elastic load balancer (AWS ELB)

