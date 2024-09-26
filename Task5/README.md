# Automated Deployment of EC2 Instance Using Terraform and GitHub Actions

Explanation:

Trigger: The workflow runs on every push to the main branch. Jobs: Checkout Code: Retrieves the repository's code. Set up Terraform: Prepares the environment for Terraform commands. Terraform Init: Initializes Terraform. Terraform Plan: Creates an execution plan. Terraform Apply: Applies the infrastructure changes. Get EC2 Public IP: Retrieves the public IP of the deployed EC2 instance. Wait for EC2 to be Ready: Pauses the workflow to allow the instance to initialize. Add SSH Key: Adds the SSH private key to the SSH agent for subsequent connections. Test SSH Connection: Verifies SSH connectivity to the EC2 instance. Environment Variables: AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY: Used by Terraform to authenticate with AWS. TF_VAR_ec2_private_key: Passes the EC2 SSH private key to Terraform as a variable. 5. Commit and Push Changes Add all the created files to your Git repository:

git add main.tf install.sh .github/workflows/deploy.yml git commit -m "Automated EC2 deployment with Terraform and GitHub Actions" git push origin main Verification After pushing the changes:

Monitor the Workflow: Go to the Actions tab in your GitHub repository to observe the workflow execution. Retrieve the Public IP Address: The workflow outputs the EC2 instance's public IP. Alternatively, obtain the IP from the AWS Management Console.
