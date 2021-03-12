# tut_packer
Packer and AWS CodeBuild image building tutorial.
https://aws.amazon.com/blogs/devops/how-to-create-an-ami-builder-with-aws-codebuild-and-hashicorp-packer/

Notes:
1. Time formatting in the legacy JSON template format using function isotime with the "magic" date "2006-01-02 15:04:05".
   An example is the creatinDate tag for the AMI image in the template file.
2. timestamp function UNIX format
3. Variables from the runtime environment can be passed to packer: 
- export time_stamp=`date "+%Y%m%d"` - assigning time_stamp variable with current date in the pre_build module
- packer build -var time_stamp=${time_stamp} - executing paker with -var parametr. the time_stamp variable needs to be defined in the packer template yaml file with null value.
