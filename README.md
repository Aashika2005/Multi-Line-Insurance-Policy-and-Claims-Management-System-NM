# Multi-Line Insurance Policy and Claims Management System

A Salesforce-based insurance management solution designed to centralize and automate **Vehicle, Property, and Life Insurance** policy and claims processes.

## 📌 Project Overview

The **Multi-Line Insurance Policy and Claims Management System** replaces fragmented and manual insurance processes with a centralized Salesforce platform.

The system enables insurance agents to create and manage policies, generate guided quotes, calculate premiums automatically, route claims based on policy type, process high-value claim approvals, and provide claims adjusters with a dedicated dashboard.

## 🎯 Objectives

* Centralize Vehicle, Property, and Life Insurance policy management
* Simplify policy quoting using Salesforce Screen Flows
* Automate premium calculation using Apex
* Validate policy information and Vehicle Identification Numbers (VIN)
* Automatically route claims to the appropriate claims queue
* Automate approval of high-value claims
* Provide claims adjusters with an LWC dashboard
* Improve data accuracy, visibility, and operational efficiency
* Implement role-based and state-based access control

## 🚀 Key Features

### 1. Policy Management

* Custom **Policy** object
* Vehicle, Property, and Life policy Record Types
* Product-specific Field Sets
* Customer and policy information management
* Policy start date, premium, VIN, model year, property, and life insurance details

### 2. Guided Policy Quoting

A Salesforce **Screen Flow** guides insurance agents through the Vehicle Insurance quoting process.

The flow captures:

* Policy Holder
* Policy Start Date
* Policy State
* VIN
* Model Year

A draft policy is then created automatically.

### 3. VIN Validation

Vehicle policies include validation to ensure that the VIN contains exactly **17 characters**.

### 4. Automated Premium Calculation

The **PremiumCalculator Apex class** calculates the policy premium using policy information such as:

* Policy State
* Vehicle Model Year
* VIN

The calculated premium is automatically updated on the Policy record.

### 5. Claims Management

The system provides a custom **Claim** object for managing insurance claims.

Supported claim types include:

* Accident
* Property
* Life

Claims are associated with their respective insurance policies.

### 6. Automated Claim Routing

A Record-Triggered Flow identifies the policy type and automatically routes the claim to the appropriate queue:

```text
Vehicle Policy  → Auto Claims Queue
Property Policy → Property Claims Queue
Life Policy     → Life Claims Queue
```

### 7. High-Value Claim Approval

Claims above the configured **$50,000 threshold** are automatically submitted for approval.

The approval process includes:

```text
Claims Adjuster
      ↓
Senior Adjuster
      ↓
Department Manager
      ↓
Approved / Rejected
```

Approvers can review the claim and provide comments.

### 8. Claims Dashboard

A **Lightning Web Component (LWC)** provides claims adjusters with a centralized dashboard.

The dashboard displays:

* Claim Number
* Policy Type
* Policy Holder
* Claim Amount
* Approval Status
* Days Open

Claims can also be filtered by:

* All
* Auto
* Property
* Life

## 🏗️ System Architecture

```text
Insurance Agent
       │
       ▼
Screen Flow
       │
       ▼
Policy Validation
       │
       ▼
Policy Record
       │
       ▼
PremiumCalculator (Apex)
       │
       ▼
Claim Creation
       │
       ▼
Claim Routing Flow
       │
       ├── Auto Queue
       ├── Property Queue
       └── Life Queue
               │
               ▼
        Claims Adjuster
               │
               ▼
      High-Value Approval
               │
               ▼
       LWC Claims Dashboard
               │
               ▼
       Reports & Visibility
```

## 🛠️ Technology Stack

