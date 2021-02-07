# Text between `` can be changes
# First create IAM policies
    Check policy.txt file, add these policies to IAM policy in json format.
# crete role for eks and copy the ARN, eks with use case, eks and eks-cluster
        AWSserviceRole,clustereksrole
# Add users and attach policy
    1. `ClusterAdmin` with attached policy, AdminEKS,AdminCF, AeksCluster, AeksService Policy add both programatic and
        console access, create password and download csv file for both.
    2. `ClusterUser` with Admineks Policy and programatic access. Logout as root user, login as ClusterAdmin IAMuser.
# Create VPC using cloudformation in us-west-2 region.
    Go to CloudFormation service, create stack standard, change region, add url 
    S3 template https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2018-08-30/amazon-eks-vpc-sample.yaml
    Leave rest default and create VPC, Wait for create and focus on output window
# Add file and install modules
    Create the hostname.yaml file in the , and check kubectl_install.md file for further commands
    After moving check aws in bash
# Create Cluster, Name:`ClassCluster`, Add clustereksrole
    Go to terminal, 
        aws configure --profile=clusterAdmin
        export AWS_PROFILE=clusterAdmin
        aws eks update-kubeconfig --name `classCluster`
    Verify, kubectl get pods
            kubectl get nodes 
            kubectl apply -f hostname.yaml