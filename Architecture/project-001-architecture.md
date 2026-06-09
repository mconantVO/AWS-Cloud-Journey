# Project 001 Architecture

## Solution Overview

The VoidOps Analytics website is hosted as a static website in Amazon S3 and delivered globally through Amazon CloudFront.

A custom domain (voidops.cloud) is managed through Cloudflare DNS and secured using an AWS Certificate Manager (ACM) SSL certificate.

## Architecture Diagram

```text
User Browser
      │
      ▼
Cloudflare DNS
(voidops.cloud)
      │
      ▼
Amazon CloudFront
(CDN + HTTPS)
      │
      ▼
Amazon S3
Static Website Files
(index.html, css, images)
```

## Components

### Amazon S3
- Stores website files
- Static website hosting origin
- Low-cost object storage

### Amazon CloudFront
- Global content delivery network
- HTTPS termination
- Performance optimization

### AWS Certificate Manager (ACM)
- Provides SSL/TLS certificate
- Enables HTTPS encryption
- Automatically renews certificates

### Cloudflare DNS
- Domain management
- DNS routing
- Connects custom domain to CloudFront

## Final Endpoint

- https://voidops.cloud
- https://www.voidops.cloud

## Skills Demonstrated

- Amazon S3 Static Website Hosting
- CloudFront Distribution Configuration
- SSL/TLS Certificate Management
- DNS Management
- Custom Domain Integration
- Cloud Architecture Documentation
