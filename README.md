I am performing this experiment in an  ec2 instance

To install terraform in linux
create a bash script

Follow this steps:
sudo nano a.sh

wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform -y

Now ctrl +s and press ctrl+x to save and exit

Now run the script using
bash a.sh

Now we have to generate access key and secret access key

go to IAM > MFA> Security policies> you will find the option to generate access key and secret access key . Copy and paste it in the main. tf file

Now write a file using
sudo nano main. tf

Refer to the main. tf file in the same repo for the file contents

Once the file is created
run the commands
terraform init
terraform plan
terraform apply

After this go and verify if the instance is created in that particular region or not.
