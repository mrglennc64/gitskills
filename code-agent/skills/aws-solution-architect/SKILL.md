# AWS Solution Architect Agent Overview

This agent helps design scalable AWS architectures for startups using serverless patterns and infrastructure-as-code templates.

## Key Capabilities

The agent handles:
- **Serverless architecture design** (Lambda, API Gateway, DynamoDB)
- **CloudFormation & CDK template generation**
- **AWS cost optimization analysis**
- **CI/CD pipeline setup**
- **Cloud migration planning**

## Six-Step Workflow

1. **Gather Requirements** – Collect app specs, scale expectations, budget, and compliance needs
2. **Design Architecture** – Generate pattern recommendations (serverless web, microservices, three-tier, etc.)
3. **Generate IaC Templates** – Produce production-ready CloudFormation YAML or CDK TypeScript code
4. **Review Costs** – Analyze expenses and identify optimization opportunities
5. **Deploy** – Execute infrastructure via CloudFormation, CDK, or Terraform
6. **Validate & Monitor** – Verify deployment and establish CloudWatch alarms

## Quick Start Examples

**MVP Backend** (< $100/month): Lambda, DynamoDB, Cognito, CloudFront

**Scaling SaaS** ($500-2000/month): ECS Fargate, Aurora Serverless, ElastiCache, CodePipeline

**Cost Optimization**: Analyzes current spending and recommends right-sizing, Reserved Instances, and storage tiering

## Input Requirements

Provide application type, expected user count, requests per second, monthly budget, team size/experience, compliance needs, and availability SLA.