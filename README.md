# GCP-Professional-Cloud-Architect

## Resources

1. [PCA exam questions analysis](https://www.youtube.com/watch?v=iNJe_NrbijM&list=PLQMsfKRZZviTIxEh0pkWNwnDUasGVZS4n&index=2)
2. [GCP architecture framework](https://cloud.google.com/architecture/framework)


## Study cases

### 1. EHR Healthcare

[PDF](https://services.google.com/fh/files/blogs/master_case_study_ehr_healthcare.pdf)

#### Company overview

Saas, leading provider of electronic health record software to the medical industry.

#### Solution concept

1. Scale
2. Disaster recovery plan
3. Continuous deployment

#### Focus Area

Healthcare industry: heavily regulated for privacy / protection os sensitive personal data (PII = Personal Identifiable Information).

#### Business requirements

| BR  | GCP service |
| ------------- | ------------- |
| Provide a minimum 99.9% availability for all customer-facing systems  | [HTTP(S) load balancer](https://www.youtube.com/watch?v=0fQr7TRhnnU&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Reduce latency to all customers  | [Cloud CDN](https://www.youtube.com/watch?v=EumuFAfTWJY&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Provide centralized visibility and proactive action on system performance and usage  | [Operations](https://www.youtube.com/watch?v=Y7L2y6NVa9Y&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Increase ability to provide insights into healthcare trends | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML |
| Make predictions and generate reports on industry trends based on provider data  | [BigQuery](https://www.youtube.com/watch?v=So-tVyBQt8E&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd) & ML  |
| Maintain regulatory compliance | [DLP (Data Loss Protection)](https://www.youtube.com/watch?v=ab_Dctdu2G8&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |
| Decrease infrastructure administration costs | Serverless services & preemptible VMs|
 
#### Technical requirements

| BR  | GCP service |
| ------------- | ------------- |
| Provide a minimum 99.9% availability for all customer-facing systems  | [HTTP(S) load balancer](https://www.youtube.com/watch?v=0fQr7TRhnnU&list=PLTWE_lmu2InBzuPmOcgAYP7U80a87cpJd)  |

[Qwiklabs analysis video](https://partner.cloudskillsboost.google/course_sessions/717302/video/113393)
![Screenshot 2022-01-25 at 16 05 57](https://user-images.githubusercontent.com/39993930/151002335-1e84de78-ac06-462b-9c98-32e2a5795974.png)

[Youtube analysis video](https://www.youtube.com/watch?v=tSTDaMV8ZFc)

