---
title: Terraform Interview Questions & Answers
description: A comprehensive collection of 200 Terraform interview Q&As with examples.
---

# Terraform Interview Questions & Answers

Welcome to the ultimate Terraform interview preparation guide. This collection includes **200 Terraform Q&A** to help you ace your interviews and strengthen your infrastructure-as-code knowledge.

---

## Table of Contents

```toc
```

---

### 1. What is Terraform?
Terraform is an open-source infrastructure as code (IaC) tool developed by HashiCorp that allows users to define and provision data center infrastructure using a high-level configuration language called HCL (HashiCorp Configuration Language) or JSON.

**Example:**
```hcl
provider "aws" {
  region = "us-west-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```

### 2. What are the main features of Terraform?
- Infrastructure as Code (IaC)
- Execution Plans
- Resource Graphs
- Change Automation
- State Management

**Example:**
```hcl
terraform {
  backend "s3" {
    bucket = "my-terraform-state"
    key    = "global/s3/terraform.tfstate"
    region = "us-west-2"
  }
}
```

### 3. What is the difference between Terraform and other IaC tools like Ansible, Puppet, and Chef?
Terraform focuses on **infrastructure provisioning**, is **declarative**, and uses HCL. In contrast, tools like Ansible, Puppet, and Chef focus on **configuration management** and are **procedural**.

**Example:**
```hcl
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```

### 200. How do you manage secrets in Terraform?
Secrets can be managed using environment variables, secure secret management services (e.g., AWS Secrets Manager), or Terraform's `sensitive` attribute.

**Example:**
```hcl
resource "aws_secretsmanager_secret" "example" {
  name        = "example"
  description = "An example secret"
}

resource "aws_secretsmanager_secret_version" "example" {
  secret_id     = aws_secretsmanager_secret.example.id
  secret_string = jsonencode({
    username = "example_user"
    password = "example_password"
  })
}
```

---

**Created by:** [Your Name or GitHub Handle]  
**GitHub Page:** Hosted via [GitHub Pages](https://pages.github.com/)

---
