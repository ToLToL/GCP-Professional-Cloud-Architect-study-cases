# GCP Professional Cloud Architect - study cases

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

2. [Youtube analysis video](https://www.youtube.com/watch?v=tSTDaMV8ZFc)


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

1. Real-time predictions
2. Process season-long results
3. Close to users (emerging regions)


![Screenshot 2022-01-26 at 11 16 35](https://user-images.githubusercontent.com/39993930/151145200-10857353-7f7f-4f47-b2ec-d7ae6895be8f.png)


### Qwiklabs analysis

![Screenshot 2022-01-26 at 10 34 18](https://user-images.githubusercontent.com/39993930/151138577-9ab4ce0b-1439-4605-9f53-f90d5a1ebf67.png)

### Existing technical environment

| Existing technical environment  | GCP service |
| ------------- | ------------- |
| Existing content is stored in an object storage service on their existing public cloud provider | [Cloud storage](https://www.youtube.com/watch?v=F8s-DAfMtRM&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Video encoding and transcoding is performed on VMs created for each job | [Dataflow](https://www.youtube.com/watchv=nGwOPAqgX7U&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) |
| Race predictions are performed using TensorFlow running on VMs in the current public cloud provider| [AI platform](https://www.youtube.com/watch?v=Hhqi8xCEI7U)  |

### Business requirements

| Business requirement  | GCP service |
| ------------- | ------------- |
| Support ability to expose the predictive models to partners  | [Cloud Endpoint](https://www.youtube.com/watch?v=0fQr7TRhnnU&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & [Cloud API Gateway]()  |
| Increase predictive capabilities during and before races: | |
Race results | SQL or NoSQL ? |
Mechanical failures | sensors, IoT, time series database: BigTable|
Crowd sentiment | NoSQL: Datastore |
| Increase telemetry and create additional insights | BigQuery |
| Measure fan engagement with new predictions| NoSQL: Datastore |
| Enhance global availability and quality of the broadcasts | CDN and VMs across regions |
| Increase the number of concurrent viewers | Autoscale: Managed instance group  |
| Minimize operational complexity | Serverless & managed services |
| Ensure compliance with regulations | Cloud IAM: lest privilege access, Operations: audit logs / cloud storage: encryption, KMS|
| Create a merchandising revenue stream | ? |

### Technical requirements

| Technical requirement  | GCP service |
| ------------- | ------------- |
| Maintain or increase prediction throughput and accuracy  | ML model |
| Reduce viewer latency | Multi-regional bucket & Cloud CDN  |
| Increase transcoding performance | [Transcoder API](https://cloud.google.com/transcoder/docs)|
| Create real-time analytics of viewer consumption patterns and engagement | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & Notebook: [DataLab](https://www.youtube.com/watch?v=Eu57QKNHaiY) & [Data Studio](https://www.youtube.com/watch?v=cd555DBrehg)|
| Create a data mart to enable processing of large volumes of race data | BigQuery |



## 3. Mountkirk Games

### Links
1. [Case study pdf](https://services.google.com/fh/files/blogs/master_case_study_mountkirk_games.pdf)

2. [Youtube analysis video](https://www.youtube.com/watch?v=1w1olPjlPZY)


### Company overview

Online, session-based, multiplaye games for mobile. It started expanding to other platform after migrating their on-premises environment to GCP.
They want to create a FPS game that allows:

- 100s simultaneous players to join a digital arena from multiple platforms and locations
- Real-time digital banner that displays a global leaderboard of top players

### Solution concept

1. Game's backend: GKE to scale rapidly
2. Route players to the closest regional game arenas: global load balancer
3. Keep the global leader in sync: New fans in emerging regions -> multi-region Spanner cluster

### Focus Area

1. Cloud-native design principales
2. Top priority: latency and then cost management
3. Advanced analytics capabilities --> iterate deployment of bug fixes and new functionality (CI / CD)


![Screenshot 2022-01-26 at 15 30 36](https://user-images.githubusercontent.com/39993930/151181786-e53f9425-3b39-467b-8aba-788598d0f5b5.png)

### Qwiklabs analysis

![Screenshot 2022-01-26 at 15 01 22](https://user-images.githubusercontent.com/39993930/151176857-483c1082-82fa-4709-8715-6b85ce0f4346.png)


### Existing technical environment

| Existing technical environment  | GCP service |
| ------------- | ------------- |
| Lift-and-shifted 5 games on GCP VMs | [Cloud storage](https://www.youtube.com/watch?v=F8s-DAfMtRM&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| 1 game / folder that maintains most of the permissions / network policies| Cloud IAM |
| 1 folder for legacy games with low traffic | |
| Separate sev / testing / prod projects / folder | |


### Business requirements

| Business requirement  | GCP service |
| ------------- | ------------- |
| Support multiple gaming platforms | Global HTTP(S) load balancer |
| Support multiple regions | Global HTTP(S) load balancer + GKE nodes autoscaling (autopilot) + Spanner (multi-region) |
| Support rapid iteration of game features | CI / CD: Cloud Source Repositories, Cloud Build, Cloud Container Registry, Cloud Deploy (or Jenkins),  |
| Minimize latency | Global HTTP(S) load balancer |
| Optimize for dynamic scaling | GKE nodes autoscaling (autopilot) + Spanner (multi-region) |
| Use managed services and pooled resources | GKE & Spanner |
| Minimize costs | [Cloud Billing: alerts / visualize](https://cloud.google.com/billing/docs/reports)  |


### Technical requirements

| Technical requirement  | GCP service |
| ------------- | ------------- |
| Dynamically scale based on game activity | GKE autoscaling / Spanner (autoscales by default) |
| Publish scoring data on a near real–time global leaderboard |  |
| Store game activity logs in structured files for future analysis | NoSQL: Datastore |
| Use GPU processing to render graphics server-side for multi-platform support | GKE with GPUs enhanced VMs |
| Support eventual migration of legacy games to this new platform | legacy games must be containerized for micro-services architecture because we use GKE |



## 4. TerramEarth

### Links
1. [Case study pdf](https://services.google.com/fh/files/blogs/master_case_study_terramearth.pdf)

2. [Youtube analysis video](https://www.youtube.com/watch?v=0G8hx9HUnbk)


### Company overview

Manufactures heavy equipment for the mining / agricultural industries.
500 dealers, service centers in 100 countries. Their mission: build products that make their customers more productive.

### Solution concept

1. Collect telemetry data from sensors on 2 million vehicles.
2. Small subset of data transmitted from the vehicles in real-time to facilicate fleet mangement
3. The rest of the sensor data: collected, compressed and uploaded daily
4. 200 ~ 500 MB of data / vehicle / day --> 400 TB ~ 1 PB / day

### Focus Area

IoT

1. Customer service, minimize vehicle downtimes
2. Online fleet management services, improve operations of their dealerships
3. 5-year plan: create a partner ecosystem of new products by:
- enabling access to their data
- increasing autonomous operation capabilities of their vehicles
- creating a path to move the remaining legacy systems to the cloud

![Screenshot 2022-01-26 at 16 54 00](https://user-images.githubusercontent.com/39993930/151198030-8cdc1b10-8e8e-4659-8a6d-9c5fe58a2feb.png)

### Qwiklabs analysis
![Screenshot 2022-01-26 at 16 39 50](https://user-images.githubusercontent.com/39993930/151195375-9305ff91-992d-4952-ba3f-7516b2bd6b05.png)


### Existing technical environment

| Existing technical environment  | GCP service |
| ------------- | ------------- |
| data aggregation and analysis infrastructure in GCP / serves clients from all around the world | DataFlow, BigQuery, Global HTTP(S) load balancer |
| data captured from their 2 main manufacturing plants and sent to private data centers that contain their legacy inventory / logistics mangement systems |  |
| Private data centers connected to GCP via multiple network interconnects | Interconnect |
| Web frontend for dealers / customers in GCP and allows access to stock management & analytics | App Engine, Cloud Run, GKE |


### Business requirements

| Business requirement  | GCP service |
| ------------- | ------------- |
| Predict and detect vehicle malfunction and rapidly ship parts to dealerships for just-intime repair where possible | ML / Tensorflow & BigQuery |
| Decrease cloud operational costs and adapt to seasonality | managed services: App Engine, GKE, Cloud Run |
| Increase speed and reliability of development workflow | CI / CD: Cloud Build |
| Allow remote developers to be productive without compromising code or data security | Cloud Identity, Cloud IAM |
| Create a flexible and scalable platform for developers to create custom API services for dealers and partners | [Apigee](https://www.youtube.com/watch?v=vGe38icp0n4)|


### Technical requirements

| Technical requirement  | GCP service |
| ------------- | ------------- |
| Create a new abstraction layer for HTTP API access to their legacy systems to enable a gradual move into the cloud without disrupting operations | [Apigee](https://www.youtube.com/watch?v=vGe38icp0n4) |
| Modernize all CI/CD pipelines to allow developers to deploy container-based workloads in highly scalable environments | Cloud Sources Repositories, Cloud Build, Container Registry, Artifact Registry, Jenkins, Cloud Deploy, Cloud Run, GKE |
| Allow developers to run experiments without compromising security and governance requirements | Sandbox: project for test purposes |
| Create a self-service portal for internal and partner developers to create new projects, request resources for data analytics jobs, and centrally manage access to the API endpoints | ? |
| Use cloud-native solutions for keys and secrets management and optimize for identity-based access | [KMS](https://www.youtube.com/watch?v=38_dWxOHUN8) |
| Improve and standardize tools necessary for application and network monitoring and troubleshooting | Operations |
