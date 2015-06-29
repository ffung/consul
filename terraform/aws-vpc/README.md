## Running the AWS templates to set up a Consul cluster on a specific VPC (e.g. non Default-VPC)

The platform variable defines the target OS, default is ubuntu, rhel6 is an option

For AWS provider, set up your AWS environment as outlined in https://www.terraform.io/docs/providers/aws/index.html

To set up ubuntu based, run like below, replace key_name, key_path vpc_id and subnet_id with actual values

terraform apply -var 'key_name=consul' -var 'key_path=/Users/xyz/consul.pem' -var 'vpc_id=<vpc_id>' -var 'subnet_id=<subnet_id>'

or 

terraform apply -var 'key_name=consul' -var 'key_path=/Users/xyz/consul.pem' -var 'platform=ubuntu' -var 'vpc_id=<vpc_id>' -var 'subnet_id=<subnet_id>'

To run rhel6, run like below

terraform apply -var 'key_name=consul' -var 'key_path=/Users/xyz/consul.pem' -var 'platform=rhel6' -var 'vpc_id=<vpc_id>' -var 'subnet_id=<subnet_id>'

For centos6 platform, for the default AMI, you need to accept the AWS market place terms and conditions. When you launch first time, you will get an error with an URL to accept the terms and conditions.
