# GCP-Professional-Cloud-Architect

## Resources

1. [PCA exam questions analysis](https://www.youtube.com/watch?v=iNJe_NrbijM&list=PLQMsfKRZZviTIxEh0pkWNwnDUasGVZS4n&index=2)
2. [GCP architecture framework](https://cloud.google.com/architecture/framework)


## Study cases

### 1. EHR Healthcare

#### Company overview

Saas, leading provider of electronic health record software to the medical industry.

#### Solution concept

1. Scale
2. Disaster recovery plan
3. Continuous deployment

#### Focus Area

Healthcare industry: heavily regulated for privacy / protection os sensitive personal data (PII = Personal Identifiable Information).
Software is currently hosted in multiple colocation facilities, the lease on one of the data centers is about to expire (we'll migrate this one first): step by step migration.

#### Existing technical environment

| Existing technical environment  | Application Tier | GCP service |
| ------------- | ------------- | ------------- |
| Customer-facing applications are web-based, and many have recently been containerized to run on a group of Kubernetes clusters  | Web | [GKE](https://www.youtube.com/watch?v=F8s-DAfMtRM&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Data is stored in a mixture of relational and NoSQL databases (MySQL, MS SQL Server, Redis, and MongoDB) | Data | MySQL / MS SQL Server: [Cloud SQL](https://www.youtube.com/watch?v=nGwOPAqgX7U&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) / [Cloud Spanner](https://youtu.be/hRDpbHtNceU) Redis: [MemoryStore](https://www.youtube.com/playlist?list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd), MongoDB: Mongo Atlas on Marketplace |


#### Business requirements

| Business requirement  | GCP service |
| ------------- | ------------- |
| Provide a minimum 99.9% availability for all customer-facing systems  | [HTTP(S) load balancer](https://www.youtube.com/watch?v=0fQr7TRhnnU&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Reduce latency to all customers  | [Cloud CDN](https://www.youtube.com/watch?v=EumuFAfTWJY&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Provide centralized visibility and proactive action on system performance and usage  | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Increase ability to provide insights into healthcare trends | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML |
| Make predictions and generate reports on industry trends based on provider data  | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML  |
| Maintain regulatory compliance | [DLP (Data Loss Protection)](https://www.youtube.com/watch?v=ab_Dctdu2G8&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Decrease infrastructure administration costs | Serverless services & preemptible VMs|
 
#### Technical requirements

| Technical requirement  | GCP service |
| ------------- | ------------- |
| Maintain legacy interfaces to insurance providers with connectivity to both on-premises systems and cloud providers  | [Apigee](https://www.youtube.com/watch?v=vGe38icp0n4)  |
| Provide a consistent way to manage customer-facing applications that are container-based, not enough time to lift and shift all apps on GCP --> kubernetes on prem and GCP: hybrid  | [Anthos](https://www.youtube.com/watch?v=FfJNAjoX3Uc&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Provide a secure and high-performance connection between on-premises systems and Google Cloud  | [Dedicated interconnect](https://www.youtube.com/watch?v=cKaryf7qp9w&t=9s) > 10 GB/s otherwise partner interconnect |
| Provide consistent logging, log retention, monitoring, and alerting capabilities  | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |
| Maintain and manage multiple container-based environments | [Artifact registry](https://www.youtube.com/watch?v=712Y0KpeHok) |
| Dynamically scale and provision new environments  | fully-managed CI / CD platform: [Cloud Build](https://www.youtube.com/watch?v=Bvo6jzC3J_A&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Create interfaces to ingest and process data from new providers  | [Pub / Sub](https://www.youtube.com/watch?v=JrKEErlWvzA&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) / [Dataflow](https://www.youtube.com/watch?v=WRspZRG9e90&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) / [Cloud Storage](https://www.youtube.com/watch?v=BeYr34swAVE&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |


### Links
1. [Case study pdf](https://services.google.com/fh/files/blogs/master_case_study_ehr_healthcare.pdf)

2. [Qwiklabs analysis video](https://partner.cloudskillsboost.google/course_sessions/717302/video/113393)
![Screenshot 2022-01-25 at 16 05 57](https://user-images.githubusercontent.com/39993930/151002335-1e84de78-ac06-462b-9c98-32e2a5795974.png)

3. [Youtube analysis video](https://www.youtube.com/watch?v=tSTDaMV8ZFc)
