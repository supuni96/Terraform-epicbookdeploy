# Terraform-epicbookdeploy
Deploy epicbook application using terraform
Terraform Commands
1️⃣ Initialize Project
terraform init


Initializes the working directory, downloads provider plugins (AzureRM), and sets up modules.

2️⃣ Validate Configuration
terraform validate


Checks that your Terraform code syntax is correct before applying.

3️⃣ Format Code
terraform fmt


Formats all .tf files for clean and consistent structure.

4️⃣ Preview Infrastructure
terraform plan -var-file="env/dev.tfvars"


Creates an execution plan showing what will be created for the dev environment.

5️⃣ Apply Changes (Deploy)
terraform apply -var-file="env/dev.tfvars" -auto-approve


Actually creates the resources in Azure (VM, MySQL server, network, etc.).

6️⃣ Destroy Dev Environment
terraform destroy -var-file="env/dev.tfvars" -auto-approve


Deletes all resources created for the dev environment to avoid extra costs.

☁️ Azure & Linux Commands
7️⃣ Connect to Azure VM
ssh azureuser@<public-ip-of-vm>


Connect to your EpicBook VM instance.

8️⃣ Check MySQL Connection from VM
mysql -h <mysql-server-name>.mysql.database.azure.com -u epic_admin -p


Verifies that your application VM can reach the Azure MySQL database.

9️⃣ Run Application
node server.js


Starts the backend Node.js application for EpicBook!

🔟 Health Check (From VM or Local)
curl -i http://<public-ip>:8080/api/health


Tests that your EpicBook backend API is up and running.

🧹 Optional Cleanup
sudo lsof -i :8080
sudo kill -9 <PID>
