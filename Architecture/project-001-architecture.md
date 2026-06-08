# Project 001 Architecture

## VoidOps Analytics Website Deployment

### Overview

This project demonstrates the deployment of a static website using Amazon Web Services (AWS) and Cloudflare. The solution provides secure HTTPS access to a custom domain while leveraging cloud-native services for scalability, performance, and reliability.

The architecture combines Amazon S3 for static content storage, Amazon CloudFront for global content delivery, AWS Certificate Manager (ACM) for SSL/TLS encryption, and Cloudflare DNS for domain management.

---

## Business Objective

Deploy the VoidOps Analytics website to a production-ready environment that:

* Uses a custom domain
* Supports HTTPS encryption
* Provides global content delivery
* Minimizes hosting costs
* Demonstrates foundational AWS cloud skills

---

## Architecture Diagram

```text
User Browser
      │
      ▼
Cloudflare DNS
      │
      ▼
CloudFront Distribution
      │
      ├── AWS Certificate Manager
      │      (SSL/TLS)
      │
      ▼
Amazon S3
(Static Website Content)
```

---

## Services Used

### Amazon S3

Purpose:

* Stores website files
* Hosts static content

Content Stored:

* HTML files
* CSS files
* Images
* Project assets

Benefits:

* Highly durable storage
* Low cost
* Simple static website hosting

---

### Amazon CloudFront

Purpose:

* Content Delivery Network (CDN)
* HTTPS termination
* Performance optimization

Benefits:

* Global edge locations
* Reduced latency
* Improved security
* Custom domain support

Distribution Features:

* Default root object configured
* HTTPS enabled
* Custom domain integration

---

### AWS Certificate Manager (ACM)

Purpose:

* SSL/TLS certificate management

Certificate Coverage:

* voidops.cloud
* *.voidops.cloud

Benefits:

* Free AWS-managed certificates
* Automatic renewal
* Secure HTTPS connections

Validation Method:

* DNS Validation

---

### Cloudflare DNS

Purpose:

* Domain management
* DNS resolution

Configured Records:

* Root domain (voidops.cloud)
* WWW subdomain ([www.voidops.cloud](http://www.voidops.cloud))
* ACM validation records
* Email routing records

Benefits:

* Simple DNS management
* Fast global resolution
* Future scalability options

---

## Request Flow

### User Access Process

1. User enters https://voidops.cloud

2. Cloudflare DNS resolves the domain

3. Traffic is directed to CloudFront

4. CloudFront presents the ACM SSL certificate

5. HTTPS connection is established

6. CloudFront retrieves website content from S3

7. Website is delivered to the user

---

## Security Controls

### HTTPS Encryption

* SSL/TLS certificate provided through ACM
* Traffic encrypted in transit
* HTTPS enforced through CloudFront

### IAM Security

* Administrative access separated from root account
* IAM user created for daily management activities

### DNS Validation

* Certificate ownership verified through Cloudflare DNS records

---

## Final Deployment URLs

Production Website:

https://voidops.cloud

https://www.voidops.cloud

---

## Skills Demonstrated

* AWS Account Configuration
* IAM User Administration
* Amazon S3 Static Website Hosting
* CloudFront Distribution Deployment
* SSL Certificate Management
* DNS Configuration
* Cloudflare Integration
* HTTPS Enablement
* Domain Validation
* Basic Cloud Architecture Design

---

## Future Enhancements

Potential improvements include:

* Route 53 migration
* Web Application Firewall (WAF)
* CI/CD deployment pipeline
* Infrastructure as Code (Terraform)
* Monitoring with CloudWatch
* Serverless contact forms
* Portfolio project expansion

---

## Project Status

Status: Completed

Completion Date: June 2026

Environment: Production

Domain: voidops.cloud
