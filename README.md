# Koustubh-Terraform

Launch a new EC2

	2. SSH to server using terminal.
	3. Got to google, click on Install Terraform
	4. 

1

2

Follow all installation steps given

Ensure that your system is up to date and that you have installed the gnupg and software-properties-common packages. You will use these packages to verify HashiCorp's GPG signature and install HashiCorp's Debian package repository.
$ sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
Install HashiCorp's GPG key.
$ wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
Verify the GPG key's fingerprint.
$ gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
The gpg command reports the key fingerprint:
/usr/share/keyrings/hashicorp-archive-keyring.gpg
-------------------------------------------------
pub   rsa4096 XXXX-XX-XX [SC]
AAAA AAAA AAAA AAAA
uid         [ unknown] HashiCorp Security (HashiCorp Package Signing) <security+packaging@hashicorp.com>
sub   rsa4096 XXXX-XX-XX [E]
Add the official HashiCorp repository to your system.
$ echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
Update apt to download the package information from the HashiCorp repository.
$ sudo apt update
Install Terraform from the new repository.
$ sudo apt-get install terraform
Terraform versions and compatibility
HashiCorp regularly releases new versions of Terraform with new features and bug fixes. HashiCorp maintains compatibility between Terraform versions, so a Terraform configuration written for one version of Terraform should continue to work with any later minor version update. Refer to the Terraform compatibility promise for more details.
Verify the Installation
Verify that the installation worked by opening a new terminal session and listing Terraform's available subcommands.
$ terraform -help
Usage: terraform [global options] <subcommand> [args]
The available commands for execution are listed below.
The primary workflow commands are given first, followed by
less common or more advanced commands.
Main commands:
##...
Add -help to any Terraform command to learn more about what it does and available options.
$ terraform plan -help
Enable tab completion
If you use either Bash or Zsh as your command line shell, you can enable tab completion for Terraform commands. To enable autocomplete, first ensure that a configuration file exists for your chosen shell.
BashZsh
$ touch ~/.bashrc
Then install the autocomplete package.
$ terraform -install-autocomplete
After installing autocomplete support, you will need to restart your shell to enable it.
INSHORT HISTROY:
   16 sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
   17  wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
   18  gpg --no-default-keyring --keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg --fingerprint
   19  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
   20  sudo apt update
   21  sudo apt-get install terraform
   22  terraform -help
   23  terraform plan -help
   24  touch ~/.bashrc
   25  terraform -install-autocomplete





Click on Documentation



Copy this basic template to launch instance.
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

# Configure the AWS Provider
provider "aws" {
  region = "us-east-1"
}

# Create a VPC
resource "aws_vpc" "example" {
  cidr_block = "10.0.0.0/16"
}

Now here we want to launch aws-ec2. So let's remove VPC block. 


Copy EMI from EC2, paste in above block infront of ami.







Copy region and insert into script



3

1

   2

Save it.

Then





Now this error you will see? Why
Because without credential AWS will not accept request to perform operations. So we need to give credentials to terraform.
There are different ways to give credentials, let's use one of them "through file."



Through file means we are using 3rd one,

SO let's create first access key. 
Go to aws page. 


On profile --> go to Security Credentials


Create access key


Download it, Save it! For now you can copy from here and paste in main.tf file, lets do this…


Save it, and agaain… 








From AMI of Terraform Server we successfully created MyEC2byTerraform  named server, which automatically created! For now it will automatically take default SecurityGroup.
If you try to connect this instance, it will show error
So got to it's Security group and add SSH 22 Port, then connect, it will connect.

..<img width="1385" height="12472" alt="image" src="https://github.com/user-attachments/assets/997c35a4-01d3-44df-b574-a8e867c2d0eb" />
