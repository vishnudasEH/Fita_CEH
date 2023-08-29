# Cloud computing

- Cloud computing = On-demand access to IT capabilities
- Before cloud computing
  - Everything was stored and processed locally (on-premises)
  - Centralized, secluded and segmented
- Now third party (cloud provider) stores the data.

### Essential characteristics

- **S3 Bucket**
  - S3 buckets are used by customers and end users to store text documents, PDFs, videos, images, etc. To store all these data, the user needs to create a bucket with a unique name.
    
- **Enumerate S3 Buckets using lazys3**
  - lazys3 is a Ruby script tool that is used to brute-force AWS S3 buckets using different permutations. This tool obtains the publicly accessible S3 buckets and also allows you to search the S3 buckets of a specific company by entering the company name.
    #### ruby lazys3.rb [Example]
    
- **Enumerate S3 Buckets using S3Scanner**
  - S3Scanner is a tool that finds the open S3 buckets and dumps their contents. It takes a list of bucket names to check as its input. The S3 buckets that are found are output to a file. The tool also dumps or lists the contents of “open” buckets locally.
    #### python3 ./s3scanner.py sites.txt
  
### Infrastructure as a services (IaaS)

- Capability for consumers to provision processing, storage, networks, and other fundamental computing resources
- Aims to give most control over the provided hardware that runs applications
  - E.g. operating systems, storage, and networking components
- E.g. virtual machines (EC2 in Amazon), virtual networks.

### Platform as a Service (PaaS)

- Provides capability for consumers to deploy onto managed cloud infrastructure
- Allows consumer to use programming languages, SDKs, services, and tools supported by the provider
- Consumer does not control or manage underlying cloud infrastructure
  - But can control deployed applications and configurations for the hosting environment
- Provides an environment for building, testing, and deploying software applications
  - Can add features such authentication.
- Aims to help creating an application quickly without managing the underlying infrastructure.
- E.g. development tools, config management, and deployment platforms

### Software as a Service (SaaS)

- Software that is centrally hosted and managed for the end customer.
- User does not control underlying cloud architecture
  - E.g. network, servers, OS, storage etc.
  - Can only control limited user-specific application configurations.

### IaaS vs PaaS vs SaaS

![SaaS vs IaaS vs PaaS](https://raw.githubusercontent.com/KICSrwp/CEH-Learning/main/chapters/16-cloud-computing/img/saas-vs-iaas-vs-paas.png)

### Identity-as-a-Service (IDaaS)

- Managed authentication services
- Services include e.g. • [Single-Sign-On (SSO)](./../01-introduction/identity-access-management-(iam).md#single-sign-on-sso) • [Multi-Factor-Authentication (MFA)](./../01-introduction/identity-access-management-(iam).md#multi-factor-authentication-mfa) • Identity Governance and Administration (IGA) • Access management • Intelligence collection

### Security-as-a-Service (SECaaS)

- Integrates security services into corporate infrastructure
- Services include e.g. • penetration testing • authentication • intrusion detection • anti-malware • security and incident management.
- E.g. [McAfee Cloud Security](https://www.mcafee.com/enterprise/en-us/solutions/cloud-security.html)

### Container-as-a-Service (CaaS)

- Container and cluster services
- Services include e.g. • virtualized container engines • easier container and cluster management

### Function-as-a-Service (FaaS)

- Provides a platform allowing to develop, run, and manage functionalities without any infrastructure effort.
- E.g. [AWS Lambda](https://aws.amazon.com/lambda/), [Google Cloud Functions](https://cloud.google.com/functions), [Azure Functions](https://azure.microsoft.com/en-us/services/functions/)

## Separation of duties

- Cloud computing is the ultimate in separation of duties
- E.g.
  - The data owner is the entity accountable for the data itself
  - Data custodian is the entity responsible for access to the data
  - When a single individual becomes both the data owner and the data custodian, security issues can arise.
- Also a countermeasure for [insider attacks](./../01-introduction/security-threats-and-attacks.md#insider-attack-countermeasures) and [social engineering attacks](./../10-social-engineering/social-engineering-types.md#social-engineering-countermeasures).

### Shared responsibility

- **On-premises**: you manage everything.
- **IaaS**: provider manages virtualization, servers, storage and networking
- **PaaS**: provider additionally manages OS, middleware and runtime
- **SaaS**: provider manages everything

#### Private cloud

- Provisioned for exclusive use of single organization
- May be owned/managed/operated by the organization, third party or combination
- May be on or off premises

#### Public cloud

- No local hardware to manage or keep up-to-date, everything runs on your cloud provider's hardware.
- Services are rendered over a network
- Provisioned for open use by the general public
- May be owned/managed/operated by a business, academic, government or combination.
- Exists on the premises of the cloud provider.

#### Community Cloud

- Shared infrastructure between several organizations with shared concerns (e.g. compliance)
- Not open to public
- May be owned/managed/operated by the organization, third party or combination
- May be on or off premises

#### Hybrid cloud

- Composition of two or more cloud (private, community or public)
- Infrastructures remain unique entities
  - but are bound by a technology allowing data and application portability.

#### Multi cloud

- Multi-cloud is a environment where an organization leverages two or more cloud computing platforms to perform various tasks
- Increases capabilities with combined offering
- Limits data loss and downtime to a greater extent.
- Management products include • [Azure Arc](https://azure.microsoft.com/en-us/services/azure-arc) • [Google Anthos](https://cloud.google.com/anthos) • [AWS Outposts](https://aws.amazon.com/outposts/)

## Pros and cons of cloud computing

### Advantages of cloud computing

- **Economical**: Less infrastructure cost, less cost of ownership, fewer capital expenses
- **Operational**: cost efficient, elastic, quick provisioning, automatic updates, backup and recovery...
- **Staffing**: Less staff is required, less personal training
- **Security**: Patch application and updates, less cost on security configurations, better disaster recovery, audit and monitoring on providers side, better management of security systems.
- **Innovation**: Quick access to innovation

### Disadvantages of cloud computing

- Organizations have limited control and flexibility
- Prone to outages and other technical issues
- Security, privacy, and compliance issues
- Contracts and lock-ins
- Depends on network connections
- Can be hard to migrate from one to another

## Cloud regulations

- **PCI DSS**: Deals with debit and credit cards, but also has a cloud SIG

## tools
- trivy
- clair
- dadga
- spyse (to enumerate S3 buckets)
- s3scanners
- GCPBucketBrute (for escalate privileges on google buckets)
- AWS pwn
- Scout Suite

