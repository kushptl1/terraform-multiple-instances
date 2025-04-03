Terraform Lab: Using Loops to Create Multiple EC2 Instances

Overview

This lab demonstrates how to use Terraform loops (count and for_each) to dynamically create multiple EC2 instances in AWS.


terraform init

terraform apply -auto-approve

Verify the Instances
aws ec2 describe-instances --query "Reservations[].Instances[].{ID:InstanceId, State:State.Name, Name:Tags[?Key=='Name'].Value|[0]}" --output table


terraform destroy -auto-approve
