# Configure AWS CLI with Access Keys

### Step 1: Install AWS CLI

- Install AWS Command Line Interface from [Here](https://aws.amazon.com/cli/)

- How to Use the AWS CLI: [Here](https://www.datacamp.com/tutorial/aws-cli-tutorial)

- Install using one script: [Here](https://github.com/mirakib/Linux-Automation-Scripts/blob/main/AWS/install_aws.ubuntu.sh)

**Or install manually:**

```sh
# Switch to superuser
sudo su -

# If you’re on Amazon Linux, to install the latest version of the AWS CLI, you must first uninstall the pre-installed yum version
yum remove awscli

# Download the AWS CLI zip file
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

# Install unzip
sudo apt install unzip

# Unzip the file
sudo unzip awscliv2.zip

# Run the installer
sudo ./aws/install

# Verify AWS CLI 
aws --version
```

**Check AWS CLI version:**

`aws --version` 

### Step 2: Configure AWS CLI with Access Keys

To use AWS CLI, you need to configure it with your AWS access keys (Access Key ID and Secret Access Key). If you don’t have these keys, you can create them in the AWS Management Console.

1. Create Access Keys in AWS Console:
- Go to the **IAM Console Dashboard**.
- In the left sidebar, click **Users**.
- Select the user you want to create access keys for.
- Go to the **Security credentials** tab.
- Under **Access keys**, click **Create access key**.
- Download the **Access Key ID** and **Secret Access Key**. Save them securely, as the Secret Access Key will not be shown again.

**Configure AWS CLI with Access Keys.**

```bash
aws configure
```

**Enter the following details:**
- **AWS Access Key ID**: Enter the Access Key ID from the previous step.
- **AWS Secret Access Key**: Enter the Secret Access Key from the previous step.
- **Default region name**: Enter the AWS region you want to use (e.g., us-west-2).
- **Default output format**: Enter the output format (e.g., json, text, or table).
  
### Step 3: Verify Configuration

Verify the setup by running a simple AWS CLI command to check your configuration.

```bash
aws s3 ls
```

---


# Connect to AWS Console Services Using boto3

## Prerequisites

- Python 3.x installed on your machine.
- An AWS account with the required permissions.
- AWS credentials configured on your local machine or environment.

## Install Required Python Packages

**Steps 1:** Install the `venv` module:\
`sudo apt install python3.10-venv`

**Steps 2:** Create boto3 Script\
**Create a Python script (e.g., app.py) and add the following code**

```py
import boto3

# Create a session without specifying credentials (uses the default profile)
session = boto3.Session(
    region_name='ap-south-1'
)

print(f"Connected to AWS region: {session.region_name}")

sts_client = session.client('sts')
identity = sts_client.get_caller_identity()

print(f"AWS Account ID: {identity['Account']}")
print(f"User ARN: {identity['Arn']}")
print(f"User ID: {identity['UserId']}")

# Create an S3 client to list buckets
s3_client = session.client('s3')
response = s3_client.list_buckets()

# Check if there are any S3 buckets and print them
if 'Buckets' in response:
    print("\nList of S3 Buckets:")
    for bucket in response['Buckets']:
        print(f"- {bucket['Name']}")
else:
    print("No S3 buckets found.")
```

**Steps 3:** Create a Virtual Environment: Navigate to your project directory and run:\
`python3 -m venv .venv`

**Steps 4:** Activate the Virtual Environment:\
`source .venv/bin/activate`

**Steps 5:** Install the boto3 library:\
`pip install boto3`

**Steps 6:** Run the Python script:\
`python3 app.py`

**Steps 7:** To exit from a virtual environment in Python.\
`deactivate`


## Additional Resources

- [Boto3 Documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)
- [AWS CLI Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)
