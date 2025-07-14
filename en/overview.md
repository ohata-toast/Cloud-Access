# Cloud Access Overview

**Security > Cloud Access > Overview**

Cloud Access is a service that enables secure access to NHN Cloud resources based on a Zero Trust security model.

Through a dedicated agent, users can access resources easily without complex configurations, while administrators can efficiently manage the service via the NHN Cloud console using user and continuous authentication, real-time logging, and monitoring features.

## Main Features

* Customized Account Management
    * Administrators can assign customized access permissions and policies to each user. Beyond simple allow/block rules, they can define which resources a user can access, during which time frames, and from which devices.
    * Users can be grouped according to the customer’s environment, allowing consistent policy enforcement even in complex user settings.
* Continuous Device Verification
    * When accessing resources, users’ devices are continuously verified based on defined policies—checking IP/MAC, OS, processes, registry, antivirus, and more. If a policy violation is detected, reauthentication is required.
* Real-time Monitoring and Logging
    * The system collects and stores real-time activity logs such as connection attempts, authentication history, and policy violations.
        * Administrators can quickly identify who is connected to which resources and detect any anomalies.
    * Collected logs are automatically stored in NHN Cloud’s Object Storage (OBS) or integrated with the Log & Crash Search service, based on the customer’s security requirements. This supports long-term log retention, regulatory compliance, and helps customers build a more structured and secure operating environment.