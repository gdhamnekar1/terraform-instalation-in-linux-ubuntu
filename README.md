this is link>> https://developer.hashicorp.com/terraform/cli/v1.2.x/install/apt


1.Download the signing key to a new keyring.

wget -O- https://apt.releases.hashicorp.com/gpg | \
    gpg --dearmor | \
    sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg


2.Verify the key's fingerprint.

gpg --no-default-keyring \
    --keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
    --fingerprint


3. Add the official HashiCorp repository to your system. The lsb_release -cs command finds the distribution release codename for your current system, such as buster, groovy, or sid.

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
    https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
    sudo tee /etc/apt/sources.list.d/hashicorp.list

4.Download the package information from HashiCorp.

sudo apt update

5. Install Terraform from the new repository.

 sudo apt install terraform

6. check version
terraform --version

ans:- Terraform v1.4.2
on linux_amd64

7. location chech
which terraform




