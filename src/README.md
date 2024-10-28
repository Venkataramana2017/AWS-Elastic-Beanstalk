

Before deployment create key pair and use name of that key pair in variables file. Also you have to existing SNS Topic for your alarm notification and Route53 Public Hosted Zone for your domain.


Change these variables in the terraform.tfvars file with your own before the deployment.


region = "us-east-1"

domain_name = "example.com"

app_tags = "Example"

application_name = "Example-App"

vpc_id = "vpc-ee2325320"

ec2_subnets = "subnet-d1c325ab"

elb_subnets = ["subnet-d1c325ab","subnet-d1c565ab"]

instance_type = "t3.micro"

disk_size = "20"

keypair = "example"

sshrestrict="12.34.56.78/32"

alarm_sns_topic = "arn:aws:sns:us-east-1:123456788900:TOPIC"


When everything is ready you can deploy with these 4 commands.

Deployment
terraform init
terraform validate
terraform plan
terraform apply
