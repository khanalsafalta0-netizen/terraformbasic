# Terraform Basic Setup

## Project Structure

```bash
terraformbasic/
├── .env
├── README.md
└── terraform_1.15.4_linux_amd64.zip
```

---

# Prerequisites

- Linux / Ubuntu System
- AWS Account
- Internet Connection
- `wget` and `unzip` installed

---

# Step 1: Download Terraform Binary

Run the following command to download Terraform:

```bash
wget -c https://releases.hashicorp.com/terraform/1.15.4/terraform_1.15.4_linux_amd64.zip
```

---

# Step 2: Unzip Terraform Binary

Extract the downloaded zip file:

```bash
unzip terraform_1.15.4_linux_amd64.zip
```

---

# Step 3: Move Terraform Binary to System Path

Move Terraform binary to `/usr/local/bin`:

```bash
sudo mv terraform /usr/local/bin
```

---

# Step 4: Verify Terraform Installation

Check Terraform version:

```bash
terraform version
```

Expected Output:

```bash
Terraform v1.15.4
```

---

# Step 5: Create AWS Environment File

Create a `.env` file:

```bash
touch .env
```

Add the following credentials inside `.env`:

```bash
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_SESSION_TOKEN=""
export AWS_REGION=""
```

Example:

```bash
export AWS_ACCESS_KEY_ID="AKIAXXXXXXXXX"
export AWS_SECRET_ACCESS_KEY="XXXXXXXXXXXXXXXX"
export AWS_SESSION_TOKEN="XXXXXXXXXXXXXXXX"
export AWS_REGION="us-east-1"
```

---

# Step 6: Export Environment Variables

Load the `.env` file:

```bash
source .env
```

---

# Step 7: Verify AWS Variables

Check whether variables are loaded:

```bash
echo $AWS_ACCESS_KEY_ID
echo $AWS_REGION
```

---

# Useful Terraform Commands

## Initialize Terraform

```bash
terraform init
```

## Validate Terraform Configuration

```bash
terraform validate
```

## Preview Infrastructure Changes

```bash
terraform plan
```

## Apply Infrastructure

```bash
terraform apply
```

## Destroy Infrastructure

```bash
terraform destroy
```

---

# Security Best Practices

- Never push `.env` file to GitHub.
- Add `.env` to `.gitignore`.
- Rotate AWS credentials regularly.
- Use IAM roles whenever possible.

Create `.gitignore`:

```bash
touch .gitignore
```

Add the following:

```bash
.env
*.tfstate
*.tfstate.backup
```

---

# Author

Safalta Khanal