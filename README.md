Comprehensive Web Application Performance Testing & Analysis: BlazeDemo

Student Name: NUR INSYIRAH BINTI MOHD SAPERI

Student ID: 2023270882

Course: ITT440 - Network Programming

Group: NBCS2555A

Instructor: SHAHADAN BIN SAAD


## 1. Introduction

Web application performance testing is a critical process used to evaluate the responsiveness,
stability, and scalability of a system under varying workloads. As modern web applications
are expected to serve a large number of concurrent users, performance degradation can lead
to poor user experience, revenue loss, and system instability.

This project aims to design, execute, and analyze comprehensive performance tests on a
publicly accessible web application using Apache JMeter. The selected target application
is BlazeDemo, a flight booking demonstration website. Multiple performance testing types
were conducted to simulate realistic user behavior and identify potential performance
bottlenecks.

The primary objective of this study is to measure key performance indicators (KPIs) such as
response time, throughput, and error rate under different load conditions and provide
recommendations for system optimization.

## 2. Tool Selection Justification

Apache JMeter was selected as the performance testing tool for this project due to its
open-source nature, extensive protocol support, and strong adoption in the industry.
JMeter allows the simulation of concurrent users through configurable thread groups and
provides detailed performance metrics through built-in listeners and reports.

Additionally, JMeter supports HTTP/HTTPS testing, parameterization, timers for realistic
think time simulation, and extensibility through plugins, making it suitable for both
basic and advanced performance testing scenarios.

## 3. Test Environment Setup

The performance tests were executed in the following environment:

- Operating System: Windows 10 (64-bit)
- Processor: Intel 
- Memory: 32 GB RAM (or your actual RAM)
- Network: Home broadband connection
- Testing Tool: Apache JMeter 5.6.3
- Java Version: Java 8 or later

## 4. Test Plan Design and Methodology

The test plan was designed to simulate a realistic user journey through the BlazeDemo
application. Each virtual user performs the following sequence of actions:

1. Access the homepage
2. Search for available flights
3. Select a flight
4. Submit purchase details and confirm booking

To simulate real user behavior, a Uniform Random Timer was added to introduce think time
between requests. HTTP Request Defaults and HTTP Header Manager were used to ensure
consistent request configuration across all test scenarios.

![WhatsApp Image 2025-12-14 at 22 13 16_801e6ba7](https://github.com/user-attachments/assets/60eb033f-bbee-4276-9712-b61b8d886a4f)

### 5.1 Load Test

The Load Test was conducted to evaluate application performance under normal expected
traffic conditions.

Configuration:
- Number of Users: 150
- Ramp-up Period: 120 seconds
- Test Duration: 15 minutes

The objective of this test was to assess system stability, average response time, and
throughput during sustained user activity.

![WhatsApp Image 2025-12-14 at 22 13 42_73041d26](https://github.com/user-attachments/assets/f2b94897-6ba9-4b92-b4f1-2a65ce19e466)

### 5.1.1 Load Test Result

![WhatsApp Image 2025-12-14 at 22 17 02_c27ad2d8](https://github.com/user-attachments/assets/b5ad9f0e-c17d-465f-aef6-e0b83533cf0b)
![WhatsApp Image 2025-12-14 at 22 17 23_baa953db](https://github.com/user-attachments/assets/1e4c8587-d898-4f27-b7d7-f16008ca93f6)
![WhatsApp Image 2025-12-14 at 22 17 37_892379bd](https://github.com/user-attachments/assets/ec519276-284f-4754-bf31-2847eddfc1c4)
![WhatsApp Image 2025-12-14 at 22 17 55_30c7f187](https://github.com/user-attachments/assets/3d1c451b-79da-4129-800b-1070ff8c28cd)


### 5.2 Stress Test

The Stress Test aimed to determine the application’s breaking point by gradually increasing
the number of concurrent users beyond normal operating conditions.

Configuration:
- Number of Users: 500
- Ramp-up Period: 60 seconds
- Test Duration: 10 minutes

This test helps identify system limitations, error thresholds, and failure points.

![WhatsApp Image 2025-12-14 at 22 36 47_cb3aa2a1](https://github.com/user-attachments/assets/a59c1208-cfe6-4356-a1df-4d92b31ed357)

### 5.2.1 Stress Test Result

![WhatsApp Image 2025-12-14 at 22 35 51_24afba0c](https://github.com/user-attachments/assets/3e845636-2502-43a0-a6ea-b838c7cacdad)
![WhatsApp Image 2025-12-14 at 22 38 35_186cd37a](https://github.com/user-attachments/assets/f18aa4fb-2d8a-4d2d-9bd2-9f916a0bca00)
![WhatsApp Image 2025-12-14 at 22 38 02_3e71f862](https://github.com/user-attachments/assets/a71ecfd3-cc82-4bd5-94dd-e8131f74c878)
![WhatsApp Image 2025-12-14 at 22 38 21_8a4142a2](https://github.com/user-attachments/assets/7ec37967-7a08-489b-8a69-f30a93bd602a)

### 5.3 Soak Test

The Soak Test was performed to evaluate the long-term stability of the application under
continuous load.

Configuration:
- Number of Users: 100
- Ramp-up Period: 300 seconds
- Test Duration: 20 minutes

The purpose of this test was to detect potential memory leaks, performance degradation,
or resource exhaustion over time.

![WhatsApp Image 2025-12-14 at 23 06 01_5fe1e906](https://github.com/user-attachments/assets/4f5d17d8-d2e7-48d7-939a-63ebb40893e4)

### 5.3.1 Soak Test Result

![WhatsApp Image 2025-12-14 at 23 06 35_6003e7b9](https://github.com/user-attachments/assets/85e96873-0947-4b40-abe0-55061aa2980e)
![WhatsApp Image 2025-12-14 at 23 07 02_ba58a8e3](https://github.com/user-attachments/assets/41a00b2a-332f-4357-beca-4cac2c5a81ec)
![WhatsApp Image 2025-12-14 at 23 07 13_b0ab8f5f](https://github.com/user-attachments/assets/cf53e655-033d-4624-a134-bf896e20c8ea)
![WhatsApp Image 2025-12-14 at 23 07 26_27842de3](https://github.com/user-attachments/assets/88d3421b-7add-41d8-b2f7-34dfb880663f)


## 6. Results and Data Analysis

The performance metrics collected include average response time, throughput, error rate,
and percentile response times (90th and 95th percentiles).

During the Load Test, the application maintained stable response times within acceptable
limits. However, during the Stress Test, response times increased significantly and error
rates began to appear, indicating server-side performance limitations.


## 7. Performance Bottleneck Identification

Analysis of the Stress Test results indicates that transaction-related requests, particularly
during the purchase confirmation stage, experienced increased latency. This suggests
potential bottlenecks related to server-side processing or database write operations.

Error rates observed during peak load further indicate insufficient resource handling
under extreme concurrency.


## 8. Recommendations

Based on the findings, the following improvements are recommended:

- Implement server-side caching to reduce response time
- Optimize database queries and indexing
- Introduce load balancing to distribute traffic evenly
- Improve connection pooling and request handling


## 9. Conclusion

This project successfully demonstrated the application of performance testing techniques
using Apache JMeter. Through Load, Stress, and Soak testing, critical insights into the
application’s performance characteristics were obtained.

The results highlight the importance of proactive performance evaluation and provide
valuable recommendations to enhance system scalability and reliability.









