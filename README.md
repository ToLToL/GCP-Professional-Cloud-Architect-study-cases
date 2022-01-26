# GCP-Professional-Cloud-Architect

## Resources

1. [PCA exam questions analysis](https://www.youtube.com/watch?v=iNJe_NrbijM&list=PLQMsfKRZZviTIxEh0pkWNwnDUasGVZS4n&index=2)
2. [GCP architecture framework](https://cloud.google.com/architecture/framework)


# Study cases

## 1. EHR Healthcare

### Links
1. [Case study pdf](https://services.google.com/fh/files/blogs/master_case_study_ehr_healthcare.pdf)

2. [Qwiklabs analysis video](https://partner.cloudskillsboost.google/course_sessions/717302/video/113393)

3. [Youtube analysis video](https://www.youtube.com/watch?v=tSTDaMV8ZFc)

### Company overview

Saas, leading provider of electronic health record software to the medical industry.

### Solution concept

1. Scale
2. Disaster recovery plan
3. Continuous deployment

### Focus Area

Healthcare industry: heavily regulated for privacy / protection os sensitive personal data (PII = Personal Identifiable Information).
Software is currently hosted in multiple colocation facilities, the lease on one of the data centers is about to expire (we'll migrate this one first): step by step migration.

![Screenshot 2022-01-25 at 18 13 10](https://user-images.githubusercontent.com/39993930/151025508-fa94f9d5-e0eb-420b-8d7c-9c6e636fe994.png)

### Existing technical environment

| Existing technical environment  | GCP service |
| ------------- | ------------- |
| Customer-facing applications are web-based, and many have recently been containerized to run on a group of Kubernetes clusters  | [GKE](https://www.youtube.com/watch?v=F8s-DAfMtRM&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Data is stored in a mixture of relational and NoSQL databases (MySQL, MS SQL Server, Redis, and MongoDB) | MySQL / MS SQL Server: [Cloud SQL](https://www.youtube.com/watch?v=nGwOPAqgX7U&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) / [Cloud Spanner](https://youtu.be/hRDpbHtNceU) Redis: [MemoryStore](https://www.youtube.com/playlist?list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd), MongoDB: Mongo Atlas on Marketplace |
| Users are managed via Microsoft Active Directory | [Cloud Identity](https://www.youtube.com/watch?v=Hhqi8xCEI7U)  |
| Monitoring is currently being done via various open source tools. Alerts are sent via email and are often ignored  | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |

### Business requirements

| Business requirement  | GCP service |
| ------------- | ------------- |
| Provide a minimum 99.9% availability for all customer-facing systems  | [HTTP(S) load balancer](https://www.youtube.com/watch?v=0fQr7TRhnnU&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Reduce latency to all customers  | [Cloud CDN](https://www.youtube.com/watch?v=EumuFAfTWJY&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Provide centralized visibility and proactive action on system performance and usage  | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Increase ability to provide insights into healthcare trends | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML |
| Make predictions and generate reports on industry trends based on provider data  | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML  |
| Maintain regulatory compliance | [DLP (Data Loss Protection)](https://www.youtube.com/watch?v=ab_Dctdu2G8&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Decrease infrastructure administration costs | Serverless services & preemptible VMs|
 
### Technical requirements

| Technical requirement  | GCP service |
| ------------- | ------------- |
| Maintain legacy interfaces to insurance providers with connectivity to both on-premises systems and cloud providers  | [Apigee](https://www.youtube.com/watch?v=vGe38icp0n4)  |
| Provide a consistent way to manage customer-facing applications that are container-based, not enough time to lift and shift all apps on GCP --> kubernetes on prem and GCP: hybrid  | [Anthos](https://www.youtube.com/watch?v=FfJNAjoX3Uc&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Provide a secure and high-performance connection between on-premises systems and Google Cloud  | [Dedicated interconnect](https://www.youtube.com/watch?v=cKaryf7qp9w&t=9s) > 10 GB/s otherwise partner interconnect |
| Provide consistent logging, log retention, monitoring, and alerting capabilities  | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |
| Maintain and manage multiple container-based environments | [Artifact registry](https://www.youtube.com/watch?v=712Y0KpeHok) |
| Dynamically scale and provision new environments  | fully-managed CI / CD platform: [Cloud Build](https://www.youtube.com/watch?v=Bvo6jzC3J_A&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd), managed CD to Kubernetes: [Cloud Deploy](https://cloud.google.com/blog/products/devops-sre/google-cloud-deploy-now-ga) |
| Create interfaces to ingest and process data from new providers  | [Pub / Sub](https://www.youtube.com/watch?v=JrKEErlWvzA&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) / [Dataflow](https://www.youtube.com/watch?v=WRspZRG9e90&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) / [Cloud Storage](https://www.youtube.com/watch?v=BeYr34swAVE&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |


## 2. Helicopter Racing League

### Links
1. [Case study pdf](https://services.google.com/fh/files/blogs/master_case_study_helicopter_racing_league.pdf)

2. [Qwiklabs analysis video](https://partner.cloudskillsboost.google/course_sessions/717302/video/113393)

3. [Youtube analysis video](https://www.youtube.com/watch?v=tSTDaMV8ZFc)


### Company overview

Global sports league for competitive helicopter racing. Each year:

- world championship
- several regional league competitions to earn a spot in the world championship

HRL offers paid service to:

- stream the races all over the world
- live telemetry
- predictions throughout each race

### Solution concept

1. Expand use of AI / ML to facilitate race predictions
2. CDN: New fans in emerging regions -> serve content (real-time and recorded) close to their users

### Focus Area

### Existing technical environment

| Existing technical environment  | GCP service |
| ------------- | ------------- |
| Existing content is stored in an object storage service on their existing public cloud provider | [Cloud storage](https://www.youtube.com/watch?v=F8s-DAfMtRM&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Video encoding and transcoding is performed on VMs created for each job | [Dataflow](https://www.youtube.com/watchv=nGwOPAqgX7U&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |
| Race predictions are performed using TensorFlow running on VMs in the current public cloud provider| [AI platform](https://www.youtube.com/watch?v=Hhqi8xCEI7U)  |

### Business requirements

| Business requirement  | GCP service |
| ------------- | ------------- |
| Support ability to expose the predictive models to partners  | [HTTP(S) load balancer](https://www.youtube.com/watch?v=0fQr7TRhnnU&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Increase predictive capabilities during and before races: Race results, Mechanical failures, Crowd sentiment | [Cloud CDN](https://www.youtube.com/watch?v=EumuFAfTWJY&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Increase telemetry and create additional insights | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Measure fan engagement with new predictions| [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML |
| Enhance global availability and quality of the broadcasts | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML  |
| Increase the number of concurrent viewers | [DLP (Data Loss Protection)](https://www.youtube.com/watch?v=ab_Dctdu2G8&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Minimize operational complexity | Serverless services & preemptible VMs|
| Ensure compliance with regulations | Serverless services & preemptible VMs|
| Create a merchandising revenue stream | Serverless services & preemptible VMs|

### Technical requirements

| Technical requirement  | GCP service |
| ------------- | ------------- |
| Maintain or increase prediction throughput and accuracy  | [Apigee](https://www.youtube.com/watch?v=vGe38icp0n4)  |
| Reduce viewer latency | [Anthos](https://www.youtube.com/watch?v=FfJNAjoX3Uc&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Increase transcoding performance | [Dedicated interconnect](https://www.youtube.com/watch?v=cKaryf7qp9w&t=9s) > 10 GB/s otherwise partner interconnect |
| Create real-time analytics of viewer consumption patterns and engagement | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |
| Create a data mart to enable processing of large volumes of race data | [Artifact registry](https://www.youtube.com/watch?v=712Y0KpeHok) |
