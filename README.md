# cst8919-lab3
Youtube link: https://youtu.be/5lyVmofL7Bg

## Summary of this lab

This lab focuses on implementing cloud governance, security, and compliance within Microsoft Azure using Azure Policy. Specifically, restrict the creation within specific resource group by validating if they: 
- Located at Canada Central
- Create Public IP
- Has Tag `ProjectName`

## Explaination on each policy:

### 1. Only-CanadaCentral
- Description: This policy denies the creation of any Azure resource outside the `Canada Central` region. This is crucial for data residency, compliance, and cost management, ensuring resources are deployed only in approved geographic locations.
- Effect: `Deny`

### 2. Require-ProjectName-Tag
- Description: This policy mandates that all newly created Azure resources must include a tag named `ProjectName`. This tag is essential for cost allocation, resource organization, and automation within MapleTech Solutions.
- Effect: `Deny`
- Parameter: `tagName` (defaults to `ProjectName`)

### 3. Deny-Public-IP
- Description: This policy explicitly prevents the creation of Public IP addresses within the assigned scope. This is a critical security control to minimize the attack surface by ensuring resources are not directly exposed to the internet unless specifically allowed by other, more granular controls.
- Effect: `Deny`