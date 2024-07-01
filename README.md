# sample-list-of-amazon-ec2-S3-lambda-iam-users
here is script to list of list of amazon ec2, S3, lambda, iam users


#!/bin/bash


# The below-given data is Metadate whenever we write a script its much to write metadata so that we can easily find details of the script
#########################
# Author: Bharath
# date: 27th June
#
# Version: V1
#
# This script will report the aws resources usage
#########################

#set cmd to put the script into debug mode
set -x

# Aws s3
# Aws ec2
# aws lambda
# aws iam users

# echo cmd is to print what we give as input like printf
# >> Resource tracker cmd  is to be used to save the o/p in file mode
# list s3 buckets
echo "print list of s3 bucket"
aws s3 ls >> resource tracker


# | pipe cmd sends o/p from 1st cmd to 2nd cmd like transfer o/p
# jq cmd is used for Json and it gets the information that we need exactly from json
# list ec2 instance
echo "print list ec2 instances"
aws ec2 describe-instances | jq '.Reservations[].Instances[].InstanceId'


# list lambda
echo "list aws lambda"
aws lambda list-functions


# list iam users
echo "print iam user"
aws iam list-users | jq '.Users[].UserId'
                                            
