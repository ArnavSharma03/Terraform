# Terraform

# 30-Day Infrastructure as Code (IaC) Challenge
## Days 1-5: The Fundamentals of Terraform & CloudFormation

### Day 1: Introduction to IaC & Provider Setup
- **Concept:** Moving from manual console clicks to version-controlled, repeatable code.
- **Terraform:** Initialized using `provider "aws"`. Requires `terraform init` to download plugins.
- **CloudFormation:** AWS-native. Uses `AWSTemplateFormatVersion` and `Description`.
- **Note:** TF is multi-cloud; CFN is AWS-specific.

### Day 2: S3 Storage (The "Hello World")
- **Concept:** Object Storage provisioning.
- **Terraform:** Created `aws_s3_bucket`. Tracks real-world state in `terraform.tfstate`.
- **CloudFormation:** Created `AWS::S3::Bucket`. Managed via AWS Stacks.
- **Note:** S3 bucket names must be globally unique.

### Day 3: Variables & Parameters
- **Concept:** Abstracting values to make templates reusable and dynamic.
- **Terraform:** Used `variable {}` blocks and referenced them via `var.variable_name`.
- **CloudFormation:** Used `Parameters:` section and referenced via `!Ref` or `!Sub`.
- **Note:** Always `.gitignore` sensitive variable files (`.tfvars`).

### Day 4: IAM Roles & Security
- **Concept:** Identity and Access Management (Least Privilege Principle).
- **Terraform:** Used `aws_iam_role` with `jsonencode` for the trust policy.
- **CloudFormation:** Used `AWS::IAM::Role` with YAML-defined policy documents.
- **Note:** The "AssumeRolePolicy" allows a service (like EC2) to take on a role.

### Day 5: Virtual Private Cloud (VPC)
- **Concept:** Isolated network foundations.
- **Terraform:** Defined `aws_vpc` with `cidr_block = "10.0.0.0/16"`.
- **CloudFormation:** Defined `AWS::EC2::VPC`.
- **Note:** Enabled `DNS Hostnames` to allow instances to be reachable by name.

---

## 30-Line Master Summary for Commits
1. Moving from manual console clicks to version-controlled code.
2. Terraform (TF): Open-source, multi-cloud, uses HCL language.
3. CloudFormation (CFN): AWS-native service, uses YAML or JSON.
4. Day 1: Initialized TF providers and CFN headers.
5. TF Logic: `init` downloads plugins; `plan` previews; `apply` executes.
6. CFN Logic: Deploys via "Stacks" in the AWS Management Console.
7. Day 2: Provisioned S3 buckets in both tools.
8. Naming: S3 bucket names must be globally unique.
9. Day 3: Abstracted hardcoded values for reusability.
10. TF Var: Defined in variable blocks; referenced via `var.name`.
11. CFN Param: Defined in Parameters; referenced via `!Ref`.
12. State File: TF stores mapping in `terraform.tfstate`.
13. Security: Always `.gitignore` the state file.
14. Day 4: Implemented IAM roles using Least Privilege.
15. Trust Policy: Allows services to act on your behalf.
16. Readability: TF uses `jsonencode` for clean IAM policies.
17. Day 5: Built the foundational VPC network.
18. CIDR Blocks: Used `10.0.0.0/16` for the private IP range.
19. DNS Support: Enabled hostnames for internal resolution.
20. Dependency: Networking must exist before compute.
21. TF Syntax: `resource "type" "local_name" { ... }`.
22. CFN Syntax: `Resources: LogicalID: Type: ...`.
23. Declarative Power: We describe the end state, tools handle the "how".
24. Immutability: Resources are often replaced, not just updated.
25. Drift: CFN has built-in detection; TF uses `plan` to check.
26. Modularity: TF excels at re-using code through Modules.
27. Intrinsic Functions: CFN uses `!GetAtt` and `!Join`.
28. Provisioners: TF can run scripts locally during creation.
29. Rollbacks: CFN rolls back on failure; TF stays at failure point.
30. Goal: Ensuring zero-downtime, scalable cloud architecture.