| Layer          | Technology                                     |
| -------------- | ---------------------------------------------- |
| Platform       | Salesforce                                     |
| UI             | Salesforce Lightning, Lightning Web Components |
| Automation     | Salesforce Flows                               |
| Business Logic | Apex                                           |
| Database       | Salesforce Custom Objects                      |
| Validation     | Validation Rules                               |
| Approvals      | Salesforce Approval Processes                  |
| Configuration  | Record Types, Field Sets, Custom Fields        |
| Security       | Permission Sets, Sharing Rules                 |
| Reporting      | Salesforce Reports & Dashboards                |
| Testing        | Apex Test Classes                              |

The documented technology stack includes Salesforce Lightning/LWC, Flows, Apex, custom objects, Record Types, Field Sets, Permission Sets, Sharing Rules, Reports/Dashboards, and Apex Test Classes.

## 📂 Main Salesforce Components

### Custom Objects

* `Policy__c`
* `Claim__c`

### Policy Record Types

* Auto
* Property
* Life

### Claim Record Types

* Accident
* Property
* Life

### Apex Classes

* `PremiumCalculator`
* `ClaimsAdjusterController`

### Lightning Web Components

* `claimsDashboardLwc`
* `claimTileLwc`

### Salesforce Flows

* Auto Quoting Flow
* Claim Routing Flow
* Premium Calculation Automation
* Submission Automation Flow
* Approver Review Flow

## 🔐 Security

The system uses Salesforce security features to control access to insurance information.

* Permission Sets for different user roles
* State-based Sharing Rules
* Role-specific access
* Controlled access to policy and claim information

The project documentation specifies role-specific access for Insurance Agents, Claims Adjusters, and Claims Managers.

## 👥 User Roles

### Insurance Agent

* Create and manage policies
* Generate policy quotes
* Enter customer and policy information

### Claims Adjuster

* View assigned claims
* Review claim information
* Monitor claim status
* Use the Claims Dashboard

### Senior Adjuster

* Review high-value claims
* Approve or reject claims

### Claims Manager / Department Manager

* Review high-value claims
* Complete the approval process
* Monitor claims operations

## 🔄 Main Workflow

```text
Customer / Agent
      ↓
Policy Information
      ↓
Guided Quote
      ↓
Policy Validation
      ↓
Premium Calculation
      ↓
Policy Creation
      ↓
Claim Creation
      ↓
Automatic Claim Routing
      ↓
Claims Review
      ↓
High-Value Approval
      ↓
Claim Decision
      ↓
Dashboard & Reporting
```

## 📊 Functional Requirements

The system supports:

* Policy creation and management
* Separate Record Types for multiple insurance products
* Product-specific policy information
* Guided quoting
* Automated premium calculation
* VIN validation
* Claim creation and management
* Automatic claim routing
* High-value claim identification
* Multi-level claim approval
* Approve/Reject functionality
* LWC Claims Dashboard
* Claim filtering
* Automated record updates
* Role-based access
* Reporting and dashboards

## 📈 Benefits

* Centralized insurance data management
* Reduced manual processing
* Standardized policy quoting
* Automated premium calculation
* Faster claim routing
* Structured approval workflows
* Improved claims visibility
* Better data accuracy
* Scalable support for multiple insurance products

## 🧪 Testing

Testing includes validation of:

* Policy creation
* VIN validation
* Premium calculation
* Claim creation
* Claim routing
* High-value claim approval
* LWC dashboard functionality
* User access and security
* Apex functionality using Test Classes

## 📚 Project Documentation

The complete project documentation contains the project ideation, requirements analysis, data flow, architecture, planning, development milestones, Salesforce configuration steps, Apex implementation, LWC development, approval automation, security, and testing details.

## 🔮 Future Enhancements

Potential future enhancements include:

* Customer self-service insurance portal
* Automated email/SMS notifications
* Advanced analytics and reporting
* AI-assisted claim classification
* Fraud detection integration
* Mobile-friendly claims management
* Additional insurance product types
* Integration with external payment and insurance systems

## 👨‍💻 Project Status

**Status:** Completed / Salesforce Development Project

## 📄 License

This project is intended for educational and demonstration purposes.
